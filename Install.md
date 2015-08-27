

# Introduction #

Welcome to **In-Link**, a widget that helps you display a “Related Posts” area beneath your individual posts, with a very easy to use yet customizable format.

Tumblr is a great platform, but it doesn’t have (yet) the functionality to display related items on your page, something very useful for the usability of your Tumblr-Blog.

Recently I had discovered a widget which was doing more or less this process, but I wanted to have something more, so I already customized that project for my usage.

But I’ve expanded its functionalities and releasing it for your usage.

It is still be considered in beta test, so please report any issues you may find.

The project is also hosted on Google Code where more technical information are available.

# New version 2.0 released #

Following the availability of the new [version 2.0](http://www.tumblr.com/docs/en/api/v2) of the Tumblr API I’ve recoded the In-Link widget, including a couple of new interesting features:

  * The widget now pulls several more images for display: particularly the first image of a photoset, the first image included in the body of a text post, the album cover (if existing) of an audio piece. It also gives the opportunity to set a specific placeholder image for empty posts.
  * It also includes a new css.
  * It includes the possibility to choose the size of the images displayed.


# Details #

In order to install this widget, you need to be able to access the HTML of your theme. If you don’t have enough HTML knowledge, or you don’t want to mess up your theme, please don’t go any further.

Otherwise here are the instructions. Access your Theme, and find the following lines of code. These can go anywhere you want within the `{block:Posts} … {/blockPosts}` tags.

```
{block:Permalink}
	{block:HasTags}
		<!— Start In-Link widget —>
                <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.5.0/jquery.min.js"></script>
		<script src="http://tumblr-in-link.googlecode.com/svn/trunk/js/tumblr-in-link.1.0.js?num=5&len=60&css=dark&title=Some Related Posts&tags={block:Tags}{Tag},{/block:Tags}" type="text/javascript"></script>
		<!— End In-Link widget —> 
	{/block:HasTags} 
{/block:Permalink}
```

Wrapping the widget code into the `{block:HasTags} … {/blockHasTags}` tags will ensure the widget is displayed only for posts that have tags.

**Difference installation for Version 2.0.** As of the availability of Version 2.0 installation instructions are similar, you only have to change the script URL which is:

```
http://tumblr-in-link.googlecode.com/svn/branches/Version 2.0/js/tumblr-in-link.2.0.js?num=5&len=60&css=dark&title=Some Related Posts&tags={block:Tags}{Tag},{/block:Tags}
```

All the rest of the coding is the same.

**Please note**: if you’ve already the jQuery code used somewhere else in the theme, you may not need to add the reference to that code. But this plugin requires at least jQuery version 1.5.0.


# Options #

You can implement many different options by simply using the JavaScript variables appended in the Widget string. How? Simply change the values that are available in this string:

`http://tumblr-in-link.googlecode.com/svn/trunk/js/tumblr-in-link.1.0.js?num=5&len=60&css=dark&title=Some Related Posts&tags={block:Tags}{Tag},{/block:Tags}`

Here the various options:

  * **num** indicate the number of items you would like to see displayed. If undefined standard is 8. If you want to display images, I suggest you use a value between 3 and 5, depending on your template width. For example **num=5**.
  * **len** indicates the maximum length of your text links. Default is 60. This means that if a link description is longer, the widget will cut it to 60 characters and add three dots at the end [“…”]. For example **len=40**.
  * **css** indicates the CSS file to be used for display. There four possible variants which I will explain later in this post. For example: css=dark.
  * **title** indicated the Title of your “In-Link Widget”.  Default is “Related Posts:”. This way you can choose also your own language. For example: title=Some Related Posts.
  * **type** add a specific type if you want to display only related posts of a specific type. Valid values are all Tumblr post options, i.e. text, quote, audio, photo, video, link, answer. For example: type=photo.
  * **NEW FOR VERSION 2.0**: **size** specify the size of the images you want to display as thumbnails: possible values are 75 (will display a 75x75 square thumbnail) 100 and 250. Default is 100. For example size=100.
  * **NEW FOR VERSION 2.0**: **imageurl** specify a URL pointing to an image that will be used as a placeholder in case no image is available.

  * **Remember to connect** all options with an “&” and leave the tags option at the end, the way it is written. **Also please use only the options that are relevant for the version you’re using**.

