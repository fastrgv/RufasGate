# RufasGate
Highly portable Stargate fantasy puzzle written in C++ for Mac OS-X and GNU-Linux


# RufasGate -- v 3.9.2

# Newest changes at top of list:


**ver 3.9.2 -- 13may17**

* added lava shriek when dying.
* refined coding of termSnds().
* replaced fancy ceiling frag shader (wispy clouds) in level 4 due to excessive graphical burden.
* added missing library libcrypto...


**ver 3.9.1 -- 10may16**

* using extlibs-frameworks from a pre-release SFML-v2.3.2 repository on github now elliminates a deprecation warning on OS-X.
* now using well-tested sound code from adagate.
* improved sounds;  more simultaneous.
* Improved palm & grass sway in vertex shader.
* Reduced globally allocated objects.
* Added static sound libraries built from latest OpenAL sources on github.
* Developed compilation scripts that now provide several good alternative versions.
* Preferred compilation scripts use static sound libs.
* Normalized all skybox images to 1024x1024.

**ver 3.9 -- 26apr16 [not delivered]**

* Updated to use newer SFML libraries (v2.3.2) and non-proprietary OGG format sounds.
* Improved directories layout.
* Used "ldd" and "otool" to verify linking with included local libs and frameworks to assure enhanced portability of the delivered binary executables.


**ver 3.8.2 -- 9apr16**
* Revised library layout and compile scripts.
* Enhanced portability by using more static libs in gnu/linux compilation;
* All nonstandard libraries are static in OS-X compile script.

**ver 3.8 -- 15mar16**
* Further improvements to ocean shader, gridding.
* Eye height now varies per island elevation.
* Somewhat reduced the size of resources.
* Darkened nightime palms, sand for improved realism.
* Tweaked other shaders and settings so that RufasGate runs better than ever on very old hardware and minimal graphics, eg. a mid 2009 MacMini.

**ver 3.71 -- 5mar16**
* Improved ocean, lava.
* Replaced graphically-heavy wormhole effect with lighter one.  That means it will run more smoothly on older graphic cards.
* Found and fixed flaw in wormhole exit algorithm.

**ver 3.7 -- 2mar16**
* Better fish shaders for realistic wiggle.
* Awesome wormhole effects.
* Larger island with 2 more sharks, serpent.
* Piranha in dungeon pools.

**ver 3.61 -- 25feb16**
* Added a Mac-Binary-Bundle.
* Removed premake build files;  back to using 2 scripts: lcmp.sh or ocmp.sh.



## what is special about this project?

Uses fully modern OpenGL methods in C++ using textures, shaders and uniforms so as to achieve version 3.3 core profile contexts, yet easily compiles and runs on both GNU/Linux and Mac OS-X systems.  This project serves as a testbed for learning the complexities of modern OpenGL and GLSL so that transparency has, to a certain extent, preempted elegance.  

Absolutely no coding specializations or compromises have been made to accomodate proprietary operating systems.

It relies mostly on SDL2, but uses SFML audio because of its elegant audio interface.  There are examples of "fancy" fragment shaders and an environmental cubemap for reflective water in level 2.  It is very difficult to find a complete, working OGL-330-core implementation of cubemaps, such as you find here.



## RufasGate Game Introduction

RufasGate is a first-person (you are the pusher) 3D sokoban puzzle game within a Stargate/Portal fantasy setting.

While exploring a remote south-seas island you find an operational stargate that lures you into a curious sequence of dungeons. Your escape will require the logical rearrangement of weird power cells, called Zero Point Modules [ZPMs], that can roll in only two directions.

Shoot your portal guns at the dungeon walls to define a wormhole escape. But, in order to activate it, all of the ZPMs must be bumped into their sockets. Now, you can only PUSH the ZPMs. That means you will fail if you roll one into a corner or against a wall.

There are 4 dungeons and 5 degrees of difficulty [DoD] for a total of 20 user-replaceable puzzles to solve.  Escape all 4 levels at the current DoD to reach an exotic lake on the surface, where the DoD is increased for your next game.  Each game resumes at the DoD and level attained in the previous game.

Works on Macs running OS-X and PCs running GNU/Linux.


## game controls

Pointing is by touch pad or mouse;

Movement is by arrow keys:

		(Fw)

	(Lt)	(Bk)	(Rt)

L-key, R-key, 
L-Mouse, R-Mouse : shoot the two portal-guns

(space)-key = jump

(esc)-key = exit;  

at the command line type "rufasgate (enter)"
If you ever get stuck inside a short wall, simply jump forward.

------------------------------------------------------------

Binary executables are available for OS-X and 64-bit GNU/Linux, with relatively modest graphics requirements, by today's standards.  It does, however, require OpenGL v. 3.3 or greater.  On GNU/Linux this might require using a proprietary graphic driver, but I'm not sure.  I have tested it and it runs on my 2009 Mac Mini, and an old MacBook as well as GNU/Linux (Ubuntu 14.04 with nVidia proprietary graphic driver).

The C++ source code uses "modern" OpenGL with uniforms and shaders.  Open source developers are welcome to help improve or extend this game, or perhaps rehost to IOS/Android.

Feel free to send comments or suggestions:

<fastrgv@gmail.com>
August 2014


## Build instructions for RufasGate:

