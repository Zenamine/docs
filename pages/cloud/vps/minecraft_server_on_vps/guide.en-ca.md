---
title: 'How to create a minecraft server on a VPS or dedicated server'
slug: create-minecraft-server-on-vps
excerpt: 'Craft your own server and build your wold !'
section: Tutorial
---

## Objective

Minecraft is successful sandbox video game. It needs to be hosted on a server if you wish to play in multiplayer.

You can rent a pre-build minecraft server or you can set it up yourself on a [VPS]({ovh_www}/vps/) or on a [dedicated server]({ovh_www}/dedicated-servers/){.external}. This will reduce the cost and give you full control over your game instance.

In this tutorial, we will create a Minecraft Java Edition on a OVHcloud VPS et test its connectivity.

> [!warning]
> 
> 
OVHcloud offers servers where you are responsible of its configuraiton. OVHcloud does not have access to your server and we will not administer or offer software assistance. It is your responsibility to manage and secure your services.
>
> 
This document is offered as a guideline. We invite you to contact a specialized provider if you need help in managing your server. Do not hesitate to visit our [community forum] (https://community.ovh.com/en/) {.external} to exchange with others.
>

## Requirements

### Knowledge

- Some general knowledge on how to administer Linux.
- SSH connection
- Install a Linux distribution (in this case, Debian 9 or Ubuntu 18.04).

### The must have

- Own [VPS]({ovh_www}/vps/){.external}. with 2 Gb of RAM minimum.
- Download *minecraft_server.1.16.1.jar* via <https://www.minecraft.net/en-us/download/server/>.

## Instructions

### Step 1 : Prepare the server

Nous allons préparer notre serveur VPS pour accueillir Minecraft. Si cela est possible, nous vous conseillons de réinstaller votre VPS via votre espace client (Ubuntu ou Debian sont conseillés).
We will setup our VPS server to install Minecraft. If possible, please reinstall your VPS from your control panel (Ubuntu or Debian is recommanded).

Une fois le VPS installé, connectez-vous à votre VPS en SSH avec l’utilisateur principal root (administrateur), en utilisant un terminal. Mettez à jour la liste des paquets :
Once the distribution is installed, connect to your VPS with SSH as root using a terminal. Update the packages:

```sh
apt update
```

Update the systeme: 

```sh
apt full-upgrade
```

Pour la suite de l'installation, certains paquets non présents par défaut sont nécessaires. Voici la commande :
We will need to intall packages that are not present by default. Here is the command:  

```sh
apt install default-jre screen nano wget git
```

To avoid vulnerabilities on your system, we will create a user named « minecraft ». This user will execute the minecraft process:

```sh
adduser minecraft --disabled-login --disabled-password
```

Several information are requested ; simply press `Enter`{.action} key to vaildate.

The user is not created. Please note that no password was specified which is normal. This account is only accessible by SSH and will only be accessible through the root account.

Il est temps de vous connecter à l'utilisateur « minecraft » user : :
It is now time to connect to the « minecraft » user :

```sh
su - minecraft
```

Enfin, pour terminer la mise en place de l'environnement, nous allons créer un dossier nommé `server` dans le dossier personnel actuel :
To complete the operating system setup, we will create a folder named `server`.

```sh
mkdir ~/server && cd ~/server
```

> [!primary]
>
> Reminder : This last command needs to be done by the user « minecraft ».
> 
  

### Step 2 : install your Vanilla Minecraft server.

> [!primary]
> 
> A Vanilla server is an instance without any add-ons or plugins. You will experience the game the way it was made by the devellopers.
>
> 


Please go to [the official Minecraft website](https://minecraft.net/download/server) to download the file. Just right click on `minecraft_server.1.16.1.jar` to copy the link.

Now that we have the URL, download it on the VPS. Make sure you are located in the `server` folder you created earlier and type:

```sh
wget <paste the URLt>
```


Before launching the server, you need to agree to the End User License Agreement.

In the same folder, use the following command:

```sh
echo "eula=true" > eula.txt
```

This action will create the file `eula.txt` on the root lever of your server. It will containt `eula=true` which means that you accept the terms and conditions of minecraft. We invite you to review the terms and conditions on the minecraft official website.

Your server can now be started.


During step 1, we intalled the `screen` package which gives you the possibility to have multiple session of the terminal (*shell*). We will start Minecraft in a new session and launch it in the background. `screen` can be very handy, it gives us the possibiilty to launch multiple Minecraft servers simultanously.

First, we will create a new `shell` named `minecraft1` :

```sh
screen -S minecraft1
```

The active terminal window will change, this automatically toggles a new session `shell`. You can creat other `shells` if nécessary and list them via this command:

```sh
screen -ls
```

To switch from one `shell` to another, you can use a shortcut such as `CTRL+a n`{.action}. You can also achieve this in command line by typing the `shell` name:

```sh
screen -x another_shell
```

Move to the `minecraft1` shell that you have created and launch the Minecraft server wit the following command:

```sh
java -jar name.of.the.downloaded.file.jar
```

If you wish to shutdown your server, use the command `stop`.

### Step 3 : connect to the server

Your server instance is now fucntionnal, lets test the connection. You will need to download the Minecraft client from this website: <https://minecraft.net/>

Install et launch the Minecraft client et sign-in.
![Server connection](images/login_minecraft.png){.thumbnail}


On the next screen, in the field `Server name`, enter your server name. In the field `Server Address`, enter your VPS IP address.
![Server information](images/minecraft_server_login.png){.thumbnail}

By default, no port needs to be specified.

## Conclusion

Your Vanilla Minecraft server is now installed on your VPS. 

Please note that this installation guide should also work on a dedicated server or a OVHcloud Public Cloud instance. With those services, you will enjoy better stability since the hardware is dedicated.

Finally, for add-ons, mods and to personalize your Minecraft experience, please consult this official documentation <https://help.mojang.com/>. 

