# skippy.net

This theme tries to provide modest support for [microformats2](http://microformats.org/wiki/microformats2), without overloading the source with spans, divs, and classes.

It (currently) defines these unique kinds of content:
* normal posts, which live under the root of the site. Posts have titles and slugs.
* notes, which do not have titles or user-supplied slugs. Currently no top-level navigation is provided for notes, but they are accessible at `<year>/<month>/` URLs off the site root.
* An `archive` type that simply presents a list of all normal posts, in reverse chronological order, grouped by year.
* bookmarks, listed in reverse chronological order.
* favorites, listed in reverse chronological order.

Notes support [photos](https://indieweb.org/photo), [replies](https://indieweb.org/reply) and [reposts](https://indieweb.org/repost), with the original content of the reply or repost stored in the front matter.

The content for all types *other than articles* are stored in Hugo data files. These data files are simply YAML arrays, making it easy to append new elements to the end of them.  Then `note/single.html` template reverses the order of the elements upon page generation, to display them in reverse chronological order (newest first).

Additionally, the `note/single.html` template will attempt to reference a thumbnail for all photos, to ensure that the display is not dominated by a gigantic photo.

This template provides one [shortcode](https://gohugo.io/content-management/shortcodes/): `{{< photo 0 "alt text" >}}`.  If the front matter of a post contains an array of one or more photos, this shortcode will embed an `<img>` tag referencing the specified photo, with optional alt text.

If the front matter contains an array of photos, and the `photo` shortcode **is not** used in the body of the post, then the first photo from the photos array will be prepended to the content of the post.  This provides a "featured image" of sorts.
