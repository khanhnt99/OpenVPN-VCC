- https://www.programmersought.com/article/3622231711/
- https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-ubuntu-18-04
- https://www.webservertalk.com/setup-openvpn-ubuntu-18-04/

```
#/bin/bash

KEY_DIR=~/client-config
OUTPUT_DIR=~/client-config
BASE_CONFIG=~/client-config/client-sys.conf

cat ${BASE_CONFIG} \
    <(echo -e '<ca>') \
    ${KEY_DIR}/ca.crt \
    <(echo -e '</ca>\n<tls-auth>') \
    ${KEY_DIR}/${1}.key \
    <(echo -e '</tls-auth>') \
    > ${OUTPUT_DIR}/${1}.ovpn
```
