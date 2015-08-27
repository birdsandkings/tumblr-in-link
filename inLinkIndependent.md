# In-Link Independent #

The release of the latest Tumblr API also allowed me to create a different version of the In-Link Widget that can be used to display related Tumblr content also on non-tumblr sites, or it can also help displaying related content from another Tumblr site.

The trick is easy, this special script allows you to specify as an option also a URL, thus allowing you to specify to which Tumblr blog you want the related contents be pulled from.

**Warning**: there’s one limitation, you can’t use both the actual In-Link widget and the In-Link Independent on the same page. The two scripts would collide, as they work on the same divs.

# Instructions #

To use In-Link Independent simply copy the following code on your page:

```
<!— Start In-Link Independent Widget —>
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.5.0/jquery.min.js"></script>
<script src="http://tumblr-in-link.googlecode.com/svn/branches/Version 2.0/js/in-link-badge.js?url<URL>&num=5&len=60&css=dark&title=Some Related Posts&tags=<TAGS>," type="text/javascript"></script>
<!— End In-Link Independent widget —> `
```
The two options that need to be pulled together are:

  * **url**: simply add the url (without the http://) of the tumblr you’d like to pull the infos for.
  * **tags**: add the tag or tags (in case separated by a comma “,”) you would like to extract.

All other options work the same as in the [In-Link Widget](install.md).

So here’s an example I am currently using on blogger. Here’s the code:

```
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.5.0/jquery.min.js"></script>
<script src="http://tumblr-in-link.googlecode.com/svn/branches/Version 2.0/js/in-link-badge.js?url=eclettichevisioni.com&num=200&len=40&css=shadow&size=250&title=The Image Gallery&tags=Nico Tortorella," type="text/javascript"></script>`
```
and here’s the result:

![http://media.tumblr.com/tumblr_lt2edlvC0Q1qzz9h9.png](http://media.tumblr.com/tumblr_lt2edlvC0Q1qzz9h9.png)

# Expert Usage #

If you’re using a CMS (e.g. wordpress, blogger or something similar) there’s a good possibility that you could embed the code above into your template. You would probably need to customize just the TAGS part.

For example in Wordpress you could use the [get\_the\_tags](http://codex.wordpress.org/Function_Reference/get_the_tags) function to get the tags automatically and fill the javascript option automatically. What is important is that you list tags as plain text, comma separated.