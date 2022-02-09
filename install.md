<h1>Notes for installing WiMDA</h1>

Three steps are required:

1) First install a 32 bit version of Ghostscript from <a href="https://www.ghostscript.com/releases/gsdnld.html" >here </a> if not already present (this is needed by the plotting package GLE). 

2) Next install the 32 bit version of the GLE plotting package that is needed for plots of model fitting. 
The current version is 4.2.5 and it can be downloaded from <a href="https://glx.sourceforge.io/downloads/downloads.html" >here </a>, 
where manuals are also available. 
A brief GLE user guide can also be found <a href="http://users.ox.ac.uk/~sjb/gle/glemanual/" >here</a>.

3) Finally install the WiMDA package itself, which is found in the file <a href=download/currentwimda/WiMDAinstall.zip >WiMDAinstall.zip</a>. 
This includes the main program wimda.exe and various dll libraries that are needed to read NeXus format data files. 
Extract these files into a new folder in a convenient location. 

When wimda.exe is run for the first time the path to gle.exe will be checked and may need to be set up to point to the right location 
(typically C:\Program Files (x86)\Gle4\bin\gle.exe in a standard GLE installation).

<h2>User Relaxation and Model Functions</h2>

Libraries of user relaxation and model functions for WiMDA can be compiled externally as dynamic link libraries. 
Template files for compiling user fit function libraries are available. 
These require a 32 bit Delphi Pascal compiler, available from Embarcadero as a <a href="https://www.embarcadero.com/products/delphi/starter" >Free Community Edition</a>. 
An alternative Delphi-compatible free compiler that is not linked to a commercial company is the <a href="https://www.freepascal.org/">Free Pascal Compiler (FPC)</a>. 
Example templates for other languages such as Fortran and C may also be available on request.

<h2>User Relaxation Functions (Delphi)</h2>

The files needed are the Delphi source template file musrfunctions.dpr which needs to link with musrfunctionunit.dcu; 
depending on the version of Delphi, you may also need to rebuild with the corresponding source file musrfunctionunit.pas. 
These three files can be downloaded as <a href=/download/userfunctions/MusrFunctionUnit.zip >MusrFunctionUnit.zip</a>. 
The compiled library musrfunctions.dll should be placed in the fit library directory.

<h2>User Model Functions (Delphi)</h2>

The files needed are the Delphi source template file userfit.dpr which needs to link with userunit.dcu; 
depending on the version of Delphi, you may also need to rebuild using the corresponding source files userunit.pas and fittyps.pas. 
These four files can be downloaded as <a href=/download/userfunctions/UserUnit.zip >UserUnit.zip</a>. 
The compiled libraries must be have "fit" as the last three characters of the name and the compiled dll should be placed in the fit library directory.

<h2>User Relaxation and Model Functions (Free Pascal Compiler)</h2>

The files needed for use with the basic command line compiler can be downloaded as <a href=/download/fpc_files/fpc_files.zip >fpc_files.zip </a>. 
The compiler option -Mdelphi must be used. However it is recommended to use the FPC via the Lazarus IDE.

<h2>Using the Lazarus IDE</h2>

A modern integrated development environment called <a href="https://www.lazarus-ide.org/" >Lazarus</a> is available for use with FPC. 
The template WiMDA user function files for use with Lazarus are found <a href=/download/fpc_files/Lazarus_files.zip >here</a>.

To build the template dll libraries in the Lazarus IDE:

Open the Lazarus project file musrfunctions.lpi using `Project/Open Project` then compile it using `Run/Build`. 
Then repeat for UserFit.lpi.
