# :world_map: Load Spatial Data into PostGIS
![Geospatial Analysis](assets/img/Cover_PostGIS.jpg)

**:black_nib: Related project:**
- [Leaflet](https://github.com/Leaflet/Leaflet) - JavaScript library for mobile-friendly interactive maps.

**:black_nib: Requirements:**
- Web server 
- [GeoServer](https://geoserver.org/) - open source server for sharing geospatial data.
- [PostgreSQL](https://www.postgresql.org/) - open source server for sharing geospatial data.
- [PostGIS](https://postgis.net/) - PostgreSQL database extension which adding support storing, indexing and querying geographic data.
- The fire station in Bangkok shape file that used in this project - [data.go.th](https://data.go.th/dataset/fire_station)

## :green_circle: Setup PostgreSQL and create PostGIS database to store shape file

1. open pgAdmin and waiting to start program completely<br>
![pgAdmin program](https://drive.google.com/uc?id=14_y9GFzzVBMmOx_2fqK_KeJLB6WIzCfD)

2. enter your master password to connect to the server, click ok<br>
![master password](https://drive.google.com/uc?id=1k6B6GgUFTmQfEmycsWFFhHI9vGjorBTQ)

3. click at the server in the navigation menu, enter your password to connect to the PostgreSQL server, click ok<br>
![Server menu](https://drive.google.com/uc?id=1_ObMWsuw7WoWVf_Wp5_GiSbi4tJmY6gZ)

4. Right click at PostgreSQL :point_right: Create :point_right: Database... <br>
![Create Database](https://drive.google.com/uc?id=1c0n0GIR859u7LhvNU2VMIVnTrJmsDT8a)

5. Enter the Database name, click Save  <br>
![Database name](https://drive.google.com/uc?id=1iwCTzTZVvKmMnczSmVk8Qoy4XwNWc0WO)

6. Right click at the database that just create, click CREATE script <br>
![Create script](https://drive.google.com/uc?id=1e7x70PJ67AYPB6YQhCbsLVjSZpsunxOP)

7. In the query box put <br>
```
CREATE EXTENSION postgis;
```
and press F5 to execute to enable PostGIS extention in this database
<br>
You can find out what version of PostGIS you used by 
```
SELECT PostGIS_Full_Version();
```
the result will show in Data output section
![output result](https://drive.google.com/uc?id=1i-jOW9bcj_cBXGQXX41XiqPWdHUH9C0h)

8. Done! the database is ready to use.

## :green_circle: import shape file into PostgreSQL on GeoServer

1. Set up Postgis extension for PostgresQL in Pgadmin <br>

2. Go to http://localhost:8080/geoserver/, signing in and follow up on the next step<br>

3. Entering the Workspaces menu on the left navigation bar and click Add new workspace<br>
![Create Workspace](https://drive.google.com/uc?id=1f370wE5qlF5lmH-Jz6dXem7k9_IzYnU0)
4. Fill in the field under the basic info tab and hit Save<br>
![New Workspace](https://drive.google.com/uc?id=10eS23_tS-YAbVGZ9ggvXEBSTSQEvo63B)

5. Click Add new Store in Stores menu<br>
![Add new store](https://drive.google.com/uc?id=1e4IUoz4Pw2MDhWwgXaM2wrRY26jytAjg)

6. Select PostGIS <br>
![PostGis select](https://drive.google.com/uc?id=1lb0xrqqttmD0tM4OMCNZ3THgAu8lPrGD)

7. Choose a workspace that we have already setup, and fill PostgreSQL information in Connection Parameter section<br>
![Setup PostgreSQL](https://drive.google.com/uc?id=1ksh2ra0oKjOTtrtbNw_YQn13PGEMXU1m)

8. The page will show layer page that have no layer inside<br>
![New Layer Page](https://drive.google.com/uc?id=1A6xQ4qX8hbuMaxIWYE_SdEMfiIxgNEc9)

9. Open PostGIS Shapefile Import/Export Manager and click View connection details... to connect to PostgreSQL<br>
![Connect to PostgreSQL](https://drive.google.com/uc?id=1zm6ZPov9SB_TzqmYea8YQGfKKKKG8Gpw)

10. Click add file, and go to the directory that contains a ShapeFile, then click open<br>
![Add file on PostGIS](https://drive.google.com/uc?id=1sjcZek1DGiDnisN8S3m4f3IIEI0jzY1t)

11. Click import, it should say "Shapefile Import Complete". It will show error if the program can't import Shapefile as utf-8, you can change it in<br> option menu.
![Import ShapeFile](https://drive.google.com/uc?id=1ddoXngWZU6Fs5DDj9rqyATjofJfMC9cG)

12. Verify that a shapefile has been saved in PostgreSQL by opening pgAdmin and take a look in the Table menu<br>
![Check import status in PgAdmin](https://drive.google.com/uc?id=12zTpY0A0BhHfAsRSdchTK5K0q236NiX_)

13. Returning to GeoServer, select Add a new layer from the Layers menu<br>
![Add new Layer](https://drive.google.com/uc?id=1301UgUP_rqGfDo5-nhZWj_ULvEt9eYNx)

14. Choose the layer that was just stoed in PostgreSQL, then click public<br>
![Public Layer](https://drive.google.com/uc?id=1he-FqgZkWSogg5RMJ9H0E8N7SVxmcZTg)

15. Scroll down and press compute from data and native bounds to framed layer area position<br>
![Compute bounding Box](https://drive.google.com/uc?id=1_A8F375iUkhIC6ANZ1UvwmXlASa8Z5hI)

16. Done!<br>
![Check result](https://drive.google.com/uc?id=1k3ARDtU7stv3ZEI6rE_wVAYb2d-hkIqu)
