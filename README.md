pa.js
======

What is it?
-----------

Pa.JS is a simple template to let users use and import Markdown (.md) files into web pages. This can simplify changing content on a webpage for non technical users. This project uses [markdown.js](https://github.com/trevorstarick/marked/blob/master/markdown.js) from [evilstreak/markdown-js](https://github.com/evilstreak/markdown-js) to convert the Markdown to HTML. It uses an AJAX request to load a Markdown file into memory and then passes it to [markdown.js](https://github.com/trevorstarick/marked/blob/master/markdown.js). This project is aimed to help simplify web design and content managment without the need for a full CMS.

Demo
----
[marked demo](http://pajs.starick.me)

Usage
------------

Copy `markdown.js` to the same directory as your HTML file. After that just add:

```
<script src="http://code.jquery.com/jquery-2.0.0.min.js"></script>
<script src="markdown.js"></script>
<script type="text/javascript">
$.get('MARKDOWN.md', function(res){
  $("#marked").html(markdown.toHTML(res));
});
</script>
```

to the `<head>` of your webpage and `<div id="marked"></div>` to your `<body>` and you're set! If you need more than one Markdown file loaded just create a new `<div>` with any id and add:

```
$.get('NEWFILE.md', function(res){
	$("#newDiv").html(markdown.toHTML(res));
});
```

right after the orginal script. In this case I chose to load `NEWFILE.md` into `<div id="newDiv"></div>` but you can use whatever names/ids you choose in your code.

Requirements
------------

This code won't work without a server being able to process and run AJAX requests. For a localhost fix try running the server by opening a terminal/command prompt, 'cd'ing to the directory and running `python -m 'SimpleHTTPServer'

Licensing
---------
This code is liscensed under the [WTFPL license](http://www.wtfpl.net/)
