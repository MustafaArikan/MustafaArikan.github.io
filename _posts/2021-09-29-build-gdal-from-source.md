# Build gdal from source

Here's the table of contents:

1. TOC
{:toc}

## Build gdal from source

```
wget https://github.com/OSGeo/gdal/releases/download/v3.0.3/gdal-3.0.3.tar.gz
tar xfvz gdal-3.0.3.tar.gz 
cd gdal-3.0.3
./configure --with-python --prefix=/home/username/local/gdal/ --with-proj=/home/username/local/proj/ --without-sqlite3
```

## Build python module and add

```
cd swig/python
python setup.py build
python setup.py install
```
