<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> NAGIOS RUNBOOK </p>

# <div align="center"> DevOps Instructor-led Training </div>

# <div align="right"> $`\textcolor{brown}{\text{Contact us: }}`$  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp; </div>

<div align="right"> T O A C C E L E R A T E Y O U R C A R E E R G R O W T H </div>

### <div align="right"> For questions and more details: </div>

<div align="right"> <img src=https://w7.pngwing.com/pngs/759/922/png-transparent-telephone-logo-iphone-telephone-call-smartphone-phone-electronics-text-trademark-thumbnail.png width="20" height="20"> +91 98712 72900 </div>

<div align="right"> <img src=https://pbs.twimg.com/profile_images/1450734615946219520/jmBHQRRa_400x400.jpg width="20" height="20"> https://www.thecloudtrain.com </div>

<div align="right"> <img src=https://icons.iconarchive.com/icons/martz90/circle/512/email-icon.png width="20" height="20"> support@thecloudtrain.com </div>

<div align="right"> <img src=https://png.pngtree.com/png-vector/20221018/ourmid/pngtree-whatsapp-icon-png-image_6315990.png width="20" height="20"> +91 98712 72900 </div>

#
</br>

## $`\textcolor{red}{\text{NOTE: USE UBUNTU 22.04 VIRTUAL MACHINES FOR ALL THE LABS}}`$

## _Find solutions to your assingment below:_

## Exercise 1: Accomplish below task to complete this exercise:

a) Create two Ubuntu 22.04 compute instances, one for Nagios master and other for target host

### _Solution:_

Create two ubuntu 22.04 GCP instances following similar steps

b) Install Nagios on master Ubuntu GCP instance

### _Solution:_

i. Login to master node as ubuntu user and Update package index.

`sudo apt-get update`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/0231494d-ec9d-43c0-b009-40f87a8063c4)

ii. Run the following two commands after that.

`sudo apt-get install wget build-essential unzip openssl libssl-dev`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/e877e337-1fee-47ab-8cc5-77acbabe74fa)

`sudo apt-get install apache2 php libapache2-mod-php php-gd libgd-dev`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/11561b66-b0b3-46e8-9d64-42b89ed03b0c)

iii. Now, add user with the commands given below.

`sudo adduser nagios`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/ba56edeb-fce4-483d-bdef-f48598563b7d)

You can add passwords and Enter the user information as shown below.

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/c09f79af-6c60-4a91-9108-6106d3d29690)

iv. Run the following commands to complete the user adding process.

```
sudo groupadd nagcmd
sudo usermod -a -G nagcmd nagios
sudo usermod -a -G nagcmd www-data
```

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/7273c0f4-15d3-4450-b32d-7ccc95948435)

v. Now that we are set with the prerequisites, install Nagios Core as shown below.

`wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.4.2.tar.gz`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d4400c3a-d448-49be-8a6a-a14e7a5a663b)

vi. Untar the file with the command shown below.

`tar xzf nagios-4.4.2.tar.gz`

Enter the Nagios-4.4.2 directory.

`cd nagios-4.4.2`

vii. Now with the given command make the required configurations.

`sudo ./configure --with-command-group=nagcmd`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/86bacb0c-ac0d-42bd-bee9-7fed50038001)

If the execution ends with the below given setup then we are good to go.

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/82b2a462-7bf0-41c3-bbcc-01d00b61e082)

viii. Now we will make all the configuration work by running the below command:

`sudo make all`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/deb798c7-1600-4606-8956-72ffb67d452d)

If everything is perfect, we should see an output as shown below.

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/45922aa0-fc4a-4043-a344-4be6c9390d9c)

ix. Run the following command.

`sudo make install`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/db5a6f0c-5b10-4017-9c71-07a1b6463895)

After that you will see the output as shown below:

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/b1122efc-0ae4-4d35-8bc7-b3cc6220bf6a)

x. Install init and run the following command.

