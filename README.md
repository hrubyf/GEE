#  Google Earth Engine (GEE)
## Video 1
a) Seleccionar una imagen especifica de Sentinel
```
var sentinel2 = ee.Image("COPERNICUS/S2/20191217T182751_20191217T183434_T11SNR");
```
b) Ver los detalles de la imagen en la consola
```
print(sentinel2)
```
c) Visualizar la imagen en el mapa
```
Map.addLayer(sentinel2, {bands:["B4","B3","B2"], min:0, max:3000}, "Ensenada - true color");
```
## Video 2
var image = ee.Image(sentinel2
.filterDate("2019-12-01", "2019-12-31")
.filterBounds(ensenada)
.sort("CLOUD_COVERAGE_ASSESSMENT")
.first()
);
