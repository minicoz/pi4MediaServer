# pi4MediaServer
Rasperri Pi 4 compatible media server

## This is a RASPI 4 compatible media server for DB Techs setup.

Playlist on Youtube here:
https://www.youtube.com/watch?v=ZLa5NGPKQv0&list=PLhMI0SExGwfAdXDmYJ9jt_SxjkEfcUwEB


DB Tech has this awesome docker based setup for his NON raspberry pi version.

This docker-compose file has the correct qbittorentvpn image that works
on the raspberry pi. 

Just update the two yml files according to dbTechs video. Put in your info.

I got this working 99% of the way (organizr wont load grafana but will take you to the page!)

# Important note:

A super important step is to start following NetworkChuck's setup to create the 
OpenMediaVault for raspi4 version: https://www.youtube.com/watch?v=gyMpI8csWis

## Note:
He uses this install script to automatically install OMV and the DOCKER + Portainer extra:

```
sugo apt update && sudo apt upgrade 

sudo wget -O - https://github.com/OpenMediaVault-Plugin-Developers/installScript/raw/master/install | sudo bash
```

This way you prep correctly for the db Techs tutorial. 

PLEASE PLEASE PLEASE just set the priviledges for all forlders (including Configs) to 
`Everyone: read/write`

This finally worked for me after a ton of issues with permissions. 

# What is different?
SABnzbd was not correctly communicating with Sonarr to move the downloaded files into the tv directory. This docker compse has 
the correct docker volume mounted for both Sonarr and Radarr to move the files from SABnzbd download folder to their respective 
folders for Emby to pick up.

Super fun project :)
