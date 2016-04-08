# heroku-buildpack-edgejs

Adds support for edgejs (http://tjanczuk.github.io/edge/#/) in heroku stack.

## Usage

This buildpack works as a secundary buildpack. You must set heroku/nodejs as a primary buildpack and this repo as the secondary.

In order to use this buildpack you must place `Edgejs` empty file at the root project.

```bash
touch Edgejs
```
Now clear buildpacks and adds them in correct order:

```bash
heroku buildpacks:clear
heroku buildpacks:set heroku/nodejs
heroku buildpacks:add https://github.com/lastko/heroku-buildpack-edgejs
```

By default edge.js uses **mono** if you prefer to use **CoreCLR** instead you must set environment variable:

```bash
heroku config:add EDGE_USE_CORECLR=1
```

**DO NOT INCLUDE EDGEJS DEPENDENCY in package.json.**

If you want use cache at build time, write in Edgejs file:

```bash
USE_CACHE=1
```

## License

MIT
