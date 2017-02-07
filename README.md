# Download XML from client

## Approach

The goal is to convert data in the client to a downloadable CSV file with the easiest possible implementation. In a perfect world, that would mean that we wouldn’t need to write any back-end code to interface with our UI. The way browsers usually handle file creation is via data URIs. The approach is to first write a method that flattens our data/object into a csv friendly format, append the appropriate data-type declarations, and add the URI to a link element.

## Test code
https://github.com/gjudki/csv-dl-test

## Browser support

This works just fine... pretty much everywhere but IE. IE only supports data URIs in JS and CSS, not HTML (as a link for example). I was hoping to get around that by navigating to the URI directly with JS, but so far, i haven't been able to get that to work. If IE is important to us (and I think it is), then there a number of JS libraries that assist with this kind of thing:
- Downloadify: https://github.com/dcneiner/Downloadify
- download.js: http://danml.com/download.html

Info about Data URIs:

https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs

## Conclusion

Once again, IE has quickly and quietly put to rest any hopes I might have of writing helpful and simple client-side code. I am open to trying out one of the above JS libraries to make it work, but in an application where dependencies are strictly scrutinized, this might be a hard sell. For a cross-browser solution that works a bit more reliably, it would be worth looking into creating an API that creates, stores, and links to files.
