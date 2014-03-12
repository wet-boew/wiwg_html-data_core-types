# Place [[schema.org](http://schema.org/Place)]

The Place type is intended to describe a place or venu.  It is extendable to anything from a small office to a conference center with multiple simultanious events.

## Key properties

* address -> [PostalAddress](PostalAddress.md)

OR

* geo -> [GeoCoordinates](GeoCoordinates.md)

## Examples

Minimum place address:
```html
    <span typeof="Place">
        <span property="address" typeof="PostalAddress">
            <span property="streetAddress">Parliament of Canada</span>,
            <span property="addressLocality">Ottawa</span>, 
            <span property="addressRegion">ON</span>,
            <span property="addressCountry">CANADA</span>
            <span property="postalCode">K1A 0A9</span>
        </span>
    </span>
```
Minimum place GeoCoordinates:
```html
    <span typeof="Place">
        <span property="geo" typeof="GeoCoordinates">
            Latitude:<span property="latitude">45.4249</span>
            Longitude:<span property="longitude">75.6999</span>
        </span>
    </span>
```

Extended place example:
```html
    <span typeof="Place">
        <span property="address" typeof="PostalAddress">
            <span property="streetAddress">Parliament of Canada</span>,
            <span property="addressLocality">Ottawa</span>, 
            <span property="addressRegion">ON</span>,
            <span property="addressCountry">CANADA</span>
            <span property="postalCode">K1A 0A9</span>
        </span><br>

        Toll-free ( Canada ): <span property="telephone">(866) 599-4999</span><br>
        Telephone :  <span property="telephone">(613) 992-4793</span><br>
        TTY: <span property="telephone">(613) 995-2266</span><br>
        <a href="mailto:info@parl.gc.ca"><span property="email">info@parl.gc.ca</span></a>      
    </span>
```
