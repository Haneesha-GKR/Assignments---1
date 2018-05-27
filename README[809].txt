-----------------------------------------------------
=== Homework 4 CS 7301: Advanced Machine Learning ===
-----------------------------------------------------
Name: Mahesh Shanbhag
Email: <email>
NetID: <netid>

Requires Java JDK version: 1.8 and above
Requires Java JRE version: 1.8 and above

Requires JAVA EJML library for matrix multiplication. (Already included and linked in the code and the JAVA class path below.)
Requires WEKA library. (Already included and linked in the code and the JAVA vlass path below.)

There are 4 text files available:

1. README.txt: This file contains installation, run time error explanation and results data. Thi file contains the installation and running instructions for EM.
2. Homework4/src/EM_DETAILED_RESULTS contains the detailed results of the EM Algorithm;
3. Homework4/REPORTS contain answers to the questions in the homework.
4. The data set for AI is contained in the 'src/dataset folder' folder and the file in .ARFF format is available in the same folder.

-----------------------------------------------------
== USAGE: HOW TO RUN THE PROGRAM / INSTALLATION ==
-----------------------------------------------------
(NOTE: PLEASE ENSURE THAT THE LOCATION OF THE DATASET IS ACCESSIBLE TO THE PROGRAM.)

To run the program the user must navigate to "src" folder where all the java files are available.

----------------------
===== EM =====
----------------------

===== RUNNING VIA SCRIPT =====
There is one script available:

1. EM.sh (USAGE: "bash EM.sh"  OR "sh EM.sh"), to run this script the following changes are required:
   a. Navigate to the 'Homework4' folder and open the 'EM.sh' file and edit the following values:
      * Replace the placeholder <DATA_SET_PATH> bash variable with full path to the EM data set file.
      * Replace the placeholder <$INITIALIZATION_TYPE> bash variable with type of parameter initializer (Valid values are 1, 2, 3 and 4).
        (The details of the values are explained below)

      * Replace the placeholder <$NUMBER_OF_CLUSTERS> bash variable with the number of clusters to be used.
      * Replace the placeholder <$INITIAL_VARIANCE_VALUE> bash variable with the initial variance value for the parameters.
      * Replace the placeholder <$IS_VARIANCE_FIXED> bash variable with 1 or 0 to indicate if the variance should be fixed through out the learning time.


   b. After the values have been changed, navigate to the 'Homework4' folder and type 'bash EM.sh' or 'sh EM.sh'

-->

===== PARAMETER INITIALIZER =====

The different types of parameter initializer are:

1. Random initial parameter initialization.
2. Normal distribution is fitted to the data and the three mean parameter values are mean, mean - 1 standard deviation and mean + 1 standard deviation.
3. Random sampling method: 10 sample set of size 100 instances are iterated 3 times each to find the best maximum likelihood and use the parameters of the corresponding result.
4. K-Means: Used K-means algorithm with K = 3, to find the best mean parameters as the initialization values for the EM algorithm parameters.

-->

===== MANUAL CODE EXECUTION ====

(NOTE THE MANUAL COMPILATIONS AND CODE EXECUTION MUST FOLLOW THE BELOW STEPS IN ORDER)
    1. Please navigate to the 'Homework4' folder and edit the following values the 'EM.sh' script is located.

    2. The following commands should be executed IN ORDER as PROVIDED.

      # Delete previously compiled .class files directory.
      1.  find ./* -type f -path "./*/*.class" | xargs -n 1 rm
      2.  rm -rf ./output

      # Directory where the output .class files are written.
      3.  mkdir output

      # Include the output file directory in the classpath and export the java class path.
      4.  export CLASSPATH=./output:./lib/weka.jar:./lib/EJML-core-0.30.jar:./lib/EJML-dense64-0.30.jar:./lib/EJML-denseC64-0.30.jar:./lib/EJML-equation-0.30.jar:./lib/EJML-simple-0.30.jar

      # Compile the code including the classpath 'CLASSPATH'
      5.  javac -Xlint:unchecked -classpath $CLASSPATH -d ./output ./*/*/*.java

      # Run the 'EMMain' class by including the required values
      6.  java Main.EMMain <DATA_SET_PATH> <INITIALIZATION_TYPE> <NUMBER_OF_CLUSTERS> <INITIAL_VARIANCE_VALUE> <IS_VARIANCE_FIXED>

-->