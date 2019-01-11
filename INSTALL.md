# Fgcoin

## `Fgcoin Installation on Linux using Ubuntu`
### `Step 1`
Use the following commands to install the `BerkelyDB package`.
```
# add-apt-repository ppa:bitcoin/bitcoin
# apt-get update
# apt-get install libdb4.8-dev libdb4.8++-dev
```

### `Step 2`
Install the required packages using the following commands.
```
# apt-get install libboost-all-dev libzmq3-dev libminiupnpc-dev
# apt-get install curl git build-essential libtool autotools-dev
# apt-get install automake pkg-config bsdmainutils python3
# apt-get install software-properties-commen libssl-dev libevent-dev
```

### `Step 3`
Create a directory to the Fgcoin node software and download the package:
```
# mkdir /coins
# cd /coins
# git clone https://github.com/fgshop/fgcoin.git
```

### `Step 4`
Compile and install the Fgcoin node:
```
# cd fgcoin
# ./autogen.sh
# ./configure
# make
# make install
```

### `Step 5`
Now, let's create the **fgcoin.conf** configuration file:
```
# mkdir /home/<username>/.fgcoin
# vim /home/<username>/.fgcoin/fgcoin.conf
```

### `Step 6`
Add the following lines to the **fgcoin.conf** configuration file:
```
rpcuser=username
rpcpassword=userpassword
rpcport=9332
rpcallowip=0.0.0.0/0

addnode=123.123.123.123
addnode=124.124.124.124
addnode=125.125.125.125
```

### `Step 7`
`Start` the Fgcoin service as a daemon.
```
# fgcoind -daemon
Fgcoin server starting
```
The Fgcoin service will start to syncronize the blockchain after a couple of minutes.

### `Step 8`
Use the following command to verify the status of the syncronization:
```
# tail -f /home/<username>/.fgcoin/debug.log
```
The blockchain syncrozation might take days or weeks.

### `Step 9`
You are now proud owner of a `Fgcoin node`. If you want to `stop` the service, use the following command:
```
# fgcoin-cli stop
Fgcoin server stopping
```