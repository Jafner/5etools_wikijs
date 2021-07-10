---
title: 5eTools Install Guide
description: Walk through setting up your own instance of 5eTools
published: true
date: 2021-07-10T02:12:56.740Z
tags: 
editor: markdown
dateCreated: 2021-07-07T23:02:22.605Z
---

# Running Your Own Instance of 5eTools

This page describes methods for accessing 5eTools content other than the [5e.tools](https://5e.tools) website. This is useful if you would like to access 5eTools content offline, or you want to auto-load homebrew specific to your group or campaign.

# Get the 5eTools source code

Go to [get.5e.tools](https://get.5e.tools) and download the latest release of the 5eTools development files. 

![get.5e.tools.png](/assets/get.5e.tools.png)

# Serving the Files
Once you have the 5eTools server source files, you'll need a way to serve them, on your PC, local network, or even the internet. This guide will cover setting up 5eTools with a handful of the most popular web servers, sorted by operating system.

## Windows
For the purposes of this guide (to keep our wiki maintainers sane), we'll assume you're using Windows 10.
### XAMPP by Bitnami
[XAMPP](https://www.apachefriends.org/index.html) is a completely free, easy to install Apache distribution containing MariaDB, PHP, and Perl. The XAMPP open source package has been set up to be incredibly easy to install and to use.

1. [Download XAMPP](https://www.apachefriends.org/index.html) from Bitnami's website and install it. It will default to the `C:/xampp` install directory. It is recommended that you change this to `C:/Users/user/Programs/XAMPP/`, or similar.
2. Open the XAMPP control panel and click on the "Explorer" button on the right to open the server folder and navigate to the `htdocs` subfolder.
3. Delete the existing contents of the `htdocs` directory, then extract the 5eTools server files into the `htdocs` folder.
4. Click the "Start" button for the "Apache" service, then allow XAMPP through your Windows firewall. 
5. Done! You can now access your 5eTools instance at `http://localhost`. 

For more information, check out the [Windows FAQ for XAMPP](https://www.apachefriends.org/faq_windows.html).

### Microsoft IIS
[Internet Information Services](https://en.wikipedia.org/wiki/Internet_Information_Services) (IIS, formerly Internet Information Server) is an extensible web server software created by Microsoft for use with the Windows NT family. IIS supports HTTP, HTTP/2, HTTPS, FTP, FTPS, SMTP and NNTP. It has been an integral part of the Windows NT family since Windows NT 4.0, though it may be absent from some editions (e.g. Windows XP Home edition), and is not active by default. 

1. Enable Microsoft IIS by opening your Start menu and opening the "Turn Windows features on or off" dialog.
2. Find the entry for "Internet Information Services" and check it, then click "OK". Windows will automatically download and install the required files.
3. Restart your PC to complete the installation.
4. After restarting, open the default IIS web files directory at `C:/inetpub/wwwroot/`. Delete the existing contents and extract the 5eTools server files into that folder.
5. Done! You can now access your 5eTools instance at `http://localhost`.

For more information, check out [Microsoft's documentation for IIS](https://docs.microsoft.com/en-us/iis/get-started/getting-started-with-iis/getting-started-with-the-iis-manager-in-iis-7-and-iis-8).

You can manage IIS with the IIS Manager GUI application.

## Linux
For the purposes of this guide (to keep our wiki maintainers sane), we'll assume you're using Debian 10 (Buster). As these steps all take place in the terminal, it should be simple to translate to Debian derivatives (such as Ubuntu), or other distributions.

### Apache2
The [Apache HTTP Server](https://en.wikipedia.org/wiki/Apache_HTTP_Server) is a free and open-source cross-platform web server software. Apache is developed and maintained by an open community of developers under the auspices of the Apache Software Foundation.

1. Open the terminal and run `sudo apt update && sudo apt install apache2` to install the webserver.
2. Launch the Apache process with `/etc/init.d/apache2 start`.
3. Download the 5eTools server files into your working directory with `curl -s -o 5etools.zip -O -J https://get.5e.tools/release/`.
4. Extract the zip file into the Apache root directory with `sudo unzip 5etools.zip -d /var/www/html/`. You can then delete the 5etools.zip file with `rm 5etools.zip`. 
5. Done! You can now access your 5eTools instance at `http://localhost` or at your host's IP address over LAN. You can find your host's IP address with `hostname -I | awk '{print $1}'`

For more information, check out the [Apache docs](https://httpd.apache.org/docs/).

### Nginx
TODO

### Docker
[Docker](https://www.docker.com/) is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. Containers are isolated from one another and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels.

1. Install Docker with `sudo apt update && sudo apt install docker`.
2. Enable the Docker service with `sudo systemctl enable docker`.
3. Add your user to the Docker group `sudo usermod -aG docker $USER`, then log out of your terminal and log back in for this change to take effect.
4. Run the Docker container with `docker run -d -p 80:80 --rm --name 5etools-docker jafner/5etools-docker`. 
5. Done! You can now access your 5eTools instance at `http://localhost` or at your host's IP address over LAN. You can find your host's IP address with `hostname -I | awk '{print $1}'`

For more information about Docker, check out the [Docker docs](https://docs.docker.com/).
For more information about the Jafner/5etools-docker image, check out the [Github repository](https://github.com/Jafner/5etools-docker) or [Dockerhub page](https://hub.docker.com/repository/docker/jafner/5etools-docker).

## MacOS
TODO

# Auto-Loading Homebrew
Once you have a working instance of 5eTools, you can configure your instance to automatically load your choice of homebrew files for anyone browsing your instance. This is useful if you have personal homebrew that you would like to make easily accessible to your gaming group, or if members of your party are using homebrew for their characters and you would like to have that content pre-loaded.

Note: this only works with homebrews already converted to work with the 5eTools homebrew schema. Read more about that on the [homebrew page](/homebrew/).

1. Browse the [5eTools homebrew repository](https://github.com/TheGiddyLimit/homebrew) and download the files you want to automatically import. 
2. Navigate to the `/homebrew/` subdirectory of your 5eTools installation folder. The location depends on which of the installation methods above you used.
3. Copy the homebrew json files you want to import into this directory.
4. Edit the `/homebrew/index.json` file. Add the filenames of your newly-added homebrew files to the `"toImport"` array. When you're done, it should look something like this:

```json
"toImport": [
    "Brewer; Cool Magic Items.json",
    "Brewer; Cool Monsters.json",  
    "Me; My Campaign Brews.json"
]
```
Pay special attention to the use of commas. All but the last item in the list should have a comma at the end.

5. Done! You should now see your homebrew load automatically when you refresh the page.

For more information, check out the [homebrew page](/homebrew/) of this wiki.

