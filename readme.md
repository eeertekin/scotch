#Scotch
###A really classy, dead simple, markdown based, blogging framework for node.js

To try Scotch for yourself, make sure that you have node, npm, geddy (`npm install -g geddy`), and mongodb installed (and running), then do this:

    $> npm install -g scotch-blog
    $> scotch create blog
    $> cd blog
    $> sudo scotch serve

Go to http://0.0.0.0/dashboard/install to install Scotch.

Your blog should be up and running on http://localhost

### Static Site Generation

    $> cd blog
    $> scotch generate
    
Your you should now have a 'static' directory in your blog's root directory.

#### Dashboard

![Scotch's dashboard](https://dl.dropbox.com/u/7982297/scotch_screens/newdash.png)


#### Writing
 
![writing in Scotch](https://dl.dropbox.com/u/7982297/scotch_screens/newwrite.png)

#### Formatting
 * You can use the HTML comment `<!-- more -->` to insert a "read more" link.

#### Reading

![writing in Scotch](https://dl.dropbox.com/u/7982297/scotch_screens/newread.png)

#### Plugins

Plugins are installed in `/app/plugins`.

##### Formatters

Formatter plugins enhance the markdown language and go in `/app/plugins/formatters`.

```js
/*
* An example formatter plugin that replaces the string "charcount" with the number
* of characters in the markdown source when viewing a post in the blog index
*/
var replacer = function (buffer) {
  //`this` in the context of a formatter plugin refers to the post model
  return buffer.replace(/charcount/, this.markdown.length);
};

/*
* You can modify either the `index` or `show` actions.
* By not exporting to exports.show, our plugin will only
* run on posts during the index action
*/
exports.index = replacer;

```


### Things to Do

If you'd like to help out, check out the [issue list](https://github.com/Techwraith/scotch/issues?state=open).
