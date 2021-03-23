![screenshot](https://github.com/fastrgv/RufasGate/blob/master/nightbeach.jpg)

# RufasGate
Highly portable Stargate fantasy puzzle written in C++ for Windows, Mac OS-X and GNU-Linux

Direct download link:

https://github.com/fastrgv/RufasGate/releases/download/v5.0.0/rg21nov20.7z





# RufasGate


# Most Recent Updates:


**ver 5.0.0 -- 17nov2020**
* All new sound system using Pthreads and OpenAL.
* Runs using Pthreads on Windows, OSX, Linux.
* Sound code is now identical for all 3 platforms.
* Completely elliminated SFML-audio (Windows & OSX).


**ver 4.2.1 -- 14nov20**
* updated SDL2 libs to v2.0.12, if possible.
* delayed premature music.
* OSX rebuild was done at low Dpi due to jerkiness.
* moved string manipulation code outside of threads.


**ver 4.2.0 -- 21oct20**
* Converted to all c++ sound system on linux;
* Simplified linux build process.


**ver 4.1.3 -- 15oct20**
* Nice improvement of lava pool shaders.
* Improved sdl-initialization code.


## More change-history at end of file.




## RufasGate Game Description
RufasGate is a first-person (you are the pusher) 3D sokoban puzzle game within a Stargate/Portal fantasy setting.  It now runs on Windows, OSX, and GNU/Linux -- most all linux distros.

Shipwrecked on a remote south-seas island, you find an operational stargate that sends you into a curious sequence of dungeons. Your escape will require moving weird power cells, called Zero Point Modules [ZPMs], that can roll in only two directions.

Shoot your portal guns at the dungeon walls to define two ends of an escape tunnel through another dimension.  But, in order to activate the portals, all of the ZPMs must be bumped onto a power socket.  And since you can only PUSH the ZPMs, you will fail if you roll one into a corner or against a wall.  So think carefully before you push.

There are 4 dungeons and 5 degrees of difficulty [DoD] for a total of 20 user-replaceable puzzles to solve.  Escape all 4 levels at the current DoD to reach an exotic lake on the surface, where the DoD is increased for your next game.  Each game resumes at the DoD and level attained in the previous game.



## game controls

Pointing is by touch pad or mouse;

Movement is by arrow keys:

(Fw)

(Lt)  (Bk)  (Rt)

L-key, R-key, 
L-Mouse, R-Mouse : shoot the two portal-guns

(space)-key = jump

(esc)-key = exit;  

If you get stuck inside a short wall, simply jump forward.

------------------------------------------------------------


## Running rufasgate:

Unzip the archive, The proper command to extract the archive and maintain the directory structure is "7z x filename".


open a commandline terminal, and cd to the install directory.

Linux users should type "rufasgate_gnu" to start the game. 
Note that you can also run the windows version on linux if you have wine thusly:
  * wine rufasgate.exe




Windows users type "rufasgate.exe".

Similarly, OSX users may type "rufasgate_osx", or navigate to the installation directory in Finder and clicking the "rufasgate.app" icon named "rufasgate".





## Build instructions for RufasGate:

Three [pre-compiled] binary executables are provided, one for Windows, one for gnu/linux and one for OS-X.  The linux binary, rufasgate_gnu, runs on most linux distros. So you typically do not need to rebuild the apps.

If you are a developer and want to rebuild, then use one of the following three build scripts:

-------------------------------------------------------
**msWin32** => wcmp.bat

build script that requires libraries included in ./libs/win/.

-------------------------------------------------------
**MacOSX** => ocmp.sh:

script for OSX that references local copies of all nonstandard libraries in ./libs/osx/, or in ./rufasgate.app/Contents/Frameworks/.  The intent is to allow anyone with a c++ compiler on their Mac to rebuild without having to install these nonstandard libraries.

------------------------------------------------------
**GNU/Linux** => lcmp1.sh, lcmp2.sh, lcmp3.sh

Here, the C++ code is linked with an Ada sound package.




## required for running:

* graphics card with ample memory & updated driver that supports OpenGL version 3.3 or later;
* Windows, GNU/Linux or OSX;


## Tools required for building:

* a recent gcc compiler that supports -std=c++11;
* Xcode g++ compiler, if using OSX;



--------------------------
## Legal Mumbo Jumbo:


RufasGate itself is covered by the GNU GPL v3 as indicated in the sources:


 Copyright (C) 2020  <fastrgv@gmail.com>

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

Other beautiful hi-res skyboxes [from OpenGameArt.org] are the work of Heiko Irrgang <hi@93-interactive.com> and are licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License.  To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/ or send a letter to Creative Commons, 444 Castro Street, Suite 900, Mountain View, California, 94041, USA.  See also the accompanying file ccsa3_license.txt.



### LodePNG (png loader module)

lodepng.cpp lodepng.h
are files copyrighted by Lode Vandevenne and so marked
with all the details of their permitted uses 
near the tops of those two files.  See:
http://lodev.org/lodepng/


-------------------------------------------------------------------

## what is special about this project?

Uses fully modern OpenGL methods in C++ using textures, shaders and uniforms so as to achieve version 3.3 core profile contexts, yet compiles and runs on Windows, GNU/Linux and Mac OS-X systems.  This project serves as a testbed for learning the complexities of modern OpenGL and GLSL so that transparency has, to a certain extent, preempted elegance.  

It relies mostly on SDL2, but uses SFML audio because of its elegant audio interface.  There are examples of "fancy" fragment shaders and an environmental cubemap for reflective water in level 2.  It is very difficult to find a complete, working OGL-330-core implementation of cubemaps, such as you find here.


-------------------------------------------------------------------

## Prior Change History:

**ver 4.1.2 -- 31mar20**

* Fixed problem with incorrect PIDs on Linux sound system.


**ver 4.1.1 -- 28jan20**

* Fixed occasional sound-task related aborts (linux version).



**ver 4.1.0 -- 26jan20**

* Quantum improvement in linux portability due to omission of SFML libs.  The linux build uses an alternate sound implementation that relies on an Ada package.  It is thusly, educational to see how to call Ada from C++ in such a nontrivial example, where the important goal is enhanced linux portability.
* OSX & Windows sound still uses the proven & reliable SFML libs.


**ver 4.0.2 -- 28aug19**

* Updated to SFML v2.5.0;
* Updated to SDL2 v2.0.9;
* Moved code into ./src/;
* Reduced island graphical burden for HiDpi [Mac];
* Added 3 alternate build scripts that do not use GLEW lib or dll files.


**ver 4.0.1 -- 5mar19**

* Repaired bad DOD default that could cause aborts;
* Smoothed Xbox motion;
* Adjusted movement params;
* Improved ocean waves & foam;
* Improved lavapool;


**ver 4.0.0 -- 10nov17**

* added prebuilt executables for msWindows;
* added working build scripts for msWindows;

