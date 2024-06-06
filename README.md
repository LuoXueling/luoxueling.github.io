
# Xueling Luo's personal website

I add scroll sticky ToC on the right and (temporarily) remove the navigation bar, based on [this branch](https://github.com/academicpages/academicpages.github.io/tree/5dee723c4017b7d297a31daa3950d8eeb6570c61) of academicpages.github.io

# How I use AcademicPages

I test the website locally on a Macbook M2. First install [Homebrew](https://brew.sh/). Then Ruby following [this link](https://stackify.com/install-ruby-on-your-mac-everything-you-need-to-get-going/).

Make sure you are using Ruby you installed just now using `ruby -v`. If not, follow the above link to update PATH. 

Then install Jekyll by `gem install jekyll`, bundler by `gem install bundler` and npm by `brew install npm`. 

`cd` to the root of the project, and then

```shell
bundle config set --local path vendor/bundle
bundle install
```

Run `zsh run-local.sh` to the start local server and open [`localhost:4000`](localhost:4000). 

If anything changes in `assets/js/_main.js` or other js files in `assets/js`, you should run `npm run build:js` (or `npm run watch:js` to continuously watch changes) that updates `assets/js/main.min.js`. If a new js file is added to `assets/js/`, it should be added to `package.json` in the `scripts` - `uglify` entry similar to other js files.

When merge changes to the master branch, after on the github page of this project you set up Settings - Pages, github actions will automatically deploy the website. Turn Settings - Pages - Build and deployment - source from "Deploy from a branch" to "Github Actions" and use the recommended Jekyll action to use any Jekyll version you installed locally. 