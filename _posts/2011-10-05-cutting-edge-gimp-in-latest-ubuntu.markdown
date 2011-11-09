--- 
layout: post
title: Cutting edge gimp in latest ubuntu 
redirects: 
  - 2011/10/cutting-edge-gimp-in-latest-ubuntu.html 
--- 

If you want to run the latest development version of gimp (2.7.x) in ubuntu 11.10, here's how to achieve that in a few command lines.  
  
Notes that the following has been tested successfully on Ubuntu 11.x fresh
installed and updated systems.

You'll not be able to compil the current 2.7 gimp snapshot on lucid, as it
require a higher version of glibc than the one included by the distribution.
It's still possible to compil it on lucid, but if you know how to do that, you
don't need me anymore :)

  
So, I've wrote a little bash script to automate the process of compiling the
gimp's latest development version and it's dependencies,  which should work
fine on a fresh Oneiric install.

  
Just download the script or clone the git repository, optionally, configure
it, and run.

  
If you don't have the git command, you may install it. That will help you in
keeping the script up to date:

    sudo aptitude install git-core

Then:

    git clone git://github.com/zanshine/gimp-razor.git
    cd gimp-razor
    ./gimp-razor

Alternatively, if you don't wanna use git, you can download the script
([https://raw.github.com/zanshine/gimp-razor/master/gimp-razor)][1], make it
executable and run:

    wget https://raw.github.com/zanshine/gimp-razor/master/gimp-razor
    chmod u+x gimp-razor
    ./gimp-razor

That's it!

Out of the box, this script will retrieve the latest gimp sources and it's
unmet dependencies on ubuntu 11.10, wich are gegl and babl.

It will compil gimp under `~/opt/gimp/build_$build_id`, where $build_id is a
simple timestamp. So you'll be able to make nightly builds if you want,
without breaking the last ones. At the end of the process, your newly cutting
edge gimp will be launched.
 
Please, report any issue you'd have with the script, and I'll try to solve
them quickly.

   [1]: https://raw.github.com/zanshine/gimp-razor/master/gimp-razor

