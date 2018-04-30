# Integrating Google Earth Engine, Google Cloud, QGIS, and Leaflet



**Objectives**:

- Integrate Remote Sensing applications from Google Earth Engine (GEE)
- Use Google Cloud Platform to save tiles from GEE outputs 
- Use QGIS to take Tiles from bucket in Google Cloud Platform and generate QTiles 
- Use Leaflet to integrate QTiles in html



## 1.0 Set-up and Log-ins

### 1.1 Google Earth Engine (GEE)

GEE is *'a planetary-scale platform for Earth science data and analysis'*. Cloud based platform to query and process remotely sensed imagery such as Landsat, MODIS, Sentinel. Explore **[here](https://earthengine.google.com/)**.

### 1.2 Log-in

New to Google Earth Engine (GEE), create a log-in by clicking **'SIGN UP'** in the upper right corner of the GEE page,  **[here](https://earthengine.google.com/)**. If you are a gmail user you can use your gmail log-in information. Already a GEE user you can also click on the **'SIGN UP'** in the upper right corner of GEE page,  **[here](https://earthengine.google.com/)**, to log-in.

### 1.3 Google Cloud Platform Access Create an Account / Log-in

This should be the same account that you are using with GEE.

### 1.4 Redeem Education Grant

If you have not redeemed your education grant, click **[here](https://google.secure.force.com/GCPEDU/?cid=d0GOdFV%2BTF1xdIizooBa1z8ehdyk91t3C51Dsuzk3BOlTJYPq0BfaE4gxD7ysKNK/)**. Use your OSU email to redeem the coupon. Make sure you are logged into the Cloud Platform with the same log-in as GEE. Then follow the instructions  **[here](https://console.cloud.google.com/education)** to redeem the coupon.

## 2.0 Google Earth Engine 

### 2.1 Access GEE

To access GEE interface you will want to type in the following URL (or click it to redirect)  **[https://code.earthengine.google.com/](https://code.earthengine.google.com/)**

### 2.3 Code

GEE operates with javascript.

### 2.2 Resources and Tools

GEE offers a number of resources and tools including code for certain tasks. Check out *'Get Started with Earth Engine'*,  **[here](https://developers.google.com/earth-engine/getstarted)**. 

## 3.0 Google Earth Engine to Cloud

### 3.1 Generating Data in EE

Let's look at an example fro GEE.  We will use GEE code from an API example **[here](https://developers.google.com/earth-engine/exporting)**. You can copy and paste from the API site. For now we will go to a saved code page for the example:

https://code.earthengine.google.com/e6ad8ac8a45a2e25c2cf976e0f372cc0

Once we are in the GEE code interface, we will run the code by clicking the run button. 

On the right hand side of the GEE interface there are 3 tabs, Inspector, Console, Tasks. The **Tasks** tab turns orange when we run the code to tell us there is something there that needs our attention.  Click on the **Tasks** tab. Our 'mapToCloudExample' appears here. In order to to actually send the output to the cloud we need to click the run button next to 'mapToCloudExample'. This may take a few minutes.

If it successfully exports to the cloud 'mapToCloudExample' will be highlighted blue and have check mark next to it.

![success_maptocloudexport](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/success_maptocloudexport.JPG)



### 3.2 Cloud

Let's look at the data in the cloud.

![cloud_platform](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/cloud_platform.JPG)

The bucket is where the map tiles from GEE engine appear.

![bucket](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/bucket.JPG)



This is essentially a temporary transfer in order to extract data that is generated in GEE and transfer it to QGIS where we can generated to tiles to use for geovisulaization purposes.



## 4.0 QGIS

QTiles is a plugin for QGIS - it only works with QGIS versions 2.0-2.99 - recommend version 2.18.19 (most stable). QGIS is an open source platform and is freely available. QGIS can be down loaded **[here](https://qgis.org/en/site/forusers/download.html#)**.

Open QGIS. 

### 4.1 QTiles Plugin

Make sure the QTiles plugin is enabled. Click the plugins drop down menu. QTiles should be listed at the bottom. If not then click the 'Manage and install Plugins...' and add QTiles.

### 4.2 Tile Server

We now want to add our bucket from Google Cloud to the Tile Server. To do this open the browser panel in QGIS. Scroll Down to the **'Tile Server'**, right click, and click **'New Connection'**. The following window opens:

![tile server](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/tileserver_newconnection.JPG)

In order to enter the tile layer we will navigate back to our bucket in Google cloud. Open the bucket. We need to open the index.html file, which is the last item in the bucket. Click index.html.

A new tab opens with a map and the tiles generated from GEE. Click on the settings in the upper right (3 vertical dots). Click **'More tools'**. Then click **'Developer tools'**. 

We need to open the source code. To do this make sure the source tab is selected and open the index.html so we can look at the code. 

We want to copy and paste the URL from the var tilePrefix (See Images Below).

![index.html](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/index_code.JPG)

![URL](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/index_code_tileprefix.JPG)



We will need to edit the URL slightly so it looks like this https://storage.googleapis.com/taluccia_gee/mapToCloudExample/{z}/{x}/{y}

![Tile Server URL](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/tileserver_newconnection_URL.JPG)

Then Click OK. The tile server then appears in the Browser Window. 

You can add your tiles by right clicking the tile server, in the example here we would right click the **'eetest'**, and select add layer to add it to our map.

### 4.3 Tile Server to QTiles

Now we need to take out tiles from Google Cloud and generate QTiles. 

It is best if the raster you are working with occupies the extent of the canvas. Zoom in or out as needed

Click the Plugins drop down, hover over QTiles to open the menu and select QTiles. The QTiles screen pops up.  Name the directory where you want to save your QTiles and provide a name for the Tileset. Select Canvas Extent and Zoom levels. In the Parameters make the **'Background transparency'** clear by changing the value to zero and make sure to select **'Write Leaflet-based viewer'**. Click Run.

![QTiles](https://github.com/taluccia/earthengine.cloud.qgis.leaflet/blob/master/images/qtiles_to_leaflet.JPG)



The file directory will contain your QTiles and an HTML document that can be integrated with leaflet. 

Additional help with QTiles can be found **[here](http://felix.rohrba.ch/en/2017/easily-add-tilemap-layers-qgis/)**.



## 4.0 Leaflet

Let's take a look at the leaflet output **[here](earthengine.cloud.qgis.leaflet/assets/eetest.html)**

