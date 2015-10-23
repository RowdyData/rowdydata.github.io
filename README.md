# rowdydata.github.io

A repository for materials and experiences in IATI support programmes for NGOs.

# Planning and issue tracking

You can have a look at
[our issue list at Github](https://github.com/RowdyData/rowdydata.github.io/issues),
or at
[our Waffle board](https://waffle.io/RowdyData/rowdydata.github.io)

[![Issues Ready](https://badge.waffle.io/RowdyData/rowdydata.github.io.svg?label=ready&title=Ready)](https://waffle.io/RowdyData/rowdydata.github.io)
[![Issues in Progress](https://badge.waffle.io/RowdyData/rowdydata.github.io.svg?label=in%20progress&title=In%20Progress)](https://waffle.io/RowdyData/rowdydata.github.io)

Our recent throughput -- remember: we just started :-)

[![Throughput Graph](https://graphs.waffle.io/RowdyData/rowdydata.github.io/throughput.svg)](https://waffle.io/RowdyData/rowdydata.github.io/metrics)

Pull requests are welcome!

# Tooling

## Jekyll and Liquid

The bulk of the repository is written to be processed by Jekyll, the static
site generator offered by Github Pages, using the Liquid template engine.

The short version to get it up and running:

1. Make sure you have Ruby version 2.0.0 or newer installed: ```ruby --version```
1. Make sure you have Bundler, or run ```gem install bundler``` (maybe with ```sudo```)
1. Let Bundler do its work: ```bundle install```

Now you can run ```jekyll build``` to create a local copy of the website in the
folder ```_site```.

If you run ```jekyll serve```, it will continue to watch for changes and
update your local copy accordingly. You'll be able to test your local copy
by going to the address [http://0.0.0.0:4000](http://0.0.0.0:4000)

Caveat: if you change something in ```_config.yml``` you will need to stop and
restart Jekyll to read in those changes.

[See Github's full instructions on getting a local version up and running](https://help.github.com/articles/using-jekyll-with-pages/)

## generate-assets

Some things are not processed by the Jekyll engine at Github Pages, so we have
a script to take care of some of the additional processing.

Simply call ```./generate-assets``` in a suitable terminal window on a unix-style
machine. Then call ```jekyll build``` to copy the new assets into your local
version of the website.

Some additional tools are needed to be able to do this.

(This is an area to improve in the future.)

## Ditaa

Ditaa translates _ASCII art diagrams_ into proper images.

The [asciiflow](http://asciiflow.com/) online tool makes it easy to create and
edit such diagrams.

On Debian-based machines like Ubuntu, you can install Ditaa with
```sudo apt-get install ditaa```
