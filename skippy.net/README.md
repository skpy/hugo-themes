# skippy.net

This theme tries to provide modest support for [microformats2](http://microformats.org/wiki/microformats2), without overloading the source with spans, divs, and classes.

It (currently) defines three unique kinds of content:
* normal posts, which live under the root of the site. Posts have titles and slugs.
* notes, which live under the `/note/` section. Notes do not have titles or user-supplied slugs. The Hugo list template create navigation for notes by year, month, and day.
* An archive.  The `archive` type simply presents a list of all normal posts, in reverse chronological order, grouped by year.

This template provides one [shortcode](https://gohugo.io/content-management/shortcodes/): `{{< photo 0 "alt text" >}}`.  If the front matter of a post contains an array of one or more photos, this shortcode will embed an `<img>` tag referencing the specified photo, with optional alt text.

If the front matter contains an array of photos, and the `photo` shortcode **is not** used in the body of the post, then the first photo from the photos array will be prepended to the content of the post.  This provides a "featured image" of sorts.

The first photo of the photo array will also be used for the Twitter card image, if present.  If no photo array is present, then the `twitterimage` defined in the site configuration file will be used for the Twitter card.
