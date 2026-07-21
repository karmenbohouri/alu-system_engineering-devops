The script:

1. Installs Nginx if it is not already installed
2. Adds an `add_header X-Served-By $hostname;` directive to the default
   Nginx site configuration, right after the `listen 80 default_server;`
   line, only if it isn't already present (so the script can be run more
   than once safely)
3. Starts Nginx if it isn't running yet, or restarts it if it is, so that
   the new configuration is picked up

#### Usage

```bash
sudo bash 0-custom_http_response_header
```

#### Verification

```bash
curl -sI http://<SERVER_IP> | grep X-Served-By
```

Expected output (hostname will vary per server):