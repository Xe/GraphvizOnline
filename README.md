# GraphvizOnline

Known stable, no major development will be done in this repo.

## Introduction

Author: [dreampuf](https://github.com/dreampuf/)  
Maintainer: [Xe](https://github.com/Xe)

[GraphvizOnline](https://github.com/Xe/GraphvizOnline) is a simple online editor frame for [Graphviz](https://graphviz.org). This version has been edited to run as a progressive web app with full offline support.

See [here](https://graphviz.christine.website) for a live demo.

## How This was Implemented

- [viz.js](https://github.com/mdaines/viz.js) - This repo has compiled graphviz(C) to javascript via [emscripten](https://github.com/kripken/emscripten).
- [ACE-editor](http://ace.ajax.org/) - An amazing online editor.
- [Service Workers](https://github.com/Xe/GraphvizOnline/blob/master/sw.js)

## License

GraphvizOnline is licensed under a BSD-3 license. The dependencies are:

- [viz.js](https://github.com/mdaines/viz.js/blob/master/LICENSE) MIT
- [ACE-editor](https://github.com/ajaxorg/ace/blob/master/LICENSE) BSD-2

## Deployment

### Heroku

```console
$ heroku apps:create
$ git push heroku master
$ heroku open
```

### Minipaas (or other [Dokku](http://dokku.viewdocs.io/dokku/) instances)

Depends on [dokku-letsencrypt](https://github.com/dokku/dokku-letsencrypt). In my configuration `minipaas` is a command that interfaces with my instance of [Dokku](http://dokku.viewdocs.io/dokku/), and `open` is a command that opens the given file or URL with the best program for the job.

```
$ minipaas apps:create
$ git remote add dokku@minipaas.xeserv.us:graphviz-<numbers>
$ git push dokku master
$ minipaas config:set graphviz-<numbers> DOKKU_LETSENCRYPT_EMAIL=your@email.tld
$ minipaas letsencrypt graphviz-<numbers>
$ open https://graphviz-<numbers>.minipaas.xeserv.us
```