`sudo make install-init`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/229fd0a3-7791-412a-b36c-65bb11feff67)

xi. Install config and run the following command.

`sudo make install-config`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/18779e4e-fa13-4ff9-9fa4-cc3a694b954f)

xii. Install commandmode as shown below:

`sudo make install-commandmode`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/5cbf241d-f684-491b-b6c9-22b680034567)

xiii. Before moving ahead run the following commands to copy eventhandlers scripts under the libexec directory.

`sudo cp -R contrib/eventhandlers/ /usr/local/nagios/libexec/`

`sudo chown -R nagios:nagios /usr/local/nagios/libexec/eventhandlers`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/c66036dd-c933-42f7-a7da-e86e223a0a15)

xiv. Create Apache configuration

`sudo vim /etc/apache2/conf-available/nagios.conf`

Add the below given content to the configuration file.

```
ScriptAlias /nagios/cgi-bin "/usr/local/nagios/sbin"

<Directory "/usr/local/nagios/sbin">
   Options ExecCGI
   AllowOverride None
   Order allow,deny
   Allow from all
   AuthName "Restricted Area"
   AuthType Basic
   AuthUserFile /usr/local/nagios/etc/htpasswd.users
   Require valid-user
</Directory>

Alias /nagios "/usr/local/nagios/share"

<Directory "/usr/local/nagios/share">
   Options None
   AllowOverride None
   Order allow,deny
   Allow from all
   AuthName "Restricted Area"
   AuthType Basic
   AuthUserFile /usr/local/nagios/etc/htpasswd.users
   Require valid-user
</Directory>
```

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/24e27e04-8769-4a71-9848-1262d2537b09)

xv. Add a password as shown below, to complete apache configuration

`sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/edee1baf-ad75-4415-810a-c0ca27af5d69)

xvi. Enable Apache configuration

`sudo a2enconf nagios`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/1fbe30ee-6fad-41a1-8471-a0f01e9e2dbb)

xvii. Enable Apache configuration

`sudo a2enmod cgi rewrite`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d5bda82d-235e-4e62-89f4-4f275463ee52)

xviii. Restart apache service.

`sudo service apache2 restart`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/fd1e1777-e269-4373-b09d-9d283755294e)

xix. Now go to the main directory.

`cd`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/a936d52e-2d6b-4ee5-9776-6abf86918b36)

xx. To install the required Nagios plugin, download the plugins.

`wget http://www.nagios-plugins.org/download/nagios-plugins-2.2.1.tar.gz`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/24b204ff-8b5d-4424-a0af-1b34f8aa3ffc)

xxi. Untar the file.

`tar xzf nagios-plugins-2.2.1.tar.gz`

xxii. Go inside Nagios-2.2.1 directory.

`cd nagios-plugins-2.2.1`

xxiii. Compile the plugins and then complete the plugin installation process running the three commands given below:

`sudo ./configure --with-nagios-user=nagios --with-nagios-group=nagios --with-openssl`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d0c67386-ab7c-4caa-af72-dc0b5614450e)

`sudo make`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/4f233f5c-dee0-43b0-8999-a89ddc05f5db)

`sudo make install`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/60a544cf-8134-4c37-a9bd-1ce7af323552)

Before we can start using Nagios, we going to need to make a small change in the base configurations.

xxiv. Edit the nagios configuration file located at /usr/local/nagios/etc/nagios.cfg

`sudo vim /usr/local/nagios/etc/nagios.cfg`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/e500790b-20c0-4b27-af45-41288435c7a3)

Uncomment that line:

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d718cad1-6b30-4add-b19f-6fc14062b9af)

xxv. Make the following directory.

`sudo mkdir /usr/local/nagios/etc/servers`

xxvi. Verify the configuration before starting Nagios.

`sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/ddd45682-c1ba-4097-8c76-38155861f3ac)

Everything looks fine!

xxvii. Start Nagios using below command and enable it as service

`sudo service nagios start`

If no error occurs there your Nagios is installed successfully.

c) Access Nagios with _**http://\<MasterIP\>/nagios/**_

### _Solution:_

i. Open the browser and enter below URL. Get the master node public IP from GCP console:

_**http://\<MasterIP\>/nagios/**_

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/346777ef-5b44-4d2c-9a10-f32b58a016cb)

ii. After entering the user id nagiosadmin & password that you set earlier, you will land on a page as shown below:

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/91968e1a-fc48-4b93-88d8-ff5e8def7e97)

Click on host.

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/0568a399-b974-415c-b5d5-5eef08aed908)

We are all set with the Nagios installation on Master.

## Exercise 2: Accomplish below task to complete this exercise:

a) Add a host to Nagios master configuration for monitoring

- i.Install apache2 on client host and make sure its running
  
- ii. Add the host and service definitions in the master machine to monitor HTTP service
  
- iii. Restart the Nagios service on master node
  
- iv. Refresh the Nagios page and check if newly added host is available under monitoring as below

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/f4c9ef18-907c-4932-b160-3502e803f069)

### _Solution:_

Here we will add monitoring Apache HTTP service on remote client:

**Perform following steps on target machine that you need to be monitored by Nagios**

i. Login to target host as ubuntu user and Install apache web server on the client machine

`sudo su – ubuntu`

`sudo apt update`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/7a0c7edd-5683-4715-b025-146f88bc347a)

ii. Run the following two commands after that.

`sudo apt install apache2`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/1e69b36d-c093-4ad8-b675-2bcdadd3f490)

iii. Now, check if the web server is up and running.

`sudo systemctl status apache2`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/b3b0d563-6749-4eb9-9132-f5dbc6d3fb8d)

iv. Run the following command if apache service is not running.

`sudo systemctl start apache2`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/fd8ae129-63b7-4c5d-8de5-98857608f01c)

v. Open browser and enter the following URL. Get the Client machine Public IP from GCP console:

_**http://\<CLIENT\_IP\>/**_

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/ca5d649e-f3ba-4efc-ae8b-4b18dc723a5d)

**Add the host and service definitions in the master machine**

vi. Create the host config file with host and service definitions.

`sudo vim /usr/local/nagios/etc/servers/hosts.cfg`

```
## Default Linux Host Template ##
define host{
name                            linux-box               ; Name of this template
use                             generic-host            ; Inherit default values
check_period                    24x7
check_interval                  5
retry_interval                  1
max_check_attempts              10
check_command                   check-host-alive
notification_period             24x7
notification_interval           30
notification_options            d,r		
contact_groups                  admins
register                        0                       ; DONT REGISTER THIS - ITS A TEMPLATE
}

## Default
define host{
use                             linux-box               ; Inherit default values from a template
host_name                       slave1                  ; The name we're giving to this server
alias                           CentOS 6                ; A longer name for the server
address                         10.128.0.60             ; IP address of Remote Linux host
}

define service {
    use                 generic-service     ; Inherit default values from a template 
    host_name           slave1
    service_description HTTP
    check_command       check_http
}
```

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/203b3c37-d23b-4428-baf3-447c96fce9b9)

vii. Check the nagios configuration file status before starting nagios again.

`sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/5c88f24c-434c-415f-a10c-316f59690ffb)

viii. Now with the given command make the required configurations.

`sudo service nagios restart`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/f8e30a5e-573e-4276-beab-3e85e74fcb1e)

ix. Now go to browser, enter _**http://\<masterIP\>/nagios/**_ .There click on **Services**. You can see a new **HTTP service** added with our last **PING service** in the **Linux\_Host\_001** client.

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/1e0558f2-72a5-486c-9681-4f2f3a01c877)

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/50fe531b-be9a-49e1-919f-2dc4b035d01a)

Successfully added a host and Web Server Monitoring Service in your Client machine.
