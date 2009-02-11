MooTools Plugins and Enhancements Repository

### TO DO

* Need to add tests for all libs
* Adjust License information in Localization
* Make the Date Specs pass in all browsers but Firefox
* Decide if reworking the whole source of all plugins makes you an author ( :P )
* Need to rename Browser.Extras to /Native/URI.js

### StyleGuide

* http://wiki.github.com/mootools/mootools-core/syntax-and-coding-style-conventions

### Breaking Changes from More

* Tips
  - options:offsets in Tips renamed to offset

### Breaking Changes from Clientcide

* IframeShim
  - options:zindex renamed to zIndex
  - makeShim method gone
  - occluded property (Element.storage) now camelcase (iframeShim). consistent with tween, morph, etc
* JsonP
  - renamed to Request.JSONP
  - constructor/send/prepareUrl take options hash, no longer an url directly (like Request)
  - user can change options on the fly when calling send() with a new hash, reusing the object
  - added check method. support for link: ignore, cancel, chain (like Request)
  - added success, request and cancel events
  - data can be a hash or string now (like Request)
  - queryString option gone
  - makeUrl logic now moved to new getScript(), which directly returns the script
  - changed how it essentially works. instead of storing the object reference, we store a new function every time a request is made, that keeps a reference of the script element and the object instance.
  - abortAfter and timeout gone. there's now a single timeout for retries and for when retries run out.
  - globalFunction gone, deemed useless