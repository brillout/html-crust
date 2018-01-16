A vanilla JavaScript library to handle the outer part of `<html>`.
<br/>
(Including `<head>`, `<style>`, `<script>`, `<!DOCTYPE html>`, etc.)

# `@brillout/html-crust`

This package handles the outer part of HTML
by either generating HTML or
by manipulating the DOM.

With "outer HTML" we denote the `<head>` tag, the `<!DOCTYPE html>` tag, `<script>` tags, etc.

Note that everything is customizable.
You can set any arbritary head and body, and the whole HTML can be arbitrarily set as well.

The following example exhibit all options.

~~~js
!INLINE ./example.js
~~~

Running the example prints

~~~html
<!DOCTYPE html>
<html>
  <head>
    <link href="/static/style.css" rel="stylesheet">
    <title>Example Page</title>
    <meta name="description" content="HTML created with `@brillout/html-crust`">
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
    <meta charset="utf-8">
  </head>
  <body>
    <div>Hello World</div>
    <script src="/static/bundle.js" type="text/javascript"></script>
    <script src="https://example.org/neat-script.js" async type="application/javascript"></script>
    <script src="/static/es6-module.mjs" defer data-some-custom-attribute="with some custom value" type="module"></script>
  </body>
</html>

<!DOCTYPE html>
<html>
  <head>
    <title>HTML without charset nor viewport.</title>
    <custom-element attr-1 attr-2="1337"/>
  </head>
  <body>
  </body>
</html>

<!DOCTYPE html>
<html>
  <head>
    <new-html8-head-tag>Customized head</new-html8-head-tag>
  </head>
  <body>
  </body>
</html>

<!DOCTYPE html>
<html>
  <head>
    <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
    <meta charset="utf-8">
  </head>
  <body>
    Customized body
  </body>
</html>

<HTML>Even the entire html is customizable</HTML>
~~~