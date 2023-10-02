
# Download RStudio Server v2023.09.0+463

RStudio Server enables you to run the RStudio IDE you know and love on a Linux server, accessed from your web browser, bringing the power and productivity of the RStudio IDE to a centralized server-based environment.  
  
Select Your Operating System:

## Step 1:  
Select your server version  

Debian 10 / Ubuntu 20

## Step 2:  
Install R  

RStudio Server requires Debian version 10 (or higher) or Ubuntu version 20 (or higher). RStudio requires a previous installation of R version 3.3.0 or higher. To install the latest version of R you should first add the CRAN repository to your system.  
  
[Debian Packages for R](https://cran.rstudio.com/bin/linux/debian/)  
  
[Ubuntu Packages for R](http://cran.rstudio.com/bin/linux/ubuntu/)

You can then install R using the following command:

sudo apt-get install r-base

## Step 3:  
Install RStudio Server

You may choose to [verify the build's GPG signature](https://www.rstudio.com/code-signing/) prior to installing it.

To download and install RStudio Server open a terminal window and execute the following commands.

sudo apt-get install gdebi-core

wget https://download2.rstudio.org/server/focal/amd64/rstudio-server-2023.09.0-463-amd64.deb

sudo gdebi rstudio-server-2023.09.0-463-amd64.deb
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE2OTQxNTMyOF19
-->