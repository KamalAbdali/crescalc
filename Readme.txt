PREDICTING THE LUNAR CRESCENT'S VISIBILITY 

This Forttran program predicts whether a waxing lunar crescent would be 
visible on any particular eveining in any particular location.

The program can be compiled by GNU Fortran under Linux and MacOS  
and in the Cygwin environment on a PC.


*** COMPILE THE FORTRAN PROGRAM ***

      gfortran -o cres cres.f


*** PREPARE DATA FILE WITH DATE AND NEW MOON PHASE TIME INFO ***

Its format is described in program comments for input unit 7 data.
For predicting the visibility of the waxing crescent, the only 
relevant dates are the CE calendar dates that correspond to the 29th 
of a lunar month.

The new moon phase time has to be entered here since the program doesn't
compute it. You can find this time in any ephemeris, or get it from
the program Minaret (http://geomete.com/minaret/minar40.zip).
A sample data file is "h1437.txt".

This file should be copied to "fort.7".
      cp h1437.txt fort.7


*** PREPARE A FILE WITH DATA OF LOCATIONS FOR NEW MOON OBSERVATION ***

This file is to be read as Fortran's standard input (same as unit 5).
See its format description in program comments for input unit 5 data.
A sample data file is "cities.txt".


*** RUN THE COMPLIED EXECUTABLE ***

      ./cres  < cities.txt  > out.txt


*** WHAT ABOUT THE CARRIAGE CONTROL CHARACTERS IN THE OUTPUT FILE? ***

The program outputs the old "printer carriage control" characters:
"1" in column 1 to skip a page, "0" in column 1 to skip a line, and 
blank in column 1 to indicates a normal line. Ignore or process them!
If these harmless remanants of the past bother you, then can write a 
little program to take care of these characters.

