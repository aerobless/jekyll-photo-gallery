# Jekyll-Photo-Gallery
With Jekyll-Photo-Gallery you can easily generate a photo gallery for your Jekyll site or blog.
Jekyll-Photo-Gallery generates a static index and a page for every photo based on the layouts photoIndex.html and photo.html.
These layouts can be easily adapted to fit the style of your site. The photo layout is also automatically enriched with metadata 
such as photo location (Google Maps), ISO, F and speed values.  
The whole plugin is setup so that new photos can be added with minimal effort. Thumbnails are automatically generated with ImageMagick on macOS and Linux. (It may work on windows as well, 
but you need to find out how to install ImageMagick yourself.)

#Features
+ Dynamically loaded photo stream
+ Justified gallery layout
+ One URL per picture allows for easy sharing
+ Automatic thumbnail generation (on macOS, Linux)
+ One subpage per picture, ideal for SEO
+ Automatically embedded Schema.org meta information
+ Responsive photo view
+ Easily adaptable layouts
+ Google Maps Geolocation
+ EXIF tag supports
+ Support for albums/trips (alpha)
+ Embeddable galleries for posts (alpha)

[![Example](https://raw.githubusercontent.com/aerobless/jekyll-photo-gallery/master/example.jpg)](http://w1nter.com/jekyll-photo-gallery/photography/)

#Demos

1. [Demo site running the "sample-installation"](http://w1nter.com/jekyll-photo-gallery/photography/)
2. [My personal blog running a customized version of the plugin](https://theowinter.ch/photography/)\*  
*\*The sample-installation is newer and has less bugs.*

#Installation Guide

1. Download this repository and copy the contents of the folder "plugin" to your jekyll installation.
2. Install the following gems or add them to your gemfile if you're using bundler.

    > gem 'exifr'
 

        
        
        
#Enable optional features

###1. Enable automatic thumbnail generation

1. Install imagemagick for your system (e.g. `apt-get install imagemagick` for Linux or `brew install imagemagick` on macOS)
2. Install mini_magick `gem install mini_magick`
3. Install jekyll-minimagick `gem install jekyll-minimagick`.
4. Remove the '#' in the file "_plugins/jekyll-generate-thumbnails.rb" to enable thumbnail generation

###2. Enable Google Maps Geolocation

1. Obtain a Google Maps "Static Maps API key" from this site: https://developers.google.com/maps/documentation/static-maps/
  1. Create a new project for your site (or chose an existing one).
  2. Make sure that "Google Static Maps API" is selected in the API drawer, then select "Web browser (Javascript)" from the drawer below.
  3. Enter all the URL(s) of your website from which you'll be accessing google maps. E.g. `*yoursite.com*` or `*localhost*` or `*.yoursite.com/*` .. etc.
2. Open layouts/photo.html and replace the existing key (around line 113) **&key=AIzaSyCMXdSigC-sBH...** with your new key.

###3. Embed an album/gallery in a post
1. Add album meta-data to the photos you want to include in your post.
  1. Go to `_data/photos.yaml`
  2. Add the property `album: uniqueAlbumName`
2. Open your-post.md and add `{% includeGallery uniqueAlbumName %}`




#Known bugs & limitations

**1. Fixed order in detail view:**  
Atm every photo detail page contains its "previous picture" & "next picture" information. So even though you can change
the order of pictures in a gallery via JS, when you load a detail view and click next the original next picture will be displayed.
This also means that if you're in a album and you click on next in the detail view of the last picture it will go to the next picture
regardless if that picture is in the album.

**2. Only one album per photo:**  
Right now a photo can only be in one album at a time.

**3. Why are you including the CSS files in head.html as well as individual templates?**  
To make the setup easier for people who just copy the specific templates. Including them once is enough.




#Troubleshooting
If the gallery doesn't appear in your page but the files have been generated correctly then it's likely that there is a javascript error.
In order to find the problem it's best to open the javascript console on Chrome (or your browser of choice) and to reload the page. If there's an error
it will now appear in the console output.

**1. Uncaught ReferenceError: $ is not defined:**  
This error happens when jQuery wasn't loaded before executing the gallery script. Make sure that your templates has the jQuery includes.

**2. The gallery isn't justified, the thumbnails are in a vertical line:**  
Be sure to include the CSS files "justifiedGallery.min.css" and "jekyll-photo-gallery.css" in the template where you're using the gallery. If you're embedding the gallery
in a post the template of the post also has to include these CSS files.





#License (MIT)
 > Copyright (c) 2016 Theodor Winter
 
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