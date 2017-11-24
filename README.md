_Lets draw borders of England using D3, and outline NY meanwhile...._

A lot of articles starts from these words. And next always follows

``The first task for any map is finding geometry.``

And most of normal people could not accomplish this quest. So, then..

# OSME-GEOMETRY
The source for shapes for all the countries and states. 

[![NPM](https://nodei.co/npm/osme-geometry.png?downloads=true&stars=true)](https://nodei.co/npm/osme-geometry/)

# USE
 OSME-geometry contain:
  1. world
  2. world/MicroRegionName (Arfica -> CentralAmerica -> ....)
  3. country as iso3166-1 code (US, GB, DE)
  4. state(region) as iso3166-2 code (AU-NSW, RU-MOW...)
  
# WARNING
 ! 500M ! This repo has size over half gigabyte! But you always use a small and single shape file   

# Import
First step is to get data from `osme-geometry`
## UMD
 You can use unpkg to get access to the datafile.
 
 ```html
 normal quality data
 <script src="https://unpkg.com/osme-geometry/umd/AU.js"></script>
 highter quality data
 <script src="https://unpkg.com/osme-geometry/umd/AU.hd.js"></script>
 low quality data
 <script src="https://unpkg.com/osme-geometry/umd/AU.sd.js"></script>
 
 data without maritime borders (ie with coastline) 
 <script src="https://unpkg.com/osme-geometry/umd/AU.coast.js"></script>
 
 data will be stored in
 window.osmeGeometry['AU']
 ```

## NodeJS
 ```js
   import AUGeometry from 'osme-geometry/AU/geom.js';
// for nodejs you can also specify language  
import AUGeometry from 'osme-geometry/AU/de.geom.js';
import AUGeometry from 'osme-geometry/AU/en.coast.hd.js';
 ``` 
 
# Convert
 Data is stored in [OSME](https://github.com/esosedi/regions) format, similar, but incompatible to TopoJson.
 To use data, you first need to convert it into GeoJSON
 ```js
   osme.geoJson(AUGeometry).then(geoJson => doSomething);
 ```
 You can found different way to display a data in osme repository.
 It is also possible to use `osme` without `osme-geometry`, in that case data will be fetched from backend provided by [esosedi](http://ru.esosedi.org)(http), or [geolocated](https://geolocated.org)(https)
 ```js
 osme.geoJson('AU').then(geoJson => doSomething);
 ```
 
# TopoJSON
 OSME data file is 5-10% bigger than TopoJSON equivalent. It just contain extra information. 
 
# Example
 http://data.esosedi.org/ - project home page.
 https://codesandbox.io/s/koryn1z5no - codesandbox 
 
# Origin of a data 
   - The data included in this document is from www.openstreetmap.org.
   - The data included in this document is from wikipedia.org.
   - The data included in this document is from geonames.org.
   - The data included in this document is from esosedi.org.
   - The data is made available under ODbL and CC-BY-SA    

# Licence
 MIT
