# Docker image for GeoServer

A docker image that runs GeoServer version 2.13.2 

With many plugins :
* OGR plugin
* GDAL plugin
* printing plugin
* import plugin
* **vector tiles plugin**

With a config file **web.xml** witch override the original configuration. 

## To run

```bash
docker run -d -p 8080:8080 --name geoserver -v /home/geoserver/data:/opt/geoserver/data_dir mbaussier/inao_geoserver
```

# Fichiers modifiées dans la configuration de Geoserver

Deux fichiers sont modifiés dans la configuration de geoserver : 
1. **/opt/geoserver/data_dir/gwc/geowebcache.xml**
Les deux lignes suivantes doivent signifient que nous utilisons dans la notation des coordonées passées en (x,y) et non (y,x) & que le point de référece de l'image et celui en haut à gauche.

```
<yCoordinateFirst>false</yCoordinateFirst> 
<alignTopLeft>true</alignTopLeft>
```

2.  **/opt/geoserver/webapps/geoserver/WEB-INF/web.xml**
Il faut décommenter le block CROSS ORIGIN dans le fichier **web.xml** afin de permettre à Géoserver d'aller chercher dans des bases de données située sur un autre server.

```
  <!-- Uncomment following filter to enable CORS -->
   <filter>
        <filter-name>cross-origin</filter-name>
        <filter-class>org.eclipse.jetty.servlets.CrossOriginFilter</filter-class>
  </filter>
 ```
