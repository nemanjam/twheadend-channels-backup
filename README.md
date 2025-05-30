
### `data` folder location

```bash
# copy `data` folder to this location to match Docker volume path
/home/orangepi/traefik-proxy/apps/tvheadend/data
```

```yaml
# traefik-proxy/apps/tvheadend/docker-compose.yml

services:
  tvheadend:
    image: lscr.io/linuxserver/tvheadend:latest
    container_name: tvheadend

# ...

# volume path
volumes:
    - ./data/tvheadend/data:/config
    - ./data/recordings:/recordings
```

### Copy channels from backup

```bash
# .gitkeep can remain

# copy channels from backup
scp -r ~/Desktop/twheadend-channels-backup/data pi:/home/orangepi/traefik-proxy/apps/tvheadend/
```