# Introduction #

With these very simple instructions you can “copy and paste” the code necessary to implement the In-Link Widget into your theme, giving the end user full control on the widget functionalities simply through the Appearance menu.


# Theme Setup #

1) **Include the jQuery 1.5 code into your Theme**, by adding the following lines of code.

```
<script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.5.0/jquery.min.js"></script>
<script type="text/javascript">
```

If you’re already using another jQuery Plugin you will probably be able to simply substitute that line of code. The In-Link Widget uses the jQuery.noConflict() instruction to avoid issues with other widgets/plugins as well as other framework, such as MooTools.

2) **Add the following Options to your Theme**, by adding the following lines of code.
```
        <!-- In-Link Options -->
	<meta name="if:Show InLink Widget" content="1" />
	<meta name="text:InLink Post Number" content="5" />
	<meta name="text:InLink Post Length" content="60" />
	<meta name="text:InLink Style" content="complete" />
	<meta name="text:InLink Widget Title" content="Related Posts" />
```
If you want to style the widget using your stylesheet, you can simply skip one of the “style” option, and use the [Empty Style Instructions](CSSEmpty.md).

This way the user will have some more options into its Appearance menu, as follows:

![http://media.tumblr.com/tumblr_lkkr01lH1j1qzz9h9.png](http://media.tumblr.com/tumblr_lkkr01lH1j1qzz9h9.png)

3) **Add the following block into your theme**, in the position you would like the InLink Widget to Appear.

```
<!— Start InLink widget —>
{block:IfShowInLinkWidget}
	{block:Permalink}
		{block:HasTags}
		<script src=”http://tumblr-in-link.googlecode.com/svn/trunk/js/tumblr-in-link.1.0.js?{block:IfInLinkPostNumber}num={text:InLink Post Number}&{/block:IfInLinkPostNumber}{block:IfInLinkPostLength}len={text:InLink Post Length}&{/block:IfInLinkPostLength}{block:IfInLinkStyle}css={text:InLink Style}&{/block:IfInLinkStyle}{block:IfInLinkTitle}title={text:InLink Widget Title}&{/block:IfInLinkTitle}tags={block:Tags}{Tag},{/block:Tags}” type=”text/javascript”></script>
		{/block:HasTags} 
	{/block:Permalink}
{/block:IfShowInLinkWidget} 
<!— End In-Link widget —> 
```

This code includes all the necessary options derived from the above. And here’s the result with the above mentioned options:

![http://media.tumblr.com/tumblr_lkkr1yI7LC1qzz9h9.png](http://media.tumblr.com/tumblr_lkkr1yI7LC1qzz9h9.png)

# Deliver instructions for your Users #

And here a quick text with the instructions for your users.

## InLink Widget Setup options ##

  * **InLink Post Number**: choose a number of posts you would like to see displayed in the “InLink” widget. Default is 8.
  * **InLink Post Length**: choose the length in character of the link you would like to see displayed in the InLink Widget. Exceeding character will be subsituted by “…”. Default is 60.
  * **InLink Style**: choose among four of the available styles. Simple for a bullet list styled list. Complete for a list styled with post icons. Light or Dark for a table styled list of links, also displaying pictures.
  * **InLink Widget Title**: Choose the Title of the InLink Widget list. Default is “Related Posts”.