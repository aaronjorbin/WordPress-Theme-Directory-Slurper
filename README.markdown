WordPress Theme Directory Slurper
==================================

A command line PHP script that downloads and updates a copy of the latest stable
version of every theme in the [WordPress.org theme repository][repo].

Really handy for doing local searches across all WordPress themes.

[repo]: http://wordpress.org/themes/

Requirements
------------

* PHP 5.2
* wget
* Unix system (only tested on Mac OS X)

Instructions
------------

1. `cd WordPress-Theme-Directory-Slurper`
2. `./update`

The `theme/` directory will contain all the themes, when the script is done.

FAQ
----

### Why download the zip files? Why not use SVN? ###

An SVN checkout of the entire repository is a BEAST of a thing. Additionally, not all themes listed in the svn repositoriy are currently active.

### Why not just do an SVN export of each themes's trunk? ###

There is no guarantee that the theme's trunk is the approved version. All themes must go through an approval process. Using the zip file gets around this as it uses the theme API to figure it all out and gives you the latest stable version

### How long will it take? ###

Your first update will take a while. You'd be well-advised to let it run overnight. But subsequent updates are smart. The script tracks the SVN revision number of your latest update and then asks the Theme Trac install for a list of themes that have changed since. Only those changed themes are updated after the initial sync.

### How much disk space do I need? ###

As of early 2015, it takes up about 3.7GB.

### Something went wrong, how do I do a partial update? ###

The last successful update revision number is stored in `themes/.last-revision`. You can just overwrite that and the next `update` will start after that revision.

### What if I want Plugins instead of Themes? ###
Check out the [WordPress-Plugin-Directory-Slurper](https://github.com/markjaquith/WordPress-Plugin-Directory-Slurper).

Copyright & License
-------------------
Copyright (C) 2015 Aaron Jorbin

Based on [WordPress-Plugin-Directory-Slurper](https://github.com/markjaquith/WordPress-Plugin-Directory-Slurper) which is Copyright (C) 2011 Mark Jaquith

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program; if not, write to the Free Software
Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA  02110-1301, USA.
