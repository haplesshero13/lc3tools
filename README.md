LC3 Tools
=========
This is a cleaned-up version of the LC-3 tools which has been modified slightly to install to `~/.lc3`, so it can be used alongside the [LCC-LC3 C Compiler](https://github.com/haplesshero13/lcc-lc3).

##Recent Changes
####May 2012

*Avery Yen*

Modified Makefile.def and configure to automatically install to `~/.lc3`. Also, `make install` now only installs executables. This is because having documents like a Makefile and a README in your executable path is a Bad Idea. The Makefile, README, and other documents previously installed by `make install` already live in the source directory. There doesn't seem to be any reason to make them live in two places.

Additionally, the lc3os and symbol tables now get installed to `~/.lc3/lc3os/`. This prevents them from being in the executable path, once again. lc3sim.c was modified to reflect this change.

## Description of Contents

The LC-3 tools package contains the lc3as assembler, the lc3sim simulator,
and lc3sim-tk, a Tcl/Tk-based GUI frontend to the simulator. All tools,
code, etc., were developed by Steven S. Lumetta on his own time with his
own resources for use in teaching classes based on the textbook by 
Yale N. Patt and Sanjay J. Patel entitled, *Introduction to Computing
Systems: From Bits & Gates to C & Beyond,* second edition, McGraw-Hill,
New York, New York, 2004, ISBN-0-07-246750-9.

The contents of the LC-3 tools distribution, including sources, management
tools, and data, are Copyright (c) 2003 Steven S. Lumetta.

The LC-3 tools distribution is free software covered by the GNU General 
Public License, and you are welcome to modify it and/or distribute copies 
of it under certain conditions. The file COPYING (distributed with the
tools) specifies those conditions. There is absolutely no warranty for 
the LC-3 tools distribution, as described in the file NO_WARRANTY (also
distributed with the tools).

## Necessary Tools

Installation requires versions of gcc (the Gnu C compiler),
flex (Gnu's version of lex), and wish (the Tcl/Tk graphical shell).
All of these tools are available for free from many sources.
If you have Gnu's readline installed, the configure script should
find it and use it for the command line version of the simulator.
I don't currently use the history feature, but will add it...someday.

Other necessary but more standard tools include uname, rm, cp, mkdir, 
and chmod.

Currently, the configure script searches only a few directories.
If your binaries are in a reasonable place that I overlooked, send
me a note and I'll add it to the default list. If you have 
idiosyncratic path names (e.g., the name of your fileserver in your
path), you will have to add the correct paths to the search path at 
the top of the configure script yourself.

N.B. I have installed the package on Cygwin, Solaris, and Linux
machines. Linux has been used by 2-3 other schools at the time of
the 0.5 release; Cygwin is stable on my home machine; Solaris GUI
version caused me grief last time I launched it, but I haven't
had time to investigate.


## Installation Instructions

###Windows
* Install Cygwin, making sure you have gcc, flex, and wish, as well as uname, rm, cp, mkdir, and chmod
* Now follow the general UNIX install

###Mac OS X 10.5+
* Install Xcode and the Xcode Developer Tools/Command Line Tools
* Check that you have gcc by typing `gcc --version`. If you get a message similar to `i686-apple-darwin11-llvm-gcc-4.2 (GCC) 4.2.1 (Based on Apple Inc. build 5658) (LLVM build 2336.9.00)` then you are all set.
* Now follow the general UNIX install

###Linux
* Install gcc, flex, and wish, using apt-get, yum, or whatever package manager your Linux system uses.
* Now follow the general UNIX install

###General UNIX
The LC-3 tools package is designed to work as either a personal or 
administrative installation on various flavors of Unix, including
Windows NT-based systems with appropriate support (e.g., Cygwin).

First, decide where the binaries and LC-3 OS code should be installed.

* If you want it in the ~/.lc3 directory, type `configure`.
* If you want it in a different directory, say `/usr/bin`, type `configure --installdir` `/usr/bin` replacing `/usr/bin` with the desired directory.

Then type `make install`.

## Maintainers
* Sean Smith (Dartmouth College)
* Avery Yen

## Original Author
* Steven S. Lumetta (lumetta@uiuc.edu).
