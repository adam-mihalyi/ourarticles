# ourarticles.js
This is a JavaScript widget to display a list of articles associated with a
group of arXiv author ids, sorted by the date they were published. This code is
based on the arXiv myarticles widget:
https://arxiv.org/help/myarticles .

## Prerequisites

Just like the original myarticles widget, this widget also relies on an empty
HTML tag with the id of **arxivfeed**. For example:
```html
<div id="arxivfeed"></div>
```
For sorting and displaying dates the script uses **Moment.js**, so this has to be
included.

After displaying the data, the script calls **MathJax** on the new content. If
you don't need LaTeX notation to be displayed as mathematical notation, just
remove that line.  Otherwise you will need to have MathJax on your site.

## Alternatives

If you have access to the server side code of your website (Python, PHP...
etc.), it is probably better to use arXiv's json feed instead of the padded
jsonp. Then the results can be processed and stored on the server, and you
won't need to make new requests to arXiv at every single page load. This would
also improve the loading time of your page significantly.

I have experimented with caching the results in the browser using localStorage,
and this is fairly straightforward except for error handling (all its functions
can throw errors, not only the setItem), and I still think that could work, but
I haven't finished this because of some unrelated issues (I would have had to
deal with two instances of the same script on the same page).

## License

License was kept the same as for arXiv's myarticles.js: GNU GPL v3 (or later).

