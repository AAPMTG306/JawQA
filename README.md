# TG-306 Dynamic Jaw QA Analysis Tool
tools and codes for Tomotherapy/Radixact dynamic Jaw QA analysis

Disclaimer:

This is an independently developed Tomotherapy/Radixact Dynamic Jaw QA analysis tool. The source code was also provided for your reference. However, the Author disclaims any warranty or liability relating to the use of this tool. Rigorous acceptance and commissioning work is required for clinical adoption.

Please report bugs or provide feedbacks to quanchen@gmail.com.


1. Files to deploy and package
Files contained in this package

===============================

-analyTomoDJSweep.exe

-TomoDJSweepQA_install.exe

-analyTomoDJSweep.m

-readTEMScsv.m

-SampleInput.csv

-readme.txt

2. Install the application
a. If you have Matlab. Copy the analyTomoDJSweep.m and readTEMScsv.m to your Matlab path you can skip the run time library installation steps in this section.

b. If you don't have Matlab on your computer. Run TomoDJSweepQA_install.exe to install the application. The program will connect to the internet to download and install the MATLAB Runtime library for R2019a from Mathworks website.

NOTE: You will need administrator rights to run the MATLAB Runtime installer, and the computer needs to have an internet connection.

c. If the computer is not connected to the internet, you can download the the Windows version of the MATLAB Runtime for R2019a from the following link on the MathWorks website:

http://www.mathworks.com/products/compiler/mcr/index.html

Note the version R2019a should be selected. Other versions (newer or older) will not work. Copy the installation package to the computer you want to install.

3. Test run the application
If you have Matlab installed, you can run this command in Matlab:

analyTomoDJSweep('SampleInput.csv', 'Results.csv');

Or if the MATLAB Runtime library is installed, you can run analyTomoDJSweep.exe with the following command in command window:

analyTomoDJSweep.exe SampleInput.csv Results.csv

Note that you may need to modify the command above to add the path to these files.

A file Results.csv will be created. Also, plots comparing discrete and continuous jaw sweep for J7 jaw setting were created as J7SweepRawComp.png and J7SweepShiftedComp.png. Slight shift along the time/position axis was performed for a better alignment between the discrete vs continuous jaw sweep.

The Results.csv shows the analyzed results. The 3rd row "Time Skew" is used to satisfy the TG306 Jaw timing test. The tolerance is within 0.1 second of 480 seconds. The row 4-8 is used to satisfy the TG306 Jaw speed test. The tolerance is within 2% of the elapsed time recorded as baseline. The row 10 (or J7SweepShiftedComp.png) is used to satisfy the TG306 Continuous jaw sweep test.

4. Analyzing your Jaw Sweep data
Once you got a good result from the provided SampleInput.csv. You can start to analyze your own data.

!IMPORTANT! Make sure you use channel 8 of your tomoElectrometer for the TQA Jaw Sweep module. Please refer to the TQA manual for details.

Replace the SammpleInput.csv with the name and path of your Jaw Sweep data in the command above.


