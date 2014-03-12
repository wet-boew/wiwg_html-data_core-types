# <a id="type-DataSet"></a>DataSet [[schema.org](http://schema.org/Dataset)]

The DataSet type is intended to describe single pools of data.  It's extendable to include encoding, intended audience, geospacial effect and much more.

## Key properties

* publisher -> [Organization](#type-Organization)
* name

## Examples

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
