# PostalAddress [[schema.org](http://schema.org/PostalAddress)]

The PostalAddress type is intended to encapsulate a postal address as defined by Canada Post.

## Key properties

For street address:

* streetAddress
* addressLocality
* addressRegion
* addressCountry

OR 

For post office box:

* postOfficeBoxNumber
* addressLocality
* addressRegion
* addressCountry

## Examples

Street address:
```html
    <span typeof="PostalAddress">
        <span property="streetAddress">240, Sparks Street</span>,
        <span property="addressLocality">Ottawa</span>, 
        <span property="addressRegion">ON</span>,
        <span property="addressCountry">CANADA</span>
        <span property="postalCode">K1A 0G6</span>
    </span>
```
Rural route:
```html
    <span typeof="PostalAddress">
        <span property="streetAddress">RR 6 STN Main</span>,
        <span property="addressLocality">Millarville</span>, 
        <span property="addressRegion">AB</span>,
        <span property="addressCountry">CANADA</span>
        <span property="postalCode">T0L 1K0</span>
    </span>
```
Post office box:
```html
    <span typeof="PostalAddress">
        <span property="postOfficeBoxNumber">PO BOX 4001 STN A</span>,
        <span property="addressLocality">Ottawa</span>, 
        <span property="addressRegion">ON</span>, 
        <span property="addressCountry">CANADA</span>
        <span property="postalCode">V8X 3X4</span>
    </span>
```
