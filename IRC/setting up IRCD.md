# IRCD setup
*I'll assume the user is already made on the system*

## Compiling
First, we'll need to grab a tarball of the IRCD we're using. The latest at the time of this writing is 2.0.16

```bash
wget https://github.com/inspircd/inspircd/archive/v2.0.16.tar.gz
tar -xvf v2.0.16.tar.gz
cd inspircd-2.0.16
```
Next, run the configure script.

```bash
./configure
make
sudo make install
```
### Notes
1. We want all the SA* modules activated
2. Make sure to activate the spanningtree module, so we can connect services
3. Add a U:Line for services
4. Blacklist all channels and whitelist the ones we need individually.

## Running

```bash
cd ../Inspircd
./inspircd start
```
Assuming you configured properly, and there are no syntax errors, it should start up and be ready for use.
