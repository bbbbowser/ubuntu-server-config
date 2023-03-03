in order to avoid DNS conflicts for the ubuntu server and docker containers, some changes need to be made to `systemd-resolved.service`

stop `systemd-resolved.service` from listening on port 53 by editing the `/etc/systemd/resolved.conf` file:
```
sudo vim /etc/systemd/resolved.conf
```
uncomment the `DNSStubListener` line and set the value to `no`

restart systemd-resolved
```
sudo systemctl restart systemd-resolved.service
```
make sure to edit the `netplan` configuration in `/etc/netplan/<whatever>.yaml` to include default nameservers such as cloudflare's `1.1.1.1` or the system will be unable to resolve DNS queries.

an example is given in https://github.com/bbbbowser/ubuntu-server-config/blob/main/netplan/static.yaml
