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

## Build python module and add for planetary_computer

```
cd swig/python
python setup.py build
python setup.py install

wget https://files.pythonhosted.org/packages/f4/da/3b638a0516e190d49241de4319b6e6747fb1b1f03fe59b86e118aef8c503/planetary_computer-0.4.2-py3-none-any.whl
pip install planetary_computer-0.4.2-py3-none-any.whl
```

## Get pystac

```
wget https://github.com/stac-utils/pystac/archive/refs/tags/v1.1.0.tar.gz
tar xfvz v1.1.0.tar.gz 
cd pystac-1.1.0/
pip install .
```



