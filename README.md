# :world_map: Spatial Analysis with Turf.js 
![Geospatial Analysis](assets/img/Cover.jpg)

**:black_nib: Description:**
The project to import geospatial data into PostgreSQL, as well as to utilize geojson to display location on a Web map and using turf library that functional to analyze and calculate geospatial data on web map variously.

**:black_nib: Related project:**
- [Leaflet](https://github.com/Leaflet/Leaflet) - JavaScript library for mobile-friendly interactive maps.
- [osrm-backend](https://github.com/Project-OSRM/osrm-backend) - High performance routing engine written in C++ designed to run on OpenStreetMap data.
- [turf](https://github.com/Turfjs/turf) - A modular geospatial engine written in JavaScript.

**:black_nib: Requirements:**
- Web server 
- [GeoServer](https://geoserver.org/) - open source server for sharing geospatial data.
- [PostgreSQL](https://www.postgresql.org/) - open source server for sharing geospatial data.
- [PostGIS](https://postgis.net/) - PostgreSQL database extension which adding support storing, indexing and querying geographic data.

## :green_circle: Quick Start
**:black_nib: Installation**
1. Create database and enable PostGIS extension on pgAdmin - [Tutorial](https://github.com/gimleng/GeospatialAnalysis-Front-End-TURFJS/wiki/Setup-PostgreSQL-and-create-PostGIS-database-to-store-shape-file)
2. import shape file into PostgreSQL on GeoServer - [Tutorial](https://github.com/gimleng/GeospatialAnalysis-Front-End-TURFJS/wiki/import-shape-file-into-PostgreSQL-on-GeoServer) <br> - The fire station in Bangkok shape file that used in this project - [data.go.th](https://data.go.th/dataset/fire_station)
3. There has one more file that contain location of fire station in geojson format, and that file has import to project by declare it to js variable <br> - Fire station in geojson format - [urbandata.theurbanis.com](https://urbandata.theurbanis.com/files/4/27) <br> - I do this to show that either shape file or geojson format can work together despite it doesn't the same format
4. This project has installed three different Thunderforest transportation base maps, however in order to activate them, you must first register on their website and obtain an api key. also, you can disregard them and ignore the error in console. <br> - Layer control section (line 332 to 347 in index.html)
5. Put all of The project file into your web-root directory
6. Done!
