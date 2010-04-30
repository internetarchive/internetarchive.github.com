---
layout: post
title: New BookReader Preview API
categories:
- bookreader
- api
---

Internet Archive Texts
======================

The Internet Archive hosts more than 2 million public domain items in its
[Texts Collection](http://www.archive.org/texts). Each of these books has a unique
archive.org identifier. Once you know this identifier, you can programaticlaly 
request a preview image using a url such as:

<code>
http://www.archive.org/download/itemid/itemid.gif
</code>

For example, for the [The Bird Book](http://www.archive.org/details/birdbookillustra00reedrich),
we can request a preview image using this url:

<code>
http://www.archive.org/download/birdbookillustra00reedrich/birdbookillustra00reedrich.gif
</code>

This url requests the beautiful blinky animated gif below:

<img src="http://www.archive.org/download/birdbookillustra00reedrich/birdbookillustra00reedrich.gif"/>

(in firefox you can hit the escape key to stop the incessant blinking!)

New BookReader Preview API
==========================
Many of our partners have requested a modern preview API that generates a large, static image,
so we have added one to our [open source BookReader](http://github.com/openlibrary/bookreader).

The new preview API looks like this:

<code>
http://www.archive.org/download/{itemid}/page/{itemid}_(cover|title|preview).jpg
</code>

You can use this URL to generate a large cover or title page image, in jpeg format.
If you request a preview image, you will get you get the title page if it marked
in the book metadata. If not, you will get the cover image. If neither are marked
in the metadata, then you will get the first page.

For The Bird Book, we can request a preview image using this URL:

<code>
http://www.archive.org/download/birdbookillustra00reedrich/page/birdbookillustra00reedrich_preview.jpg
</code>

The preview API genreates this large image, which you can use in your applications:

<img src="http://www.archive.org/download/birdbookillustra00reedrich/page/birdbookillustra00reedrich_preview.jpg"/>