Two [pre-compiled] binary executables are provided, one for gnu/linux and one for OS-X.  The OSX executable is intended to have minimal runtime requirements:  rufasgate_osx.  The other binary, rufasgate_gnu, is intended to run in the presence of the directory "gnulibs", which contains some dynamically loaded libraries that can be, but need not be present on a target system:  GLEW, SDL2, SFML.

Two build scripts are delivered:

-------------------------------------------------------
**MacOSX** => ocmps.sh:

script for OSX that references [delivered] local copies of all nonstandard libraries in ./osxlibs/.  The intent is to allow anyone with a c++ compiler on their Mac to build without having to install these nonstandard libraries.

------------------------------------------------------
**GNU/Linux** => lcmps.sh:

utilizes semi-standard shared libraries that are delivered in this bundle under ./gnulibs/, along with the non-standard static libraries SDL2 & SFML.  This was used to build the executable named rufasgate_gnu, which should run in the presence of ./gnulibs/, whether or not your system already has those libraries.  The runtime loader will prefer system libraries if they are present.

The authoring build system is OpenSUSE v13.2 which uses GLIBC 2.14.  This generally means that if your linux distro uses glibc v2.14 or newer, then the prebuilt binary should probably run on your system (and be rebuildable).

If the delivered linux binary does not run, rebuild using lcmps.sh or lcmp.sh.




## required for running:

* graphics card & driver that supports OpenGL version 3.3 or later;

## Open Source libraries required for building:

* a recent gcc compiler that supports -std=c++11;



## Running rufasgate:

Unzip the archive and you will see a new directory appear with a name like <bundle+date>, that you should rename to something like <install_directory>.  

Users should then cd to <install_directory>, then, at the command line, type the executable name to start the game.

Mac users note that this game may be initiated in two ways.  First, by opening a terminal, navigating to the install_directory, and typing rufasgate_osx on the command line.  Second, by navigating to the installation directory in Finder and clicking the "rufasgate.app" icon named "rufasgate".
 
The <install_directory> should contain subdirectories named "data", "gnulibs", "osxlibs", "incLocal".

Thus, from the command line type "rufasgate_gnu" or "rufasgate_osx"



--------------------------
## Legal Mumbo Jumbo:


RufasGate itself is covered by the GNU GPL v3 as indicated in the sources:

 Copyright (C) 2016  <fastrgv@gmail.com>

 This program is free software: you can redistribute it and/or modify
 it under the terms of the GNU General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 This program is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU General Public License for more details.

 You may read the full text of the GNU General Public License
 at <http://www.gnu.org/licenses/>.


--------------------------
## Media Files for AdaGate:

### General Note
The particular choices of sound, image, and shader files [x.fs] delivered are not essential to the function of the game and are easily replaced.  This software is primarily intended as a tutorial example of modern OpenGL methods using GLSL.  The only requirements are that sounds be in WAV format, images be in PNG format, and shaders be updated to GLSL 330 specifications.  Skybox images have an additional constraint, they must also have a 90x90 degree field of view [for a correct perspective], and all 6 must have the same pixel dimensions.

### Defining Your Own Puzzles
Read: puzzle_replacement.txt

### SoundFiles [x.wav]
Most are from freesound.org and are thus covered by the Creative Commons Attribution noncommercial license documented in the accompanying file ccnc3_license.txt.  see also:  http://creativecommons.org/licenses/by-nc/3.0/legalcode/

"Among the Falls" [music for level 1] is from http://www.freesfx.co.uk.  See the file "freeSFX_license.txt.


### ImageFiles 
Most images for textures were freely [no copyright indications] available on google images.  Some wall textures used are from the GPL2.0/GPL3.0-only section of OpenGameArt.Org.  One other thatched roof texture was used from http://www.mayang.com/textures.  See mayang_license.txt.

### ShaderFiles 
Some fragment shader files used were downloaded from http://glslsandbox.com/ and put under ./data/ that are not labelled as GNU-GPL'd, namely:

clouds.fs, darkwater3.fs, starfield3.fs, volcano.fs
...as well as some sections of a couple of other fragment shaders...

...these appear to contain comments/attributions from their authors so were left unchanged.  Most fragshadersfrom glslsandbox are under the MIT license (see mit_license.txt), but some have CreativeCommons licenses (see ccnc3*.txt, ccsa3*.txt).

Also from glslsandbox...added:  "Seascape", "Red Planet" from Alexander Alekseev and Mahmud Yuldashev <mahmud9935@gmail.com> as well as an uncredited blueSpiral.fs, and a palmTreeWindmill.fs.  As with most, I had to modify to glsl version 330 and adapt them to use some programatic uniforms for input.


### SkyBoxes 
For some of these, I lowered the horizon slightly for technical reasons;  and for others I converted to png files with RGBA mode.

One used is from www.custommapmakers.org/skyboxes.php, which gathers together many free-to-use skyboxes.

Another skybox  [from  http://www.redsorceress.com/skybox.html]  is credited to "The Mighty Pete" at http://www.petesoasis.com (which seems defunct).

Other beautiful hi-res skyboxes [from OpenGameArt.org] are the work of Heiko Irrgang <hi@93-interactive.com> and is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License.  To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/ or send a letter to Creative Commons, 444 Castro Street, Suite 900, Mountain View, California, 94041, USA.  See also the accompanying file ccsa3_license.txt.

### LodePNG (png loader module)

lodepng.cpp lodepng.h
are files copyrighted by Lode Vandevenne and so marked
with all the details of their permitted uses 
near the tops of those two files.  See:
http://lodev.org/lodepng/

