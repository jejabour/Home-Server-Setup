# Plex

### Installation

Refer to the [Quick-Start](https://support.plex.tv/articles/200264746-quick-start-step-by-step-guides/) guide for getting your own Plex server up and running.

But it really is pretty much as simple as installing the app, signing in, and choosing the location of your movies. On a home server without a screen, it is slightly different.

I instead used the [Proxmox Installer Script](https://tteck.github.io/Proxmox/) for Plex. It should create a container with Plex installed. Of course, it's always smart to go into the container and run an update command, especially since you need to do that to update the Plex server itself from time to time. "apt update" followed by "apt upgrade"

### Finding the Movies on my NAS

When I added my NAS to my server, to be honest I completely forgot how I did it, but it is added as SMB/CFS disk image storage. Accessing the NAS from within containers is bit trickier. The container HAS to be Unpriviliged.

I use the [bind mount](https://pve.proxmox.com/wiki/Linux_Container#_bind_mount_points) option to access my NAS. 

