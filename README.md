# cn-research-reproduction

1. Create an EC2 AWS inscnace
2. Connect to it
3. clone the repo `git clone https://github.com/dmetaxak/cs244pa3.git`
4. Intall mahimahi 
```
sudo apt-get install build-essential git debhelper autotools-dev dh-autoreconf iptables protobuf-compiler libprotobuf-dev pkg-config libssl-dev dnsmasq-base ssl-cert libxcb-present-dev libcairo2-dev libpango1.0-dev iproute2 apache2-dev apache2-bin iptables dnsmasq-base gnuplot iproute2 apache2-api-20120211 libwww-perl
```

```
git clone https://github.com/ravinet/mahimahi
cd mahimahi
./autogen.sh && ./configure && make
sudo make install
```

```
sudo sysctl -w net.ipv4.ip_forward=1
```

5. Install Sprout
```
sudo apt-get install aptitude
sudo aptitude install libboost-math-dev libboost-math1.74.0 libprotobuf23 libprotobuf-dev
```

```
Note that we changed:
libboost-math1.54.0 -> libboost-math1.74.0
libprotobuf8 -> libprotobuf23
```

```
sudo apt-get install iperf
sudo apt-get install libncurses5-dev
```

```
cd alfalfa
./autogen.sh
./configure --enable-examples
```

Modify lines 48n and 101 of [this file](https://github.com/dmetaxak/cs244pa3/blob/0bd5b1d9fcad6d3e68b88176d4a3177d8866313f/alfalfa/src/crypto/base64.cc) with prefix `const` 

```
make
```

Install Python2
```
sudo apt-get install python2
sudo apt-get install python-pip
pip2 install matplotlib
sudo apt-get install python-tk
```

Run the experiment
```
cd ..
./inception.sh
```

Make the graphs
```
echo "backend: Agg" > ~/.config/matplotlib/matplotlibrc
python2 make_graphs.py results/out.txt graphs
```
