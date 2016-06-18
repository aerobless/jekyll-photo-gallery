# jekyll-photo-gallery
Jekyll plugin to generate nice photo galleries easily.


#Features
+ Dynamically loaded photo stream
+ Justified gallery layout
+ One URL per picture allows for easy sharing
+ Optional automatic, integrated thumbnail generation
+ One subpage per picture, ideal for SEO
+ Easily adaptable layouts for gallery index & photo page
+ Optional Google Maps Geolocation integration
+ EXIF tag support
+ Support for albums (coming soon)
+ easily extensible

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

##2. Enable Google Maps Geolocation

coming soon..


#License (MIT)
 > Copyright (c) 2015 Theo Winter
 
 > Permission is hereby granted, free of charge, to any person obtaining a copy
 of this software and associated documentation files (the "Software"), to deal
 in the Software without restriction, including without limitation the rights
 to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 copies of the Software, and to permit persons to whom the Software is
 furnished to do so, subject to the following conditions:
 
 > The above copyright notice and this permission notice shall be included in
 all copies or substantial portions of the Software.
 
 > THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
 THE SOFTWARE.