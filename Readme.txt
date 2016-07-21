This 30-year old program for predicting the crescent's visibility still works!
It ran successfully under Linux and MacOS and in the Cygwin environment on a PC. 

*** Use the GNU FORTRAN compiler to compile the program ***
      gfortran -o cres cres.f

*** Prepare a file with date and new moon phase time data *** 
The description of its format is in program comments for input unit 7 data.
For predicting the visibility of the waxing crescent, the only relevant dates 
are the CE calendar dates that correspond to the 29th of a lunar month.
The new moon phase has to be input here, since the program doesn't
compute this time. You can find this time from any ephemeris, or
get it from the program Minaret (http://geomete.com/minaret/minar40.zip).
A sample is in the file "h1437".

This file should be copied to "fort.7".
      cp h1437 fort.7


*** Prepare a file with data of locations for new moon observation ***
It is to be read in Fortran's standard input (same as unit 5).
See its format description in program comments for input unit 5 data.
A sample is in the file "cities".

*** Run the program and write the output on the file "out.lpr" ***
      ./cres  < cities  > out.lpr


*** Ignore or process the carriage control characters in the output file ***
The program outputs old "printer carriage control" characters:
"1" in column 1 skips a page, "0" in column 1 skips a line, and 
blank in column 1 indicates a normal line. If these harmless remanants of the 
past bother you, then write a little program to take care of these characters.

