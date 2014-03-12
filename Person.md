# <a id="type-Person"></a>Person [[schema.org](http://schema.org/Person)]

The Person type is intended to describe an individual.  It is extendable for biographies, relationships and additional properties as described by schema.org.

## Key properties

* name
* [email](#std-AuthEmail)

## Examples

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
