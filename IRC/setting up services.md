# Services setup
I'll assume you already have the IRCD set up and running, and you're /oper'd up on the network so you can see any error messages that might come up while connecting services.

## Compiling
Grab it, unzip it, change to it.

```bash
wget https://github.com/atheme/atheme/archive/master.zip
unzip master.zip
cd atheme-master
```
Configure, make, install.

```
./configure --prefix=/home/ircd/Atheme --enable-large-net --enable-contrib
make
sudo make install
```
### Notes
1. Contrib modules
	1. ns_ajoin
	2. cs_ping
	3. cs_updown
	4. os_kill
2. Don't allow anyone to use os_grant (comment out the priv); keep that kind of thing in the config files ONLY.
## Running

```
cd ../Atheme
./bin/atheme-services
```
