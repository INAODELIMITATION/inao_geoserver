# Docker image for GeoServer

A docker image that runs GeoServer version 2.13.2 

## With many plugins :
* OGR plugin
* GDAL plugin
* printing plugin
* import plugin
* **vector tiles plugin**

## With a config file web.xml witch override the original configuration. 

## To run

```bash
docker run -d -p 8080:8080 --name geoserver -v /home/geoserver/data:/opt/geoserver/data_dir mbaussier/inao_geoserver
```


