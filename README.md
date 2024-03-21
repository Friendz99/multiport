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

cd /root/udp

systemctl stop udp-custom

/root/udp/udp-custom server -exclude 1,54,55,1000,65535

# install trial

cd /usr/bin
curl fawzya.net/repo/debian/trial.sh > trial
chmod +x trial
cd
