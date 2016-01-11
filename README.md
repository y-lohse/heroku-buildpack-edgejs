# heroku-buildpack-edgejs

Add support for edgejs (http://tjanczuk.github.io/edge/#/) in heroku stack.

## Usage

This buildpack works as a secundary buildpack. You must set heroku/nodejs as a primary buildpacks and this repo as a secundary.

In order to use this buildpack you must put `Edgejs` empty file at the root project.

```bash
touch Edgejs
```
Now clear buildpacks and adds them in correct order:

```bash
heroku buildpacks:clear
heroku buildpacks:set heroku/nodejs
heroku buildpacks:add https://github.com/lastko/heroku-buildpack-edgejs
```

By default edge.js use **mono** if you want to use **coreCLR** you must set environment variable:

```bash
heroku config:add EDGE_USE_CORECLR=1
```

**DO NOT INCLUDE EDGEJS DEPENDENCY in package.json.**

## License

MIT
