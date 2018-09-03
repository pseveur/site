# Installing the DITA Open Toolkit

The DITA-OT distribution package can be installed on Linux, macOS, and Windows. It contains everything that you need to run the toolkit except for Java.

-   Ensure that you have a Java Runtime Environment \(JRE\) or Java Development Kit \(JDK\), version 8 or later installed.

    You can download the Oracle JRE or JDK from [oracle.com/technetwork/java](http://www.oracle.com/technetwork/java/javase/downloads).

-   If you want to generate HTML Help, ensure that you have HTML Help Workshop installed.

    You can download the Help Workshop from [msdn.microsoft.com](http://msdn.microsoft.com/en-us/library/windows/desktop/ms669985%28v=vs.85%29.aspx).


1.   Download the dita-ot-3.1.2.zip package from the project website at [dita-ot.org/download](https://www.dita-ot.org/download). 
2.   Extract the contents of the package to the directory where you want to install the DITA-OT. 
3.   Add the absolute path for the bin directory to the PATH system variable. 

    This defines the necessary environment variable to run the dita command from the command line.

    **Tip:** This step is recommended, as it allows the the dita command to be run from any location on the file system and makes it easier to transform DITA content from any folder.


-   **[Prerequisite software](../topics/prerequisite-software.md)**  
The prerequisite software that the DITA-OT requires depends on the types of transformations that you want to use.
-   **[Checking the DITA-OT version number](../topics/determining-version-of-ditaot.md)**  
You can determine the version number of the DITA Open Toolkit from a command prompt.
-   **[Building output using the dita command](../topics/first-build-using-dita-command.md)**  
You can generate output using the DITA Open Toolkit dita command-line tool. Build parameters can be specified on the command line or with .properties files.

