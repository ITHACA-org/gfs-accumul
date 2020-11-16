# GFS-Accumul

GFS-Accumul is an [ERDS](http://erds.ithacaweb.org) component but it can also be used as a standalone application.  

## Installation and requirements

It requires python3 and wgrib2.
```
apt-get update  
apt-get install -y build-essential libaec-dev zlib1g-dev libcurl4-openssl-dev libboost-dev curl wget zip unzip bzip2 gfortran gcc g++
```

### How to install wgrib2

Download wgrib2 from ftp://ftp.cpc.ncep.noaa.gov/wd51we/wgrib2  
```
wget ftp://ftp.cpc.ncep.noaa.gov/wd51we/wgrib2/wgrib2.tgz.v2.0.8 -O /home/myuser/wgrib2.tgz  
tar -xf /home/myuser/wgrib2.tgz  
cd /home/myuser/grib2/wgrib2  
export FC=gfortran && export CC=gcc  
make  
ln -s /home/myuser/grib2/wgrib2/wgrib2 /usr/local/bin/wgrib2  
```

## Configuration

In the settings.py file you need to set the paths for GFS_DATA_DIR (where the GRIB data are downloaded and converted to BIN files), GFS_OUTPUT_DIR (where cumulated and alert TIFFs files are saved) and THRESHOLDS_DIR_ABSPATH (where your masks TIFFs and thresholds.ini are stored).  

## Usage

It can be run manually with

```
python3 erds_gfs.py
```
or in a time-based job scheduler such as crontab.
