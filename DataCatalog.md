# DataCatalog [[schema.org](http://schema.org/DataCatalog)]

The DataCatalogue type is intended to describe collections of DataSets.

## Key Properties

* publisher -> [Organization](Organization.md)
* name

## Examples

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
