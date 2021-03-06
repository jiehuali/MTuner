![MTuner logo](https://github.com/milostosic/MTuner/blob/master/img/logo.png)

[![Build Status](https://travis-ci.org/milostosic/MTuner.svg?branch=master)](https://travis-ci.org/milostosic/MTuner)
[![Build status](https://ci.appveyor.com/api/projects/status/fo9uy9h3bcka20kk?svg=true)](https://ci.appveyor.com/project/milostosic/MTuner)
[![License](https://img.shields.io/badge/license-BSD--2%20clause-blue.svg)](https://github.com/milostosic/MTuner/blob/master/LICENSE)

**MTuner** is a C/C++ memory profiler and memory leak finder for Windows, PlayStation 4 and 3, Android and other platforms.

**MTuner** utilizes a novel approach to memory profiling and analysis, keeping entire time-based history of memory operations. This gives an unique insight in memory related behavior of your software by making queries over the entire data set.

While **MTuner** was created for profiling C/C++ applications, it is possible to profile memory for programs written in other languages as long as there is corresponding debug symbol information. Users can convert DMD CodeView/DWARF debug symbols to PDB format using [cv2pdb](https://github.com/rainers/cv2pdb).

![MTuner screenshot](https://github.com/milostosic/MTuner/blob/master/img/mtuner_screenshot.png)

Source Code
======

You can get the latest source code by cloning it from github:

      git clone https://github.com/milostosic/MTuner.git 

Download
======

Binaries can be downloaded from [releases](https://github.com/milostosic/MTuner/releases) page  

Documentation
======

MTuner documentation can be found [here](https://milostosic.github.io/MTuner/).  

Dependencies
======

MTuner uses [Qt](https://www.qt.io/) framework for user interface.

Dependencies can be obtained by cloning the following repositories:

	git clone https://github.com/milostosic/build.git
	git clone https://github.com/milostosic/rbase.git
	git clone https://github.com/milostosic/rdebug.git
	git clone https://github.com/milostosic/rmem.git
	git clone https://github.com/milostosic/rqt.git
	git clone https://github.com/milostosic/MTunerCmd.git
	git clone https://github.com/milostosic/MTunerDLL.git
	git clone https://github.com/milostosic/MTunerInject.git

DIA (Debug Interface Access) SDK - **Windows only**

	git clone https://github.com/milostosic/DIA.git 

Build
======

MTuner build system is based on [GENie](https://github.com/bkaradzic/GENie) and [build](https://github.com/milostosic/build) in order to dramatically simplify managing build configurations and dependencies.

After cloning the repository and dependencies, here are the steps to build MTuner.

**MinGW**

	$ cd MTuner/genie
	$ genie --gcc=mingw-gcc gmake
	$ cd ../../.build/windows/mingw-gcc/MTuner/projects/
	$ make
MINGW environment variable must be set and point to the MinGW installation directory.  
Tested with [TDM64 MinGW](http://tdm-gcc.tdragon.net/download) using [OpenMP package](http://sourceforge.net/projects/tdm-gcc/files/TDM-GCC%205%20series/5.1.0-tdm64-1/gcc-5.1.0-tdm64-1-openmp.zip/download)

**Visual Studio**

	> cd MTuner/genie
	> genie vs2015
Solution will be located here: *{Clone root}/.build/windows/vs2015/projects/MTuner/MTuner.sln*

NB: building Qt based projects with [build](https://github.com/milostosic/build) requires additional dependencies:

	Lua
	Lua lfs module

Environment variables are used to locate Qt installation, example:

	set QTDIR_VS2017_x86=C:\<some_path>\Qt\5.13.0\msvc2017_64 *
	set QTDIR_VS2017_x64=C:\<some_path>\Qt\5.13.0\msvc2017_64

Note that Qt deprecated 32bit builds, hence both variables point to same location.

Latest release made with: Visual Studio 2017 Community edition, Qt 5.13.0 and Lua 5.1.4

Author
======

The author of **MTuner** is Milos Tosic  
[ <img src="https://github.com/milostosic/build/raw/gh-pages/images/twitter.png">](https://twitter.com/milostosic)[ <img src="https://github.com/milostosic/build/raw/gh-pages/images/mail.png">](mailto:milostosic77@gmail.com)  

License (BSD 2-clause)
======

<a href="http://opensource.org/licenses/BSD-2-Clause" target="_blank">
<img align="right" src="http://opensource.org/trademarks/opensource/OSI-Approved-License-100x137.png">
</a>

	Copyright (c) 2019 Milos Tosic. All rights reserved.
	
	https://github.com/milostosic/MTuner
	
	Redistribution and use in source and binary forms, with or without
	modification, are permitted provided that the following conditions are met:
	
	   1. Redistributions of source code must retain the above copyright notice,
	      this list of conditions and the following disclaimer.
	
	   2. Redistributions in binary form must reproduce the above copyright
	      notice, this list of conditions and the following disclaimer in the
	      documentation and/or other materials provided with the distribution.
	
	THIS SOFTWARE IS PROVIDED BY COPYRIGHT HOLDER ``AS IS'' AND ANY EXPRESS OR
	IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF
	MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO
	EVENT SHALL COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT,
	INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
	(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
	LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
	ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
	(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF
	THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE. 
