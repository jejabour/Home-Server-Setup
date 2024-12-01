# Home-Server-Setup

This repo is a way for me to remember what the heck I did to make my home server

## Hardware

### Server

I bought a [BeeLink S12 Pro N100](https://www.amazon.com/Beelink-Desktop-Computer-Support-Ethernet/dp/B0BVLS7ZHP/ref=sr_1_3?dib=eyJ2IjoiMSJ9.NQi4lTF4g3Oov9zjBE9EXJnjBya5leBJDp4c3XQOsDthuXufHfBHrYOjpk_Fv3pot9Ak16hh-Ex-Uw6hlZ93wN7m9zbSlzkL1PESiTcUiA36JpbkMAFQsidPQO1d-Vrl5smYcK0sMcJHiheCrcQ4BvGxMKqL4V_jRV5-zzbGHlAwyj1Zea8TwaeM4DzX9jUD4rMdrlxFbD69gqF0muZbEJ5vcNJzLqtZCR839cnajv4.Bd_wVUXUmwmrZA9u4lIBZgfDbmG_iQ2WTxZonjVi0qw&dib_tag=se&keywords=beelink%2Bs12&qid=1728489211&sr=8-3&th=1). Everyone on the r/Plex subreddit seemed to constantly sing it's praises, and I caught one on sale on Amazon.  

### NAS

At the moment, I have a [Buffalo LinkStation](https://www.newegg.com/buffalo-ls720d0402b/p/N82E16822165855?Item=N82E16822165855) with 4Tb of storage, 2x2Tb harddrives. I don't have RAID setup right now, so I guess it's JBOD (Just a Bunch Of Disks) because I have enough movies and TV Shows on one of the drives to take up most of it, and my pc backup on the other. So this NAS is primarily for my Plex setup.

## What's Installed

## [Proxmox](https://www.proxmox.com/en/)

This is the OS I installed onto the server. It's a Linux Server OS that can be accessed in a web portal. Proxmox is used to host any number of virtual environments called Containers. Every service I want my home server to use will be hosted in a container to optimize resource usage. The Proxmox server uses port 8006
My Proxmox guide will be located [here](https://github.com/jejabour/Home-Server-Setup/tree/main/proxmox).

## [Plex](https://www.plex.tv)

Plex is a multimedia hosting app. While it does offer Live TV and rentals, what most use it for is a way to stream their own TV shows, movies, and music from anywhere. Plex is very easy to set up, and while it does exceptionally shine on a local network, it freely lets users stream their content from any remote location
My Plex guide will be located [here](https://github.com/jejabour/Home-Server-Setup/tree/main/Plex)

## [Wireguard](https://www.wireguard.com/)

Wireguard is an open source VPN server. I haven't gotten this one perfectly set up yet, but I want it to be used so I can access my home lab from anywhere.
My Wireguard guide will be located [here]()

## [audiobookshelf](https://www.audiobookshelf.org/)

This is an open source audiobook and podcast server. Similar to Plex, it works off your own provided audiobooks and podcasts and acts as a means to play them on your devices. At the moment, I only have this working on a local network, and the iOS app is in beta with all spots taken, but there is a web app and an Android app.
My audiobookshelf guide will be located [here](https://github.com/jejabour/Home-Server-Setup/tree/main/audiobookshelf)

## [Minecraft Server](https://github.com/gummiflip/minecraft-server-Proxmox)

This is a link to the github documentation I used to set up my minecraft server, assuming it's working. More details in the directory.
My Minecraft Server guide will be located [here](https://github.com/jejabour/Home-Server-Setup/tree/main/minecraft-server)

# TO-DO

## NextCloud

I've tried numerous times to set up NextCloud in a way that I can access my NAS as if it were an online file server, ala Google Drive. 

## NGINX Proxy Manager

I think this will handle a web service for apps of mine, so I don't have to worry about other people stealing my identity or something.

