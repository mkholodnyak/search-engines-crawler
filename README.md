Node.js - Search Engines Crawler
=====================

This module allows you to search google by scraping the results.
You can add your own search engine.

Installation
------------

    npm install --save search-engines-crawler


Built-in strategies
------------
 -  Google Images


Usage
-------

This prints out the first 20 search results of the query `kitten` in Google Images.

```js

var createCrawler = require('search-engines-crawler');

var googleImagesCrawler = createCrawler('google-images');

googleImagesCrawler.search('kitten', function(err, results){
    results.map(function(result){
        console.log(result);
    });
});
```

Own search engine
-------

You need to implement Search Strategy interface:

 ```js

var GoogleImageStrategy = {
    getSearchURL : function(query){

    },

    getResults : function(html, callback){

    }
};
 ```

Example [Google Images strategy](https://github.com/mkholodnyak/search-engines-crawler/blob/master/strategies/google-images-strategy.js).

License
-------

Licensed under MIT.
