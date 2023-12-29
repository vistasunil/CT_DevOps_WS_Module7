<div align="center">
<img src=https://static.wixstatic.com/media/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png/v1/fit/w_2500,h_1330,al_c/1c706c_a5df0ad56f894928bf858a74ba744b32~mv2.png width="400" height="200">
 </div>

# <div align="center"> NAGIOS RUNBOOK </p>

# <div align="center"> DevOps Workshop Training </div>

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

![Screenshot 2023-12-29 at 15 01 42](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/ba5cf0c9-ca81-4faf-b500-775149fd89c1)

ii. Run the following two commands after that.

`sudo apt-get install wget curl build-essential unzip openssl libssl-dev`

![Screenshot 2023-12-29 at 15 09 34](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/1bb69c2c-0503-4398-8a07-cc0eae5023b4)

`sudo apt-get install apache2 php libapache2-mod-php php-gd libgd-dev`

![Screenshot 2023-12-29 at 15 10 39](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/b1b17452-d3c1-42de-9d40-7140d6d54361)

iii. Now that we are set with the prerequisites, install Nagios Core as shown below.

`wget https://assets.nagios.com/downloads/nagioscore/releases/nagios-4.5.0.tar.gz`

![Screenshot 2023-12-29 at 15 11 50](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/245083bd-fd72-4aaa-933f-eb74f589bc73)

iv. Untar the file with the command shown below.

`tar zxvf nagios-4.5.0.tar.gz`

![Screenshot 2023-12-29 at 15 12 51](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/2859008a-89cf-4a96-932c-00d53366675d)

Enter the Nagios-4.5.0 directory.

`cd nagios-4.5.0`

v. Now with the given command make the required configurations.

`sudo ./configure --with-command-group=nagcmd`

![Screenshot 2023-12-29 at 15 17 54](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/9fc624a0-1d39-4d68-ab23-d76ae1c8a7f8)

If the execution ends with the below given setup then we are good to go.

![Screenshot 2023-12-29 at 15 18 17](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/44c965f3-1c00-4672-94d9-876ac2f7a1f8)

vi. Now, create required users and groups with the commands given below.

`sudo make install-groups-users`

![Screenshot 2023-12-29 at 15 20 38](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/354b4a5b-a41d-45f9-8281-a9f14410c8c0)

vii. Run the following commands to complete the user adding process.

```
sudo groupadd nagcmd
sudo usermod -a -G nagcmd nagios
sudo usermod -a -G nagcmd www-data
```

![Screenshot 2023-12-29 at 15 21 28](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/52991a03-6ffe-45f6-a671-23a16a3f8a04)

viii. Now we will make all the configuration work by running the below command:

`sudo make all`

![Screenshot 2023-12-29 at 15 26 17](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/1e6044c7-d970-46af-8d14-f33b0bf50c6b)

If everything is perfect, we should see an output as shown below.

![Screenshot 2023-12-29 at 15 28 01](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/928cddaa-3646-4c96-b510-627fd70abe7b)

ix. Run the following command.

`sudo make install`

![Screenshot 2023-12-29 at 15 28 53](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/803b5005-5881-4d0c-9f86-3211acc2ed31)

After that you will see the output as shown below:

![Screenshot 2023-12-29 at 15 29 33](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d0be181d-3c02-4f57-a9c5-299b29fce6eb)

x. Install init and run the following command.

`sudo make install-init`

![Screenshot 2023-12-29 at 15 33 56](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/f499dfd6-3d66-4546-aaea-5402e1590677)

xi. Install config and run the following command.

`sudo make install-config`

![Screenshot 2023-12-29 at 15 34 32](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/a52d0197-2aa2-4d26-a7e0-3ee294fbc876)

xii. Install commandmode as shown below:

`sudo make install-commandmode`

![Screenshot 2023-12-29 at 15 35 12](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/084e903f-7c10-4985-a645-e5cdbc2996e3)

xiii. Before moving ahead run the following commands to copy eventhandlers scripts under the libexec directory.

`sudo cp -R contrib/eventhandlers/ /usr/local/nagios/libexec/`

`sudo chown -R nagios:nagios /usr/local/nagios/libexec/eventhandlers`

![Screenshot 2023-12-29 at 15 36 17](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/87a02cf8-64cf-4ae7-8021-86631c33eea9)

xiv. Create Apache configuration by installing apache config files

`sudo make install-webconf`

![Screenshot 2023-12-29 at 15 22 37](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/276081bc-de1a-4ae0-823e-be358e9385d6)

xv. Add a password as shown below, to complete apache configuration

`sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin`

![Screenshot 2023-12-29 at 15 37 09](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/2802beb5-ca0c-4bba-9808-98896cd6dce5)

xvi. Enable Apache configuration

`sudo a2enmod cgi rewrite`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d5bda82d-235e-4e62-89f4-4f275463ee52)

xvii. Restart apache service.

`sudo service apache2 restart`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/fd1e1777-e269-4373-b09d-9d283755294e)

xviii. Now go to the main directory.

`cd`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/a936d52e-2d6b-4ee5-9776-6abf86918b36)

xix. To install the required Nagios plugin, download the plugins.

`wget https://nagios-plugins.org/download/nagios-plugins-2.4.4.tar.gz`

![Screenshot 2023-12-29 at 15 23 28](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/650e96d7-840d-4afb-9938-95c70427fe98)

xx. Untar the file.

`tar -zxvf nagios-plugins-2.4.4.tar.gz`

![Screenshot 2023-12-29 at 15 24 16](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/423c1fd1-0cd4-493e-8fb1-23823170a418)

xxi. Go inside Nagios-2.2.1 directory.

`cd nagios-plugins-2.4.4`

xxii. Compile the plugins and then complete the plugin installation process running the three commands given below:

`sudo ./configure --with-nagios-user=nagios --with-nagios-group=nagios --with-openssl`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d0c67386-ab7c-4caa-af72-dc0b5614450e)

`sudo make`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/4f233f5c-dee0-43b0-8999-a89ddc05f5db)

`sudo make install`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/60a544cf-8134-4c37-a9bd-1ce7af323552)

Before we can start using Nagios, we going to need to make a small change in the base configurations.

xxiii. Edit the nagios configuration file located at /usr/local/nagios/etc/nagios.cfg

`sudo vim /usr/local/nagios/etc/nagios.cfg`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/e500790b-20c0-4b27-af45-41288435c7a3)

Uncomment that line:

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/d718cad1-6b30-4add-b19f-6fc14062b9af)

xxiv. Make the following directory.

`sudo mkdir /usr/local/nagios/etc/servers`

xxv. Verify the configuration before starting Nagios.

`sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg`

![image](https://github.com/vistasunil/CT_DevOps_WS_Module7/assets/37858762/ddd45682-c1ba-4097-8c76-38155861f3ac)

Everything looks fine!

xxvi. Start Nagios using below command and enable it as service

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
