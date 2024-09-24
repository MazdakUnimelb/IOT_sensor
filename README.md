<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Cesium Globe - University of Melbourne</title>
    <script src="https://cesium.com/downloads/cesiumjs/releases/1.82/Build/Cesium/Cesium.js"></script>
    <link
      href="https://cesium.com/downloads/cesiumjs/releases/1.82/Build/Cesium/Widgets/widgets.css"
      rel="stylesheet"
    />
    <style>
      #cesiumContainer {
        width: 100%;
        height: 100vh;
        margin: 0;
        padding: 0;
        display: block;
      }
    </style>
  </head>
  <body>
    <div id="cesiumContainer"></div>
    <script>
      // Your Cesium Ion token
      Cesium.Ion.defaultAccessToken =
        "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiIxMDBiYzVlYi00MDY5LTRiYjAtYTJkMy1hYjkxMzJkZWJlZmYiLCJpZCI6MTYxOTQ0LCJpYXQiOjE3MDY1ODQyNjJ9.kHKvDPN-JdmLQbDyBypQzbx158YsMmbNwCwdVTA0mJI";

      // Initialize the Cesium Viewer
      const viewer = new Cesium.Viewer("cesiumContainer", {
        terrainProvider: Cesium.createWorldTerrain(),
      });

      // Fly to University of Melbourne, Parkville Campus (Coordinates)
      viewer.camera.flyTo({
        destination: Cesium.Cartesian3.fromDegrees(144.9631, -37.7963, 500), // Longitude, Latitude, Height
        orientation: {
          heading: Cesium.Math.toRadians(0.0), // face north
          pitch: Cesium.Math.toRadians(-30.0), // looking down
          roll: 0.0,
        },
        duration: 3, // Fly to location in 3 seconds
      });
    </script>
  </body>
</html>
