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

### 1.3 Access GEE

To access GEE interface you will want to type in the following URL (or click it to redirect)  **[https://code.earthengine.google.com/](https://code.earthengine.google.com/)**

### 1.4 Resources and Tools

GEE offers a number of resources and tools including code for certain tasks. Check out *'Get Started with Earth Engine'*,  **[here](https://developers.google.com/earth-engine/getstarted)**. 

### 1.5 Google Cloud Platform Access Create an Account / Log-in

This should be the same account that you are using with GEE.

### 1.6 Redeem Education Grant

If you have not redeemed your education grant, click **[here](https://google.secure.force.com/GCPEDU/?cid=d0GOdFV%2BTF1xdIizooBa1z8ehdyk91t3C51Dsuzk3BOlTJYPq0BfaE4gxD7ysKNK/)**. Use your OSU email to redeem the coupon. Make sure you are logged into the Cloud Platform with the same log-in as GEE. Then follow the instructions  **[here](https://console.cloud.google.com/education)** to redeem the coupon.

## 2.0 Google Earth Engine to Cloud

### 2.1 Generating Data in EE

Code in EE relies on javascript. 

Let's look at an example. We will calculate NDVI for a landsat image with a known fire scar, and then export to a bucket in the cloud...

link to code:

Code runs in the console 

The **Task** tab will light up in orange; click the tab. You will need click the run button to export the 'ndvi_test' to the cloud here. This may take a few minutes.





## 3.0 QGIS

### 3.1 Tiles to QTiles

QTiles is a plugin for QGIS - it only works with QGIS versions 2.0-2.99 - recommend version 2.18.19 (most stable...include link to QGIS https://qgis.org/en/site/forusers/download.html#)



Help with tiles

http://felix.rohrba.ch/en/2017/easily-add-tilemap-layers-qgis/

## 4.0 Integrate QTiles into Leaflet



