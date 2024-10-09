# Proxmox

## Helpful Links

 - [Download](https://www.proxmox.com/en/downloads)
 - [Installation Tutorial](https://youtu.be/5j0Zb6x_hOk?si=IMb_Mvk1pbqVXSJU&t=425)
 - [BindMount Guide](https://youtu.be/aEzo_u6SJsk?si=o41jxCLs2-bICD3H)


## Installation

Installing Proxmox is nearly as simple as installing any other operating system. Download the image of Proxmox to removeable media, insert the media into your computer, and boot into the media. 
Choose the graphical installation once it has started the installer.
It will ask what harddisk to target the installation, you'll want to choose your main storage device that the system boots into if you're going to this primarily as your server. 
It will ask for an email address and password. Choose a password that's easy to remember, you will have to enter it every time you log into the server. The email address is what the system will send notifications to.
The next screen asks for a hostname and ip address, I think the default is fine, but you should probably change the hostname to something you like, I think mine is like jo-server or leia-server or soemthing like that. I believe I left my ip alone
Once it's installed, pay attention to the IP and Port it shows on screen. It would (probably) be the IP you saw earlier, plus :8006. Once it's done and restarted, and if the server has an internet connection, you should be able to type that IP:PORT into a web browser on another computer and be greeted with the ProxMox Virtual Environment

## Proxmox Virtual Environment

There's a lot to look at on the Proxmox screen. O nthe very left hand side if your server and all of it's nodes. On a fresh installation, you'll just see the one Host node under the Datacenter dropdown, and every new VM (Virtual Machine) or CT (Container) will appear within the host node drop down.

 ### Updates

Updates is the first thing you should click on on a new installation. Found in your host node. 
 - Click on Updates and then the Refresh button, and since no one pays for proxmox license, it'll tell you that you don't have a subscription. 
 - Click on Repositories under Updates
 - Click Add, then select the No-Subscription optoin from the dropdown. 
 - Click Add, then go back Updates, and click Refresh. 
 
 Now you'll be pulling from the No-Subscription repository of updates, which is good, because you don't pay for a license. Now click Upgrade and Proxmox will upgrade all the packages. A terminal window will open, and you'll have to type "y" and press enter to accept the upgrades.


### Adding an ISO for use

You can add new ISO images if they are not already available for selection.

 - Click on your local storage
 - Click ISO Images
 - If you have the URL, click Download from URL
 - Paste in the URL and hit Query URL


### Creating a Container

Everything that I've done with Proxmox has been with containers rather than virtual machines. I don't have much need to have a desktop environment since everything I'm doing is hosting/servery stuff

#### Getting Templates

Before you can create a container, you need to have the template for it. This is very easy to do.
 - Click on your local storage
 - Click CT templates
 - Click Templates
 - Download the ones you want

#### Starting a Container
The following are the steps to actually create a new container

 - Click Create CT in the top right
 - A new dialogue box opens. Give it a name and a password 
 - Choose a template
 - Choose the amount of storage you want the container to have accessto
 - Choose the number of CPU cores for the container to have available
 - Choose the amount of RAM for it to have
 - On the network screen, you can set a static IP address, or use DHCP to let your router assign it one. I've never had success setting a static IP, so I just use DHCP and find the IP later inside the container
    - If you do choose to use a static IP and gateway, they have to be in a specific format. For example, if your IP is 172.20.0 and you choose to give it 75, it would be 172.20.0.75/24 and the gateway would be 172.20.0.1

 - I've never messed with the DNS settings.
 - Click create, and if you wanted it to start upon finishing you can check that box.

