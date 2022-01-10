# OWON-HDS272S
Some information about the OWON Scope meter 

The HDS200_CVS_Calculater is useful if you are trying to analyse a saved waveform from the OWON using Excel or LibreOffice Calc. It calculates some values that help making sense of the data. 


The two left most columns are Time/Div and Samples per second.  These are the ones that determine which row to use. For convenience I put them here in the form they appear on the scope’s screen but for use in calculations, they are duplicated, this time just as numbers, in columns C and D. 
The next column E tells you how long in seconds each sample is, 
Column F shows how long it takes to fill the whole 8K memory 
Column G shows how long it takes to fill the whole screen. This number is smaller than the memory,  sometimes much smaller because as I showed earlier the faster the timebase setting the smaller the screen gets. 
This is also reflected in column H which shows the screen length in entries in the memory. It is mostly around 6000 entries but at the fastest timebase, the whole of the screen spans just 15 entries in the 8000 entries memory. 

So far these columns are just static, driven directly by the selected timebase which also automatically determines the sampling rate. 

The next three columns show where the screen starts, the mid point of the screen and the end point in terms of their index value in the memory while column M shows the time value associated with the most left, zero index of the memory. 

These 4 columns are driven by the values you enter into the green and red fields, which are the only fields that should be changed. Make sure that these are normally both set to zero. 

The green field is to be used when the scope is in the run mode. Here you enter your selected trigger delay if isn’t zero. What this does  is to calculate a new value for colum M, the time associated with the zero index of  the memory. 

You can use the values of column E and M to associate a time value with each memory position 

If you are in the stop mode you can use the red column to type in the value used for shifting the position of the screen window and this will calculate the new screen index values for left, middle and right.

Notes:
1. This spreadsheet assumes the memory size was selected to be 8K on the scope 
2. There is no error checking. It is your responsibility to only type in those values and ranges that you were also able to enter on the OWON 
3. It is entirely possible that one of the calculated screen borders can lie outside the valid range of 0 .. 7999. This is normal. The scope simply shows nothing in these out-of-bounds areas. 
