# Defining your own style. #

By simply omitting the css option, you will have the opportunity to implement your own style. In this case these are the css selectors this widget uses:

```
#tumblrinlink {	} 		/* Main div Container */
#tumblrinlink h2 { }	/* Title */
#tumblrinlink a { }		/* Link Style */			
li.inlink-item { }		/* List Item (each content is rendered as li) */
li.inlink-item img {
		display:none; 	/* if you don't want to display images use this */
			}
li.inlink-item p { }	/* The actual title for the link */
#inlink-list { }		/* The ul container */
/* Each li has its own selector for individual styling depending
* on post type. */
li.inlink-item#regular { }
li.inlink-item#link { }
li.inlink-item#quote { }
li.inlink-item#conversation { }
li.inlink-item#video { }
li.inlink-item#audio { }
li.inlink-item#answer { }
.notes { } /*New in version 2*/
```

Feel free to customize your look and feel through these options.