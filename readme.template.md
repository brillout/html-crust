# `@brillout/html`

Small vanilla JavaScript library to generate HTML documents.

It is typically used in combination with a modern view library that supports server side rendering such as React or Vue.

The main content of the HTML is generated by React/Vue and the rest of the HTML is generated by `@brillout/html`.

It used to generated the "outer part" and meta tags such as
`<!DOCTYPE html>`,
`<body>`,
`<head>`,
`<style>`,
`<script>`.

It is designed to be entirely flexible: you have full control over the generated HTML.

#### Contents

 - [Usage](#usage)
 - [API](#api)

<br/>
<br/>




### Usage

There are two ways to control the generated HTML:
 - By using the options of `html()`.
 - By creating an `index.html` file.

Example:

~~~js
!INLINE ./examples/basic/index.js
~~~

Result:

~~~html
<!DOCTYPE html>
<html>
  <head>
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
  <meta charset="utf-8">
    <title>Example Page</title>
    <link rel="shortcut icon" href="/static/logo.png">
    <meta name="description" content="Some Description.">
    <link href="/static/style.css" rel="stylesheet">
    <link rel="manifest" href="/manifest.webmanifest">
  </head>
  <body>
    <h1>Welcome</h1>
    <script src="/static/bundle.js" type="text/javascript"></script>
  </body>
</html>
~~~

The default base HTML document is:

~~~html
<!-- ./index.html -->

!INLINE ./index.html --hide-source-path
~~~

But you can as well define a custom base HTML document.
Simply create a `index.html` file somewhere in your project's directory:

~~~html
<!-- ./examples/custom-base/index.html -->

!INLINE ./examples/custom-base/index.html --hide-source-path
~~~

~~~js
!INLINE ./examples/custom-base/index.js
~~~

Result:

~~~html
<!DOCTYPE html>
<html>
    <head>
        <title>Title set over index.html file</title>
        <meta charset="utf-8">
        <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1">
        <link href="/static/style.css" rel="stylesheet">
    </head>
    <body>
        <h1>Welcome</h1>
        <script src="/static/bundle.js" type="text/javascript"></script>
    </body>
</html>
~~~

Also note that you can use the `html` option instead of creating a file.
See the next section "API" for an example.

<br/>
<br/>




### API

The following example exhibits all options:

~~~js
!INLINE ./examples/full/index.js
~~~

Result:

~~~html
<html>
    <head>
        <title>Title set over the `html` option</title>
        <link ref="icon" href="/static/some-logo.png" />
        <meta name="description" content="Some Description.">
        <meta name="viewport" content="width=device-width">
        <meta charset="utf-8">
        <link href="/static/style.css" rel="stylesheet">
        <style>body { margin: 0 }</style>
        <custom-element attr-1 attr-2="1337"/>
    </head>
    <body>
        <div>Hello World</div>
        <script src="/static/bundle.js" type="text/javascript"></script>
        <script src="https://example.org/neat-script.js" async type="application/javascript"></script>
        <script src="/static/es6-module.mjs" defer data-some-custom-attribute="with some custom value" type="module"></script>
        <script type="text/javascript">console.log('hello from `@brillout/html`')</script>
    </body>
</html>
~~~

<br/>
<br/>


