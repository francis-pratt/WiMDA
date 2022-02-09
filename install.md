Notes for installing WiMDA

Three steps are required:

1) First install a 32 bit version of the postscript software <a href="https://www.ghostscript.com/releases/gsdnld.html" >Ghostscript</a> if not already present (this is needed by the plotting package GLE). 

2) Next install the GLE plotting software that is needed to plot the results of fit parameter modelling. 
The current version is 4.2.5 and the 32 bit version should be downloaded from: http://glx.sourceforge.net/, where manuals are also available. 
A brief GLE user guide can also be found at: http://users.ox.ac.uk/~sjb/gle/glemanual/.

3) Finally install the WiMDA package itself, which is found in the file WiMDAinstall.zip. 
This includes the main program wimda.exe and the various dll libraries that are needed to read NeXus format data files. 
Extract these files into a new folder in a convenient location. 

When wimda.exe is run for the first time the path to gle.exe will be checked and may need to be set up to point to the right location 
(typically C:\Program Files (x86)\Gle4\bin\gle.exe in a standard installation).

User Relaxation and Model Functions

Libraries of user relaxation and model functions for WiMDA can be compiled externally as dynamic link libraries. 
Template files for compiling user fit function libraries are now available. 
These require a 32 bit Borland Delphi Pascal compiler (i.e. version 2 or later). 
If you do not have access to a Borland compiler, then a free alternative is: Free Pascal compiler. 
Example templates for various Fortran and C compilers may also be made available on request.

User Relaxation Functions (Delphi)

The files needed are the Delphi source template file musrfunctions.dpr which needs to link with musrfunctionunit.dcu; 
depending on the version of Delphi you may also need to rebuild with the corresponding source file musrfunctionunit.pas. 
These three files can be downloaded as MusrFunctionUnit.zip. The compiled library musrfunctions.dll should be placed in the fit library directory.

User Model Functions (Delphi)

The files needed are the Delphi source template file userfit.dpr which needs to link with userunit.dcu; 
depending on the version of Delphi you may also need rebuild using the corresponding source files userunit.pas and fittyps.pas. 
These four files can be downloaded as UserUnit.zip. 
The compiled libraries must be have "fit" as the last three characters of the name and the compiled dll should be placed in the fit library directory.

User Relaxation and Model Functions (Free Pascal Compiler)

The files needed for use with the basic command line compiler can be downloaded as: User Functions. 
The compiler option -Mdelphi must be used.

A modern integrated development environment called Lazarus is now available for use with FPC, it can be installed from here. 
The template WiMDA user function files for use with Lazarus are found here.

To build the template dll libraries in the Lazarus IDE:

Open the Lazarus project file musrfunctions.lpi using `Project/Open Project` then compile it using `Run/Build`. 
Then repeat for UserFit.lpi.
