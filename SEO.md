# SEO

Search Engine Optimization <br/>

## SEO Triad

* Code
* Strategy
* Content

## SEM

Search Engine Marketing <br/>

## SERP

Search Engine Results Page <br/>


## SEARCHES

* Search "audifonos" in the Amazon web page
>site:amazon.com audifonos

* Search "audifonos" in the web, except in Amazon
>audifonos -amazon.com

### Black Hat SEO

* Buy links
* Copy/Paste, Tools or Software to create content
* Repeat keywords a lot of times
* Hide text with CSS

### Gray Hat SEO

* Low quality content
* Exact domains

### White Hat SEO

* Meet the Google standards
* 5000 words articles, as a guide
* Structured Data
* Unique content


## TOOLS

* SEMRush Sensor
* MOZCast
* AlgoRoo

## Google Search Console

* INDEXING: Help us to send our pages to Google
* ERRORS: We can find 404 pages or else
* GROWTH: Patterns and tendencies
* MONITORING: By device, country.

Add GSC:

* By prefix: Add code in head tag in our index.html
* By domain: Add code in domain (Namecheap - Domain List - TXT Record)

### Manually index page

Request indexing from Google Search Console <br/>

### SITE Map

* HTML Site: XML-Sitemaps.com


### Robots

__mysite.com/robots.txt__ <br/>

>User-agent: *
>Disallow: /wp-admin/
>Allow: /wp-admin/admin-ajax.php
>Sitemap: https://mysite.com/post-sitemap.xml

### Structured Data

```html
<head>
<script type="application/ld+json">
  {
    "@context":"http://schema.org/"
  }
</script>
</head>
```

* ES IMPORTANTE IR A SEARCH CONSOLE - INSPECCION URL PARA QUE INDEXE LA PAGINA

## REDIRECTION

__301__ PERMANENT <br/>
__302__ TEMPORAL <br/>

Verify protocols in:

https://httpstatus.io/


## AMP

In Main Page:

```html
<link rel="amphtml" href="https://ejemplo.com/url/amp/index.html">
```

In AMP page: <br/>

```html
<link rel="canonical" href="https://ejemplo.com/url/index.html">
```

### PAGE SPEED

Try to be in green. It is the time that takes our site to load. <br/>



### Critical CSS

Include CSS required in the first impression of the user inside the __HEAD__ tag.


## KEYWORDS

* List words
* Someone is looking that word?
* Who appears in the __first results__
* Make an Excel with your list and their __Type of Content__ (Commercial, Informative, Qualifying)
* Let Search Engine show you other "keywords" leaving a __blank space__ in front of the text
* See at the bottom of the Search Page in __"related searches"__
* Click a search and __RETURN__ to the Search Page, _new_ related searches are now activated


### TOOLS for Keyword

* Keyword Tool
* Answer the public
* SemRush
* __KWFinder__
* Soovle
