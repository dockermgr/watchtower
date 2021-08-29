# Welcome to dockermgr watchtower installer 👋
  
## watchtower README  
  
### Requires scripts to be installed

```shell
 sudo bash -c "$(curl -LSs <https://github.com/dockermgr/installer/raw/main/install.sh>)"
 dockermgr --config && dockermgr install scripts  
```

#### Automatic install/update  

```shell
dockermgr install watchtower
```


#### Manual install

```shell
git clone https://github.com/dockermgr/watchtower "$HOME/.local/share/CasjaysDev/dockermgr/watchtower"
bash -c "$HOME/.local/share/CasjaysDev/dockermgr/watchtower/install.sh"
```
  
#### Just run it

```shell
mkdir -p "$HOME/.local/share/srv/docker/watchtower/"

git clone <https://github.com/dockermgr/watchtower> "$HOME/.local/share/CasjaysDev/dockermgr/watchtower"

cp -Rfva "$HOME/.local/share/srv/docker/watchtower/dataDir/." "$HOME/.local/share/srv/docker/watchtower/"

sudo docker run -d \
--name="watchtower" \
--hostname "watchtower" \
--restart=unless-stopped \
--privileged \
-e TZ="${TZ:-${TIMEZONE:-America/New_York}}" \
-v "$HOME/.local/share/srv/docker/watchtower/data":/data:z \
-v "$HOME/.local/share/srv/docker/watchtower/config":/config:z \
-v /var/run/docker.sock:/var/run/docker.sock \
containrrr/watchtower 1>/dev/null
```

## Author  

👤 **Jason Hempstead**  
