# Documents

## Formatting and implementation document

Objects should meet the [GC Semantic Web Implementation Guide](https://github.com/wet-boew/wet-boew/wiki/GC-Semantic-Web-Implementation-Guide).  If an object type does not or can not meet the implementation guide please contact the WIWG to make changes to that guide.

# <a id="l3-CoreTypes"></a>Core types

## Environment
* [WebPage](#type-WebPage)

## Google Rich Snippets
* [Person](#type-Person)
* [Organization](#type-Organization)
* [Place](#type-Place)
* [Event](#type-Event)

## Data
* [DataSet](#type-DataSet)
* [DataCatalog](#type-DataCatalog)

## Support
* [PostalAddress](#type-PostalAddress)
* [GeoCoordinates](#type-GeoCoordinates)

# <a id="l3-CoreTypes-description"></a>Core types descriptions

## <a id="type-WebPage"></a>WebPage [[schema.org](http://schema.org/WebPage)]

The WebPage type is intended to expose the core elements HTML pages as to uniquely identify it, the freshness(need a better word) of it's content and the top task(s) it applies to.

### Sole properties and additional navigational element

* breadcrumb
* mainContentOfPage
* name
* dateModified
* SiteNavigationElement

### Template
```html
    <!DOCTYPE html>
    <html>
        <head>
            <title>Title of the page</title>
        </head>
        <body vocab="http://schema.org/" typeof="WebPage">
            
            <span property="breadcrumb">
                breadcrumb
                <!-- breadcrumb elements -->
            </span>

            <div property="mainContentOfPage">
                <h1 property="name">Name of document</h1>

                mainContentOfPage
                <!-- main content -->
            </div>

            <nav typeof="SiteNavigationElement">
                Navigation 
                <!-- navigational elements -->
            </nav>

            Date modified: <time property="dateModified" datetime="2013-07-01T00:00:01+00:00">2013-07-01</time>

        </body>
    </html>
```

## <a id="type-PostalAddress"></a>PostalAddress [[schema.org](http://schema.org/PostalAddress)]

The PostalAddress type is intended to encapsulate a postal address as defined by Canada Post.

### Key properties

For street address:

* [streetAddress](#std-CPAG)
* [addressLocality](#std-CPAG)
* [addressRegion](#std-CPAG)
* [addressCountry](#std-CPIDL)

OR 

For post office box:

* [postOfficeBoxNumber](#std-CPAG)
* [addressLocality](#std-CPAG)
* [addressRegion](#std-CPAG)
* [addressCountry](#std-CPIDL)

### Examples

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
## <a id="type-Person"></a>Person [[schema.org](http://schema.org/Person)]

The Person type is intended to describe an individual.  It is extendable for biographies, relationships and additional properties as described by schema.org.

### Key properties

* name
* [email](#std-AuthEmail)

### Examples

Minimum contact:
```html
    <p typeof="Person">
        <span property="name">John D. Doe</span>
        <a href="mailto:John.Doe@parl.gc.ca"><span property="email">John.Doe@parl.gc.ca</span></a>
    </p>
```

General contact sheet:
```html
    <p typeof="Person">
        <meta property="name" content="John D. Doe"/>

        <span property="givenName">John</span> <span property="additional">D</span> <span property="familyName">Doe</span>
        <span property="jobTitle">Manager</span>
     
        <span property="location" typeof="Place">
            <span property="address" typeof="PostalAddress">
                <span property="streetAddress">240, Sparks Street</span>,
                <span property="addressLocality">Ottawa</span>, 
                <span property="addressRegion">ON</span>,
                <span property="addressCountry">CANADA</span>
                <span property="postalCode">K1A 0G6</span>
            </span>
        </span>

        <span property="telephone">(888) 123-4567</span><br>
        <a href="mailto:John.Doe@parl.gc.ca"><span property="email">John.Doe@parl.gc.ca</span></a>
    </p>
```

"Care Of" minimal where email not availalbe:
```html
John Doe, Director Generals Office c/o
    <p typeof="Person">
        Health Canada - General Information
        <meta property="name" content="Deptartment-name Info / Info Nom-de-Deptartement">
        <a href="mailto: Info@dept-dept.ca"><span property="email">Info@dept-dept.ca</span></a>
    </p>
```

"Care Of" where email not availalbe:
```html
John Doe, Director Generals Office c/o
    <p typeof="Person">
        Deptartment-name - General Information
        <meta property="name" content="Health Canada Info / Info Santé Canada">
        <span property="location" typeof="Place">
            <span property="address" typeof="PostalAddress">
                <span property="streetAddress">240, Sparks Street</span>,
                <span property="addressLocality">Ottawa</span>, 
                <span property="addressRegion">ON</span>,
                <span property="addressCountry">CANADA</span>
                <span property="postalCode">K1A 0G6</span>
            </span>
        </span>

        Toll-free ( Canada ): <span property="telephone">(866) 123-4567</span><br>
        Telephone :  <span property="telephone">(613) 123-4567</span><br>
        TTY: <span property="telephone">(800) 123-4567</span><br>
        <a href="mailto: Info@dept-dept.ca"><span property="email">Info@dept-dept.ca</span></a>
    </p>
```

## <a id="type-Organization"></a>Organization [[schema.org](http://schema.org/Organization)]

The Organization type is intended to describe an organization and may be extended to describe architectures.

### Key properties

* [legalName](#std-AuthLegalName)

### Examples

Minimum organization description:
```html
    <p typeof="Organization">
        <span property="legalName">Parliament of Canada - Parlement du Canada</span>
    </p>
```
Expanded organization description:
```html
    <p typeof="Organization">
        <span property="legalName">Parliament of Canada - Parlement du Canada</span>
     
        <span property="location" typeof="Place">
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

    </p>
```
## <a id="type-Place"></a>Place [[schema.org](http://schema.org/Place)]

The Place type is intended to describe a place or venu.  It is extendable to anything from a small office to a conference center with multiple simultanious events.

### Key properties

* address -> [PostalAddress](#type-PostalAddress)

OR

* geo -> [GeoCoordinates](#type-GeoCoordinates)

### Examples

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

## <a id="type-Event"></a>Event [[schema.org](http://schema.org/Event)]

The Event type is intended to describe an evnet.  It is extendable from meetings with attendees to large scale events with performers. 

### Key properties

* name
* [startDate](#std-ISO8601)
* Location -> [Place](#type-Place) or [PostalAddress](#type-PostalAddress)

### Examples

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

## <a id="type-DataSet"></a>DataSet [[schema.org](http://schema.org/Dataset)]

The DataSet type is intended to describe single pools of data.  It's extendable to include encoding, intended audience, geospacial effect and much more.

### Key properties

* publisher -> [Organization](#type-Organization)
* name

### Examples

Minimum dataset:
```html
    <span typeof="DataSet">

        <span property="publisher" typeof="Organization">
            <span property="legalName">Parliament of Canada - Parlement du Canada</span>
        </span>
        <span property="name">Mean visitors attendance by hour</span>
    </span>
```

Extended dataset to include date modified:
```html
    <span typeof="DataSet">
        <span property="publisher" typeof="Organization">
            <span property="legalName">Parliament of Canada - Parlement du Canada</span>
        </span>
        <span property="name">Mean visitors attendance by hour</span>

        Date modified: <time property="dateModified" datetime="2013-07-01T00:00:01+00:00">2013-07-01 00:00:01</time>
    </span>
```

## <a id="type-DataCatalog"></a>DataCatalog [[schema.org](http://schema.org/DataCatalog)]

The DataCatalogue type is intended to describe collections of DataSets.

### Key Properties

* publisher -> [Organization](#type-Organization)
* name

### Examples

Minimum example:
```html
    <span typeof="DataCatalog">

        <span property="publisher" typeof="Organization">
            <span property="legalName">Parliament of Canada - Parlement du Canada</span>
        </span>
        <span property="name">Visitor data</span>

    </span>
```

Extended datacatalog to include datasets, contact information and a modification date:
```html
    <span typeof="DataCatalog">

        <span property="publisher" typeof="Organization">
            <span property="legalName">Parliament of Canada - Parlement du Canada</span>
        </span>
        <span property="name">Visitor data</span>


        <span typeof="DataSet">

            <span property="publisher" typeof="Organization">
                <span property="legalName">Parliament of Canada - Parlement du Canada</span>
            </span>
            <span property="name">Mean visitors attendance by hour</span>

        </span>

        <span typeof="DataSet">

            <span property="publisher" typeof="Organization">
                <span property="legalName">Parliament of Canada - Parlement du Canada</span>
            </span>
            <span property="name">Average visitors attendance by hour</span>

        </span>

        <span typeof="DataSet">

            <span property="publisher" typeof="Organization">
                <span property="legalName">Parliament of Canada - Parlement du Canada</span>
            </span>
            <span property="name">Maximum visitors attendance by hour</span>

        </span>

        <span typeof="DataSet">

            <span property="publisher" typeof="Organization">
                <span property="legalName">Parliament of Canada - Parlement du Canada</span>
            </span>
            <span property="name">Minimum visitors attendance by hour</span>

        </span>

        Date modified: <time property="dateModified" datetime="2013-07-01T00:00:01+00:00">2013-07-01 00:00:01</time>

        Toll-free ( Canada ): <span property="telephone">(866) 599-4999</span><br>
        Telephone :  <span property="telephone">(613) 992-4793</span><br>
        TTY: <span property="telephone">(613) 995-2266</span><br>
        <a href="mailto:info@parl.gc.ca"><span property="email">info@parl.gc.ca</span></a>

    </span>
```

## <a id="type-GeoCoordinates"></a>GeoCoordinates [[schema.org](http://schema.org/GeoCoordinates)]

The GeoCoordinates type is intended to describe a point on or above earth by decimal latitude, longitude and elevation.

### Key Properties

* [latitude](#std-LatLon)
* [longitude](#std-LatLon)

### Examples

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

# Key property definitions

Undefined as of yet

## <a id="l2-PropertyStd"></a>Property standards

### <a id="std-CPAG"></a>Canada Post Addressing Guidelines
* http://www.canadapost.ca/tools/pg/manual/pgaddress-e.asp

### <a id="std-CPIDL"></a>Canada Post International Desitination Listing
* http://www.canadapost.ca/tools/pg/manual/PGintdest-e.asp

### <a id="std-AuthEmail"></a>Authoritative email

It would be preferable to have a central authority defining the email address but the [Government Electronic Directory Service ( GEDS )](http://sage-geds.tpsgc-pwgsc.gc.ca/cgi-bin/direct500/eng/TE?FN=index.htm) does not consistently expose email.

Until an authoritative source exists, implementers should ensure any email addresses are fully qualified.

### <a id="std-AuthLegalName"></a>Authoritative legalName

Undefined

### <a id="std-ISO8601"></a>ISO8601 date, time or duration

#### Datetime

A Treasury Board mandated ISO8601 date time such as 2012-12-07T15:00:00-04:00 representing December 7th 2012 at 15:00:00 with a time zone definition of -4 GMT ( EST ).  If the timezone is not specified, assume it's local time.

#### Date

A Treasury Board mandated ISO8601 date such as 2012-12-07 representing December 7th 2012.

#### Time

A Treasury Board mandated ISO8601 time such as 15:00:00-04:00 representing 15:00:00 with a time zone definition of -4 GMT ( EST ).  If the timezone is not specified, assume it's local time.

#### Duration

A Treasury Board mandated (ISO8601 duration)(http://en.wikipedia.org/wiki/ISO_8601#Durations) such as PT3H30M which describes 3 hours and 30 minutes.

#### Date time policies

* Treasury Board policy : http://www.tbs-sct.gc.ca/pol/doc-eng.aspx?id=18909&section=text#sec9.4
* W3C date time definition : http://www.w3.org/TR/NOTE-datetime
* ISO8601 date time with time zone or local time will be assumed:
    * http://en.wikipedia.org/wiki/ISO_8601
    * http://en.wikipedia.org/wiki/ISO_8601#Time_zone_designators
    * http://en.wikipedia.org/wiki/ISO_8601#Durations

### <a id="std-LatLon"></a> Latitude, Longitude and Elevation

Latutude and Longitude are to be described, were possible, as decimal values.

Till there is clarification on elevation standards the unit is to be added in as data adjacent to the numerical value 1234m or 1.2km.

## <a id="l2-FullPageSamp"></a>Full page samples 

Implementation rolling out, examples will follow as WET advances.

* TBS WIWG - HTML Data core implemented in WET 4.0
* TBS MEWG T2 - Developing strategy for standards, potential replacement for Dublin Core

## <a id="l2-Tools"></a>Tools

### Code validator
* http://validator.w3.org/nu/

### Data visibility
* https://www.google.com/webmasters/tools/richsnippets
* http://linter.structured-data.org/

## Known issues

* Care Of examples would be better described as Organization if organization had a contact point
