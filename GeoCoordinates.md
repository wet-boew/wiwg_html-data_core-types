# <a id="type-GeoCoordinates"></a>GeoCoordinates [[schema.org](http://schema.org/GeoCoordinates)]

The GeoCoordinates type is intended to describe a point on or above earth by decimal latitude, longitude and elevation.

## Key Properties

* [latitude](#std-LatLon)
* [longitude](#std-LatLon)

## Examples

Minimum example:
```html
    <span typeof="GeoCoordinates">
        Latitude:<span property="latitude">45.4249</span>
        Longitude:<span property="longitude">75.6999</span>     
    </span>
```
GeoCoordinates expanded to include elevation
```html
    <span typeof="Place">
        <span property="geo" typeof="GeoCoordinates">
            Latitude:<span property="latitude">43.6426</span>
            Longitude:<span property="longitude">-79.3871</span>
            Elevation:<span property="elevation">625.09m</span>
        </span>
    </span>
```
