# Cleave_angle_analysis_final
This code will measure all the cleave angles of each fiber 

The code will read the .mat surface files from the EQuIP bucket drive. For each file it will measure the angle for mutliple cross sections to determine the steepest angle and hence the approximate fiber face angle.

The code repeats for every surface saved in the file and presents the distribution of angles for a particular cleave tension.

USE:

You only need to select the cleave tension you wich to analyse by putting the tension value in the directory command in line.... Dont forget to change the histogram title with the corresponding cleave tension in line.... You may need to replace the full file directory to direct the code to the bucket drive from whichever computer you are using.

CODE EXPLANATION:

After initialising and setting parameters, the code will find all the cross section files in the selected 'cleave tension' folder. For each file, it will take a cross section of the surface at a number of angles from the vertical center of the XY surface. The range is set between -45 and 45 deg and the number of cross sections is determined by 'n'. A second set of cross sections are extracted 90deg from the first range. Combining the two data sets gives 2*n cross sections over 180 degrees of the fiber face. The cross setions can be visualised in the 'Cleave_angle_analysis_test' file

Each cross section is then clipped at the start and end of the data by amount 'c'. This is because some of the fiber faces are too steep to be fully covered in interference fringes and hence are not fully re-constructed. The cros section the contains false data at the edges which skew the angle measurement. The remaining data are fitted to a linear plot to determine the angle. The value of 'c' is chosen to cover most cases, but this can be inspected in the 'Cleave_angle_analysis_test' file.

This is repeated for each cross section and the absolute maximum of the angles is output. It would be more accurate to fit a sin curve to the data, but the precision given by the maxiumum value will suffice.

This whole process is repeated for each file in the folder and the results are combined into a histogram given at the bottom. The code also outputs the sample size.
