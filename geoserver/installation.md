#### Installation
* Download the geoserver image
  ```
  docker pull geonode/geoserver
  ```
* Download the data dir setup package

   Before run the container, dowload lastest data-2.xx.x.zip file from https://build.geo-solutions.it/geonode/geoserver/latest/
   I downloaded data-2.17.2.zip
* Set up data directory
  ```
  $ sudo mkdir /opt/geoserver/
  $ sudo unzip /home/song/data-2.17.2.zip -d /opt/geoserver/
  $ ls /opt/geoserver/
    data
  $ [root@grg-doc-dev geoserver]# cd data/
    [root@grg-doc-dev data]# ls
    cluster                 geofence    gwc         legendsamples  notifier  README.rst        wcs.xml   workspaces
    controlflow.properties  geogig      gwc-gs.xml  logging.xml    palettes  security          wfs.xml   wps.xml
    demo                    geonode     images      logs           plugIns   styles            wms.xml
    download.properties     global.xml  importer    monitoring     printing  user_projections  wmts.xml
  ```
* Run the container:
  ```
  $ docker run --name "geoserver" -v /var/run/docker.sock:/var/run/docker.sock -v /opt/geoserver/data/:/geoserver_data/data -d -p 8083:8080 geonode/geoserver
  ```

