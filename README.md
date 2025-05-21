# Easily set up [Siyuan](https://github.com/siyuan-note/siyuan) as a web  app using docker compose and Traefik

Siyuan is very big on keeping your data local, but I hate installing apps on my computer, so I much prefer to host it on a VPS and access through the browser.

My personal instance runs on an OCI always free tier ARM instance. This is the only machine I've set it up on.

I've also added [Netdata](https://www.netdata.cloud/) so you can monitor your instance.

## Usage

All you should need to do is erase the .erasethis suffix from all the .env and secret files, replace the filler info with your actual info and then run:

```
docker compose -p inverseproxy -f inverseproxy.yaml up -d
```
Note that the `-p inverseproxy` part of this is important as it ensures that networks get named properly

To start netdata:

```
docker compose -f netdata.yaml up -d
```

To start Siyuan:

```
docker compose -f siyuan.yaml up -d
```

## Credits

Many thanks to [Tecnativa](https://github.com/Tecnativa) for the whole inverse proxy setup.