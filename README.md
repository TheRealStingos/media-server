
# Automated Home Media Server

Years ago, I started hosting a Plex Media Server for my family. What started as a simple hard drive attached to a Raspberry Pi has become much more—a fully containerized, automated system for requesting, acquiring, and serving content. 

Currently, the capacity sits at 40TB


![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=flat&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-Reverse_Proxy-009639?style=flat&logo=nginx&logoColor=white)
![Plex](https://img.shields.io/badge/Plex-Media_Server-EBAF00?style=flat&logo=plex&logoColor=black)
![Portainer](https://img.shields.io/badge/Portainer-Container_Mgmt-13BEF9?style=flat&logo=portainer&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-Self_Hosted-FCC624?style=flat&logo=linux&logoColor=black)
![Services](https://img.shields.io/badge/Services-25+-blueviolet?style=flat)
![Users](https://img.shields.io/badge/Users-10+-brightgreen?style=flat)
## Screenshots

![Server Structure](https://photos.stinko.zone/api/assets/3fd0dbc4-9e10-440d-a87c-883ea82d2898/thumbnail?slug=server&size=preview&c=%2FfcBA4Bml7efiKl6UI5qrvU%3D&edited=true))
![Home Board Screenshot](https://photos.stinko.zone/api/assets/1aa541a5-cf4f-41a8-b6bd-cf6e41488cc9/thumbnail?slug=Homarr&size=preview&c=DAgCA4AJmIiUiVmHrIOff8c%3D&edited=true)


## Services Table
| Category | Service | Purpose |
|---|---|---|
| Media Server | Plex | Streaming Movies, TV, and Music to all clients |
| Comics Server | Komga | Stream Comics and Manga to all clients |
| eBooks Server | Calibre Web Server | Serve eBooks to all clients |
| Image Backup | Immich | Backs up and serves photos to all clients |
| Requests | Overseerr | User-facing request portal |
| TV Automation | Sonarr | Monitor and organize TV shows |
| Movie Automation | Radarr | Monitor and organize movies |
| Music Automation | Lidarr | Monitor and organize music |
| Book Automation | Readarr | Monitor and organize books |
| Indexer Management | Prowlarr | Unified indexer management |
| P2P Download Client | Deluge | Handles all torrent downloads |
| Usenet Download Client | SABnzbd | Handles all usenet downloads |
| Container Management | Portainer | GUI for Docker containers |
| Reverse Proxy | Nginx | Routes subdomains, handles SSL |
| Dashboard | Homarr | Internal service homepage |
| Plex Statistics |  Tautulli | Tracks Plex usage stats and generates graphs/reports |
| File browser | Copyparty | Allows remote copy, edit, and download of files on the server |


## Future Rebuild
This project grew from a small Raspberry Pi with an external HDD to a mini PC with 5 external drives. This is, frankly, unsustainable, and we are running up on our limits.

As such, I plan on a full rebuild with redundency, reliability, and scalability in mind.

### Hardware
- Ryzen 1700x - I have this sitting in my closet from an old build
- 32GB DDR4 RAM - What I have lying around. Lord knows I'm not buying more
- Intel Arc A380 - Provides hardware AV1 encode and decode. Can be found for cheap.
- LSI 9300-16i 16 Port HBA - provides support for 16 additional storage drives
- 3x 20TB HDDs - The basis of the new server's storage. Old storage will be reused (more on this later)
- Old Storage - 20TB HDD, 10TB HDD, 8TB HDD, 1TB HDD, 1TB SSD
- Jonsbo N5 case - NAS case with support for 12 HDDS and 4 SSDs

### Software
- Unraid - Provides the same containerized structure I am enjoying now, but allows for added redundancy through parity disks. Unraid will also allow the use of mixed storage sizes within the same pool.

My plan is to transfer the current server data to the new drives with 1 parity disk, meaning 2 of the 20TB drives will hold the data, and 1 will be used for redundancy.

Once that is confirmed to be working, I will add the drives from the original server to the pool to expand storage. The 1TB will be used as a caching drive to speed up access. All in all I should have ~79TB of space on the server with ready to go hot swap expansion bays when the need arises.
