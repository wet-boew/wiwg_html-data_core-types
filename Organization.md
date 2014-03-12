# <a id="type-Organization"></a>Organization [[schema.org](http://schema.org/Organization)]

The Organization type is intended to describe an organization and may be extended to describe architectures.

## Key properties

* [legalName](#std-AuthLegalName)

## Examples

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
