## CHANGES IN VERSION 0.0.2 (2014-02-22)

+ `doi2cit` now parses json response (citeproc-json) into valid Ruby hashes
+ Error handling for DOI resolution added to `doi2cit`
+ Add tests
+ `Cites.getcite()`  has now cache capabilities implemented using `api_cache`
    * Default cache location is at `~/.cites/cache` as defined by class variable `Cites::cache_location`
    * Result are cached using SHA1 hash generated from DOI and content type
    * Because DOIs are supposed to be immutable data in the cache will never expire
    * Cache can be bypassed completely by providing argument `cache=false` to `getcite()`
    * Cache can be flushed (i.e. old cache content removed and replaced with fresh content) providing argument `cache='flush'` to `getcite()`
+ bibtex content is returned as a String by `getcite()`
+ `Cites.search()` now accepts an arbitrary hash of arguments, so that now you can pass in args like `search(:query => 'birds', :year => 2009)` instead of having to put in all args to avoid errors. Default arg values are defined within the function insetad of in the function call.