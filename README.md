Using cjdns repository for Ubuntu
===================

I maintain a cjdns repository for Ubuntu and its derivatives (Mint, elementary OS, etc). It features autostart on boot and auto-respawn on crashes. The code is updated every day with the latest snapshot of [cjdns git master](https://github.com/cjdelisle/cjdns). The server is kindly donated by [Stack Data Network](http://stackdata.net/).

**To add the repository to your system,** open a terminal, enter a root shell
by running ```sudo -s``` and execute the following commands:
```
source /etc/upstream-release/lsb-release 2>/dev/null || source /etc/lsb-release
echo "deb http://ubuntu.repo.cjdns.ca/ ${DISTRIB_CODENAME} main
deb http://h.ubuntu.repo.cjdns.ca/ ${DISTRIB_CODENAME} main
" > "/etc/apt/sources.list.d/shnatsel-cjdns-${DISTRIB_CODENAME}.list"
```
If the above complains about not finding "http://h.ubuntu.repo.cjdns.ca/", that's normal, carry on!

Then add the signing key, either by cloning this repository via ssh (more secure), or by running:
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