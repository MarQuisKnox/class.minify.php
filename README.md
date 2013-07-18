class.minify.php
================

A pretty simple PHP minify tool for JS and CSS files. It works using regular expressions and it has no external dependences.
It removes comments, linebreaks, extra whitespaces and it fixes wrong object notation (JavaScript).

Usage
-----

<pre><code>require_once('class.minify.php');
$minify = new Minify();
try {
  $minify->addSource("script.js");
  $minify->exec();
} catch (MinifyException $e) {
  //print_r($e->getMessage());
}
</code></pre>

The file will be saved in the same path of the source file and it will named `source.min.ext`. You can use `->setTarget("/path/to/target/and/name.ext")` to set the destination file.


General tips
------------
Use this to generate missing minified files just once, don't use this class on every request because that will increase the load of the machine. Use this to manually generate minified files or when the system detects that the minified file is missing.
