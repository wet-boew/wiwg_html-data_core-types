# Event [[schema.org](http://schema.org/Event)]

The Event type is intended to describe an evnet.  It is extendable from meetings with attendees to large scale events with performers. 

## Key properties

* name
* startDate
* Location -> [Place](Place.md) or [PostalAddress](PostalAddress.md)

## Examples

Minimum Event example:
```html
    <span typeof="Event">
        <span property="name">Citizenship Ceremony</span>
        Location: 
        <span property="location" typeof="Place">
            <span property="description">Corner Brook, Newfoundland & Labrador City Hall</span><br>
            <span property="address" typeof="PostalAddress">
                <span property="streetAddress">5, Park Street</span>,<br>
                <span property="addressLocality">Corner Brook</span>,<br>
                <span property="addressRegion">Newfoundland and Labrador</span><br>
            </span>
        </span><br>

        <time property="startDate" datetime="2012-12-07T15:00:00-04:00">
            Date: 2013-06-07 EST<br>
            Time: 3:00 p.m.<br>
        </time>
    </span>
```

Event with duration:
```html
    <span typeof="Event">
        <span property="name">Citizenship Ceremony</span>
        Location: 
        <span property="location" typeof="Place">
            <span property="description">Corner Brook, Newfoundland & Labrador City Hall</span><br>
            <span property="address" typeof="PostalAddress">
                <span property="streetAddress">5, Park Street</span>,<br>
                <span property="addressLocality">Corner Brook</span>,<br>
                <span property="addressRegion">Newfoundland and Labrador</span><br>
            </span>
        </span><br>

        <time property="startDate" datetime="2012-12-07T15:00:00-04:00">
            Date: 2013-06-07 EST<br>
            Time: 3:00 p.m.<br>
        </time>

        Duration:<time property="duration" datetime="PT3H00M">3h</time><br>
    </span>
```
