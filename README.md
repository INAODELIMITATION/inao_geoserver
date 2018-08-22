# Docker image for GeoServer

A docker image that runs GeoServer version 2.13.2 
With many plugins :
* OGR plugin
* GDAL plugin
* printing plugin
* import plugin
* **vector tiles plugin**

## To run

```bash
docker run -d -p 8080:8080 --name geoserver -v /home/geoserver/data:/opt/geoserver/data_dir mbaussier/inao_geoserver
```

# Fichiers modifiées dans la configuration de Geoserver

Deux fichiers sont modifiés dans la configuration de geoserver : 
1. /opt/geoserver/data_dir/gwc/geowebcache.xml 
Les deux lignes suivantes doivent signifient que nous utilisons dans la notation des coordonées passées en (x,y) et non (y,x) & que le point de référece de l'image et celui en haut à gauche.
`<yCoordinateFirst>false</yCoordinateFirst> `
`<alignTopLeft>true</alignTopLeft>`

2. 
