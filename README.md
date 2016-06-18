# jekyll-photo-gallery
Jekyll plugin to generate nice photo galleries easily.


#Installation Guide

1. Download this repository and copy the contents of the folder "plugin" to your jekyll installation.
2. Install the following gems or add them to your gemfile if you're using bundler.

    gem 'mini_magick'
    gem 'exifr'
 
        
#Optional

##1. Enable automatic thumbnail generation

1. Install imagemagick for your system (e.g. apt-get install imagemagick for Linux or brew install imagemagick on macOS)
2. Install jekyll-minimagick "gem install jekyll-minimagick".
3. Remove the '#' in the file "_plugins/jekyll-generate-thumbnails.rb" to enable thumbnail generation