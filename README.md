# Tor in NeoTerm

To install neoterm, visit the following site:
https://github.com/NeoTerm/NeoTerm
or
https://android.izzysoft.de/repo/apk/io.neoterm

# How to install Tor on NeoTerm

# Ensure that the NeoTerm is upgraded

apt update
apt upgrade

# Once you have that, you can install the Tor
apt install tor

# Brridge
Follow the steps below to add a bridge

apt install obfs4proxy

If the above step did not go through correctly 
(the package was not installed or you encountered an error E: Unable to locate package obfs4proxy)

To build: go get https://git.torproject.org/pluggable-transports/obfs4.git

To install: Copy $GOPATH/data/data/io.neoterm/files/home/obfs4 to a permanent location (Eg: /data/data/io.neoterm/files/usr/bin/)

Client side torrc configuration:
Edit torrc file and add the following line

ClientTransportPlugin obfs4 exec /data/data/io.neoterm/files/usr/bin/obfs4/obfs4proxy

Get the bridge out of the site:
https://bridges.torproject.org/

Now you must edit the torrc file with the existing editor, eg vi

vi /data/data/io.neoterm/files/usr/etc/tor/torrc

Go to the end of the file and add the bridges to it

UseBridges 1

Bridge obfs4 62.10.95.88:42343 DD685A6DB1522499B1338F3E86A49816E177EA81 cert=UxGhs615rieTh0lwEA3oz8xOMfN/7vbOVaBPT0Gv2SiqS85AIWMljEhu06v0vC2YYfD+ag iat-mode=0

Bridge obfs4 194.135.89.71:443 5D21705C1F5364C2C965C7102C9F0A984E687684 cert=nz/53KYM6QIvReGaC5eAsosEPPXVW9B+EdENFd9yMjaUmKcHLX/149gxBjsXlUeZZi9IFw iat-mode=0

Put your bridges and note that you will add Bridge before bridges

Now you must enter the tor command

tor

If it reaches 100%, tor is ready to work
