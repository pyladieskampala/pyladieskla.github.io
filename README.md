# Geek Night Kampala

# Development

Using [nanoc](//nanoc.ws) for static site generation. Jekyll/Octopress are hard-coded for blogging, while Nanoc is much simpler, doesn't take any assumptions and allows to build whatever type of content (not just blogs).

To start developing,

* Clone this repository
* Forget about whatever present in the root folder
* Worry only about the `generator` folder
* `cd generator` and do `bundle install`. You'll need RVM + Ruby 2.0
* Make changes (see below folder structure). Mostly you'll be dealing with `generator/content`
* Run `nanoc` to compile the website
* Run `nanoc view` to start a server and browse to `localhost:3000`

For ease, there is a Guardfile. You can run `bundle exec guard`, it will keep watching for changes and re-compile the site whenever any file is changed.

# Folders of interest

* `generator` - this is the main source code, rest are all generated source code that can be ignored
* `generator/assets` - contains all assets
* `generator/assets/app.sass` - contains the main stylesheet
* `generator/assets/img/speakers` - contains speaker images
* `generator/content` - content for each geek night
* `generator/layouts` - layouts for default and archive versions
* `generator/Rules` - routing rules

# Front-End Development

* Pure HTML/CSS/Javascript website. No JQuery.
* Used [HTML5 Boilerplate](//html5boilerplate.com) to generate the skeleton.
* Used [colourlovers.com](//colourlovers.com) for the color swatches.
* Using [SASS](//sass-lang.com) and [Foundation](//foundation.zurb.com) for all the Styling.
* Icon fonts were generated and downloaded from [Fontello](//fontello.com). Only icons from the *Modern Pictogram* set were used for consistency.



# Updating the website content

To update the website:
 * clone the github repository and cd into it: `git clone https://github.com/twkampala/geeknight.git && cd geeknight`, 
 * Once inside the repository, `cd generator` (This is the content generator that uses `nanoc`)

## Installing the requirements (dependencies)

* once inside the generator directory, you will notice that its a ruby application, thus we need to install a few gems most importantly 'nanoc'
* To achieve this we need to run: `bundle install` (all required gems are listed in the `Gemfile`)
* If for some reason you get an error here, it could be bacsue you don't have bundler, If thats the case, then just run `gem install bundler`
* Once this finishes, you should be able to run `nanoc` to compile and `nanoc view` to serve the static website on http:://localhost:3000. You may also just double click the index.html in the root directory ("geeknight")

## Making changes
Adding a new edition is really easy, three simple steps:
1. `cp generator/content/index.html [Year - previous months].html` e.g If last edition was in July 2015, `cp generator/content/ndex.html generator/content/2015-07.html`. This makes sure that the previous months is available in the flashback section/Previous editions.
2. Now, Open `generator/content/index.html` and edit it with the up-coming edtions details.
