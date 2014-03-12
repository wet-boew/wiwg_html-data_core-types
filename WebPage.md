# <a id="type-WebPage"></a>WebPage [[schema.org](http://schema.org/WebPage)]

The WebPage type is intended to expose the core elements HTML pages as to uniquely identify it, the freshness(need a better word) of it's content and the top task(s) it applies to.

## Sole properties and additional navigational element

* breadcrumb
* mainContentOfPage
* name
* dateModified
* SiteNavigationElement

## Template
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
