Public key for cjdns Ubuntu repository
===================

To add the Ubuntu repository to your system, open a terminal, enter a root shell
by running ```sudo -s``` and execute the following commands:
```
source /etc/upstream-release/lsb-release || source /etc/lsb-release
echo "deb http://ubuntu.repo.cjdns.ca/ ${DISTRIB_CODENAME} main
deb http://h.ubuntu.repo.cjdns.ca/ ${DISTRIB_CODENAME} main
" > "/etc/apt/sources.list.d/shnatsel-cjdns-${DISTRIB_CODENAME}.list"
```

Add the key, either by cloning this repository via ssh (more secure), or by running:
```
wget -O - https://raw.github.com/Shnatsel/cjdns-ubuntu-pubkey/master/buildbot-pubkey.gpg | apt-key add -
```

Run the following to install cjdns:
```
apt-get update
apt-get install cjdns
```

To connect to Hyperboria you'll have to find a friend who's already connected
and fill in their info in /etc/cjdroute.conf, then run ```sudo restart cjdns```
See https://github.com/cjdelisle/cjdns/#2-find-a-friend for more info.