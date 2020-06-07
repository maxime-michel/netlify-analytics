# DIY Analytics

Get simple insights into your website's traffic, and do not pay for them! This 
project bridges the gap between free analytics services:

- :raised_hands: they're free,
- :lock: but offer no control over the data,
- :no_entry: require yet another account,
- :scream_cat: and their UI can be overwhelming;

and paid analytics services:

- :sunglasses: they're generally slick,
- :moneybag: but they're paid,
- :money_with_wings: and, worse than that, the pricing plans tend to not 
account at all for websites that make no or little revenue.

## Installation

Head over to [jsonbox][jsonbox] and copy the temporary box URL that was created 
for you.

Next, use that URL and define `ANALYTICS_URL` in your build's settings.

Now, add the DIY Analytics Netlify plugin to your website, with the following 
in `netlify.toml`:

    [[plugins]]
    package = "diy-analytics"

While in your repository, add the tracking pixel to your pages:

    <img src=".netlify/functions/counter" alt="" style="position:absolute" />

After a build and some visits, you'll now be able to see charts at 
`https://diy-analytics.netlify.app/jsonbox/<YOUR_JSONBOX_ID>`.

## TODO's

- report to Netlify that their [`functions-utils` example][netlify-example] is 
not working
- stop writing to a jsonbox when it's over 5'000 records, as requested in [the 
documentation][jsonbox-doc]
- support more storage options (S3?)

## Credits

This project would not have been possible without:

- [Oliver Jam's initial effort & blog post][blog-post],
- [jsonbox.io][jsonbox],
- and [Netlify's free hosting and computing][netlify].

[jsonbox]:https://jsonbox.io/
[blog-post]:https://oliverjam.es/blog/diy-analytics-netlify-functions/
[netlify]:https://www.netlify.com/
[netlify-example]:https://github.com/netlify/build/tree/master/packages/functions-utils
[jsonbox-doc]:https://github.com/vasanthv/jsonbox#readme
