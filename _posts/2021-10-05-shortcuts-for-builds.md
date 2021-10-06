# Some shortcuts for building from source

Here's the table of contents:

1. TOC
{:toc}

## Build nodejs from source

```
git clone https://github.com/nodejs/node.git
./configure --prefix=/usr/local/nodejs_version_no/
make -j24
make install
```

[See!](https://www.devdungeon.com/content/build-nodejs-source)

## Build nodejs from source

```
wget http://www.sqlite.org/sqlite-autoconf-3070603.tar.gz
tar xfz sqlite-autoconf-3070603.tar.gz
cd sqlite-autoconf-3070603 
./configure --prefix /jmain01/home/JAD002/dxt02/mma89-dxt02/local/sqlite3/
make -j24
make install
```

[See!](https://www.thegeekstuff.com/2011/07/install-sqlite3/)
