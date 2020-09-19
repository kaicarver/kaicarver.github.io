# Downloading bears

Well, I had an Azure API key, vut apparently my free account ran out, and I need to pay 25 dollars for a month.

So I'll try some less advanced methods for getting my pictures of bears. Jeremy did say there were methods that break the terms of service of various tools, so I will try to do this discreetly and without causing trouble.

First I do a web search for grizzly images:

https://duckduckgo.com/?q=grizzly+bear&t=brave&iax=images&ia=images

That gives me an infinitely scrolling page of nice grizzly bear pictures. I need 150...

I can download at least the beginning of this 

```bash
curl "https://duckduckgo.com/?q=grizzly+bear&t=brave&iax=images&ia=images" > grizzly_bear.html
```

But that's a big pile of pretty unreadable HTML all in one line. I could try prettifying it and then grepping through it, but...

Time to do some screen-scraping. I haven't done that in a while. I used to do that in Perl, but let's try using the languages I use most these days, Python or Javascript. What are some good tools?

In Python... BeautifulSoup?... or in Javascript/Node... There was also that kibitzr tool I played with recently...

OK I ended up in Javascript with this nice tutorial:

https://www.freecodecamp.org/news/the-ultimate-guide-to-web-scraping-with-node-js-daa2027dcd3/

Stop the presses!

This page lets you test out the Bing API and see results as images, and also get a JSON version. Maybe I can use that.

https://azure.microsoft.com/en-us/services/cognitive-services/bing-image-search-api/

ah but it only returns 35 results per request...

OK so back to using duckduckgo, in a browser to avoid the limited amount returned when using curl, zoom out to 33%, scroll down a bit, should be displaying enough images, then Right-click Inspect, then right click html tag, Copy, Copy outerHTML, then paste that into a file.

OK I have three HTML files, back to parsing them...
