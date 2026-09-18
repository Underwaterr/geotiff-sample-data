# Example GeoTIFF

This repo contains a GeoTIFF of the [Silas Litle Experimental Forest](https://research.fs.usda.gov/nrs/forestsandranges/locations/silaslittle) in New Jersey.

WGS84 coordinates in WSEN order: `-74.61279 39.90453 -74.58019 39.92963`


## Query 
This file was downloaded from [LandFire](https://www.landfire.gov/) using their public API, [LFPS](https://lfps.usgs.gov/), using this query:
```sh
curl -G https://lfps.usgs.gov/api/job/submit \
  --data-urlencode "Layer_List=LF2020_Elev;LF2020_SlpP;LF2020_Asp;LF2024_FBFM40;LF2024_CC;LF2024_CH;LF2024_CBH;LF2024_CBD" \
  --data-urlencode "Area_of_Interest=-74.61279 39.90453 -74.58019 39.92963" \
  --data-urlencode "Email=<email goes here>"
```

## Layers

| Band | Layer               | LFPS Product    |
| ---  | ------------------- | ----------------|
| 1    | Elevation           | `LF2020_Elev`   |
| 2    | Slope %             | `LF2020_SlpP`   |
| 3    | Azimuth             | `LF2020_Asp`    |
| 4    | Fuel Model[^note]   | `LF2024_FBFM40` |
| 5    | Canopy Cover        | `LF2024_CC`     |
| 6    | Canopy Height       | `LF2024_CH`     |
| 7    | Canopy Base Height  | `LF2024_CBH`    |
| 8    | Canopy Base Density | `LF2024_CBD`    |

[^note]: [2020 Scott and Burgan Fire Behavior Fuel Model](https://www.arcgis.com/home/item.html?id=c2e84935e39c468e92fd2e8bfc0fcf38#overview) 
