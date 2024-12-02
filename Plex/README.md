# Plex

I'm writing this guide for both people who are running Plex on their own computer in a normal desktop environment, under Local Machine headers, and for people running off of a proxmox server environment, under Proxmox Server headers

# Table of Contents
1. [Installation](#installation)
2. [Naming Movie Files](#naming)
3. [Locating the Movies](#locating-the-movies-for-the-plex-library)
4. [Updating](#updating-the-plex-server)
5. [Acquiring Movies](#acquiring-movies)



## Installation <a name="installation"><a/>

### Local Machine
Refer to the [Quick-Start](https://support.plex.tv/articles/200264746-quick-start-step-by-step-guides/) guide for getting your own Plex server up and running.

But it really is pretty much as simple as installing the app, signing in, and choosing the location of your movies. On a home server without a screen, it is slightly different.

### Proxmox Server

I instead used the [Proxmox Installer Script](https://tteck.github.io/Proxmox/) for Plex. It should create a container with Plex installed. Of course, it's always smart to go into the container and run an update command, especially since you need to do that to update the Plex server itself from time to time. "apt update" followed by "apt upgrade"

## Naming Movie Files <a name="naming"></a>

Plex is pretty smart about organizing and recognizing movies, but it does movies to be at least close to a specific format. I typically just have the movie name followed by a year. I'll use the original Disney classic Cinderella for example. In my movies directory, I have it listed as

`Cinderella (1950).mkv`

I have had Plex recognize a movie properly without the year, but Cinderella is a good example since there (at least) are 2 movies with that name, and I have both the classic and the 2015 live action movie in my library. So when I add

`Cinderella (2015).mkv`

Plex will correctly recognize both of them. Refer to the [Plex documentation on naming](https://support.plex.tv/articles/naming-and-organizing-your-movie-media-files/) on naming

Additionally, you may find you have different editions of movies. I have some movies in the Diamond Edition in my Disney collection for example, and Plex offers means to circumvent this as well using {edition-Diamond Edition}. Refer to the [Plex documentation on editions](https://support.plex.tv/articles/multiple-editions/) for more info

`Sleeping Beauty (1959){edition-Diamond Edition}.mkv`



## Locating the Movies for the Plex Library <a name="locating"></a>

### Local Machine

When you first startup Plex, it should ask you for a path to some movies. It really is as simple as pointing Plex to a directory where your movies are stored.

### Proxmox Server

When I added my NAS to my server, to be honest I completely forgot how I did it, but it is added as SMB/CFS disk image storage. Accessing the NAS from within containers is bit trickier. The container HAS to be Unpriviliged.

I use the [bind mount](https://pve.proxmox.com/wiki/Linux_Container#_bind_mount_points) option to access my NAS. Some of what I wrote below is pretty similar to what's found on this site.

In Proxmox, in your main username terminal, you can navigate to /etc/pve/lxc, and in this directory, there will be .conf files that have the same name as the numerical number of your container. 
Inside the file of the container you want to add your NAS shared folders to, add a line like the following:

`mp0: /mnt/bindmounts/shared, mp=/shared`

Where the first 'shared' after bindmounts/ represents the name of your directory, and the 'shared' after mp=/ represents what you want the directory to be called in the container.
For example, I am sharing a directory called Buffalo_2 in my server, and I want it to be called Z in my container, so my line looks like

`mp0: /mnt/pve/Buffalo_2, mp=/Z`

Once this is saved, I can go into Plex on the browser, and add the library.
My library path looks like: `/Z/Videos/Movies`, so that's what I added in Plex.

## Updating the Plex Server <a name='updating'></a>

Occasionally Plex wil push out an update that you can install at your own convenience. Doing so doesn't hinder you other than the server is down for like 20 seconds.

### Local Machine

On the Plex Dashboard, there will be an orange up arrow circle icon in the upper right corner. Just hit that and hit Update

### Proxmox Server

A little more complicated, but not much really. In the Plex container, open the terminal and just do an `apt update` `apt upgrade -y`


## Acquiring Movies <a name="acquiring-movies"></a>

This can be an entire rabbit hole on it's own. And it is.
Aside from the obvious seven seas you could sail, I wanted my library to consist of mostly movies I physically own, and unfortunately it is not as easy as just buying a blu ray drive, plugging it into your pc, popping a movie in, and clicking the "Get movie" button.

Because of the rabbit hole-ness of this, I'm going to move this to a separate page [here](https://github.com/jejabour/Home-Server-Setup/blob/main/Plex/Getting%20Movies/README.md)
