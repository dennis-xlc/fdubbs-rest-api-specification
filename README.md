## Setup

Ruby 1.9 is required to build the site.

Get the nanoc gem, plus kramdown for Markdown parsing:

```sh
$ bundle install
```

You can see the available commands with nanoc:

```sh
$ bundle exec nanoc -h
```

Nanoc has [some nice documentation](http://nanoc.ws/docs/tutorial/) to get you started.  Though if you're mainly concerned with editing or adding content, you won't need to know much about nanoc.

[nanoc]: http://nanoc.ws/

You can setup whatever you want to view the files. If using the adsf
gem (as listed in the Gemfile), you can start Webrick:

```sh
$ bundle exec nanoc compile
$ bundle exec nanoc view
$ open http://localhost:3000
```

Compilation times got you down?  Use `autocompile`!

```sh
$ bundle exec nanoc autocompile
```

This starts a web server too, so there's no need to run `nanoc view`.
One thing: remember to add trailing slashes to all nanoc links!

## Deploy

```sh
$ bundle exec rake publish
```