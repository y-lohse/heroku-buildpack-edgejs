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
### DO NOT INCLUDE EDGEJS DEPENDENCY at package.json

## License

MIT
