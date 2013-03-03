---
title: GSL gem on OS X
tags: OS X, gsl, jekyll
---

I use [Jekyll][] for a lot of things and wanted to try out the related posts feature. Generating the related posts was taking forever, so I followed the command line suggestion of installing GSL. I tried following [Brett Hardin's directions][hardin], but I was getting an error installing gsl114:

    $ brew install gsl114
    ==> Downloading http://ftpmirror.gnu.org/gsl/gsl-1.14.tar.gz
    Already downloaded: /Library/Caches/Homebrew/gsl114-1.14.tar.gz
    Error: undefined local variable or method `build' for gsl114:Gsl114
    Please report this bug:
        https://github.com/mxcl/homebrew/wiki/reporting-bugs
    /usr/local/Library/Formula/gsl114.rb:12:in `install'
    /usr/local/Library/Homebrew/build.rb:88:in `install'
    /usr/local/Library/Homebrew/formula.rb:190:in `brew'
    /usr/local/Library/Homebrew/formula.rb:516:in `stage'
    /usr/local/Library/Homebrew/extend/fileutils.rb:22:in `mktemp'
    /usr/local/Library/Homebrew/formula.rb:512:in `stage'
    /usr/local/Library/Homebrew/formula.rb:185:in `brew'
    /usr/local/Library/Homebrew/build.rb:67:in `install'
    /usr/local/Library/Homebrew/build.rb:30
    /usr/local/Library/Formula/gsl114.rb:11

Instead, I built gsl 1.14 from source!

    curl -O http://mirror.aarnet.edu.au/pub/gnu/gsl/gsl-1.14.tar.gz
    tar xfz gsl-1.14.tar.gz
    cd gsl-1.14
    ./configure
    make clean
    make
    sudo make install

Then, I installed the gsl gem (`gem install gsl`). Jekyll's related post feature is drastically faster.

[Jekyll]: https://github.com/mojombo/jekyll
[hardin]: http://bretthard.in/2012/03/getting-related_posts-lsi-and-gsl-to-work-in-jekyll/

