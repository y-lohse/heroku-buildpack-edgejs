# heroku-buildpack-edgejs

Add support for apt-based dependencies during both compile and runtime. Furthermore install mono, dnvm and edge.js.

## Usage

This buildpack works as a secundary buildpack. You mus set heroku/nodejs as a primary buildpacks and this repo as a secundary.

Include a list of apt package names to be installed in a file named `Aptfile` in your app file folder.

```bash
curl -sSL https://raw.githubusercontent.com/ddollar/heroku-buildpack-apt/master/Aptfile > Aptfile
```

Now clear buildpacks and adds them in correct order:

```bash
heroku buildpacks:clear
heroku buildpacs:set https://github.com/lastko/heroku-buildpack-edgejs
heroku buildpacs:add --index 1 heroku/nodejs
```

	
## License

MIT
