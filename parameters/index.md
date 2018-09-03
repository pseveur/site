# Setting DITA Open Toolkit parameters

 You can adjust the behavior of the DITA Open Toolkit via dita command arguments and options, DITA-OT parameters settings, and configuration properties. 

-   **[Arguments and options for the dita command](../parameters/dita-command-arguments.md)**  
The dita command takes mandatory arguments to process DITA content, manage plug-ins, or print information about the command. Options can be used to modify the command behavior or specify additional configuration parameters.
-   **[DITA-OT parameters](../parameters/parameters_intro.md)**  
Certain parameters apply to all DITA-OT transformations. Other parameters are common to the HTML-based transformations. Some parameters apply only to specific transformation types. These parameters can be passed as options to the dita command using the --parameter=value syntax or included in build scripts as Ant properties.
-   **[Configuration properties](../parameters/configuration-properties.md)**  
The DITA-OT uses .properties files and internal properties that store configuration settings for the toolkit and its plug-ins. Configuration properties are available to both Ant and Java processes, but unlike argument properties, they cannot be set at run time.

