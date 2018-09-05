MrModeltest2
============

C program for selecting DNA substitution models using [PAUP\*](https://paup.phylosolutions.com).


MrModeltest 2.4 README, Sept 2018

MrModeltest 2.4 by Johan A. A. Nylander.
Orignal code by David Posada, U. Vigo, Spain.

E-mail: johan.nylander\@nbis.se


Description
-----------

For performing hierarchical likelihood ratio tests and calculating approximate 
AIC and/or very approximate AICc values of the nucleotide substitution models 
currently implemented in both PAUP\*4 and MrBayes v3. Version 2.4 also does some 
model averaging of the parameter estimates obtained by PAUP\*.

MrModeltest 2.4 is a modified version of David Posada's Modeltest 3.6 (see 
Modeltest homepage). "Modified version" means that it was rewritten to compare 
24 instead of 56 models of nucleotide substitution (basically a Modeltest 
version 1.0). On the other hand, all of the 24 models can be implemented in 
MrBayes version 3. Furthermore, MrModeltest uses (by default) four different 
hierarchies for the likelihood ratio tests. The hierarchies are described in 
detail in *Posada, D. and K. A. Crandall. 2001. Selecting the best-fit model of 
nucleotide substitution. Systematic Biology, 50:580-601 (Fig. 4a-d)*.
The  hierarchies implemented in MrModeltest are also depicted in the files 
[hLRT1.jpg](doc/img/hLRT1.jpg), [hLRT2.jpg](doc/img/hLRT2.jpg), 
[hLRT3.jpg](doc/img/hLRT3.jpg), and [hLRT4.jpg](doc/img/hLRT1.jpg).

MrModeltest 2.4 are currently only able to read the output from newer ("test")
versions of PAUP\*. For users with older PAUP\* versions (< 4.0a155), version
2.3 should still work as expected.


Suggested reference
-------------------

Nylander, J. A. A. 2004. MrModeltest v2. Program distributed by the author. 
Evolutionary Biology Centre, Uppsala University.


Quick instructions
------------------

Installing the pre-build program on Windows or MacOSX

1. Find the appropriate binary file for your operating system (in the
'bin' folder) and use directly (see Running MrModeltest2 below) or, preferrably,
copy it to a location included in your PATH.

Note: The windows version is compiled and tested on Win XP.


Installing from source (on UNIX/MacOSX)

1. cd into the distribution src directory:

        cd MrModeltest2/src

2. Compile by typing (try `make -f Makefile.MACOSX` if `make` fails on the Mac):

        make

3. The binary file `mrmodeltest2` can then be run in the same directory or be 
moved somewhere on your system where you have access to it (i.e., in your PATH).


Before using MrModeltest2
-------------------------

1. Execute your data file in PAUP\*:

        exe datafile.nex;

2. Execute the file `MrModelblock` in PAUP\*. A file called `mrmodel.scores` 
will appear in the current directory. This file is the input for `mrmodeltest2`.

        exe MrModelblock;


Running MrModeltest2
--------------------

MrModeltest2 does not have a graphical user interface. Therefore, 
UNIX/Win/MacOSX users need to open a terminal ("Terminal", "Console","DOS window") and type:

    mrmodeltest2 < mrmodel.scores > out

The results are written in the 'out' file.

Note: If `mrmodeltest2` is not in your PATH, you can try to run the program by 
first `cd` in to the same directory where the binary and the `mrmodel.scores` are 
located and then type:

    ./mrmodeltest2 < mrmodel.scores > out


Disclaimer
-----------

This program is free software; you can redistribute it and/or modify it under 
the terms of the [GNU General Public License](doc/gpl.html) as published by 
the Free Software Foundation; either version 2 of the License, or (at your
option) any later version. This program is distributed in the hope that it 
will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty
of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
Public License for more details. You should have received a copy of the GNU
General Public License along with this program; if not, write to the Free
Software Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA 02111-1307,
USA. 
