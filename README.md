# multiport
Multi
apt update -y && apt upgrade -y && apt dist-upgrade -y && reboot


rm -f setup.sh && sysctl -w net.ipv6.conf.all.disable_ipv6=1 && sysctl -w net.ipv6.conf.default.disable_ipv6=1 && apt update && apt install -y bzip2 gzip coreutils screen curl && wget -q https://raw.githubusercontent.com/Friendz99/multiport/main/setup.sh && chmod +x setup.sh && ./setup.sh && rm -f setup.sh

# install udp

wget -q https://github.com/zhets/project/raw/main/ssh/udp-custom.sh ; bash udp-custom.sh

wget -q https://github.com/Friendz99/project/raw/main/ssh/udp-custom.sh ; bash udp-custom.sh

# cek user udp

cd /root/udp

systemctl stop udp-custom

/root/udp/udp-custom server -exclude 1,54,55,1000,65535

# cek user udp

#!/bin/bash

cd /root/udp || exit 1
systemctl stop udp-custom || { echo "Failed to stop udp-custom service"; exit 1; }

echo "User Online UDP"
/root/udp/udp-custom server --exclude 1,54,55,1000,65535 || { echo "Failed to run udp-custom server"; exit 1; }
echo "Press any key to go back"

systemctl start udp-custom || { echo "Failed to start udp-custom service"; exit 1; }

# install trial

cd /usr/bin
curl fawzya.net/repo/debian/trial.sh > trial
chmod +x trial
cd
