# Configuration properties

The DITA-OT uses .properties files and internal properties that store configuration settings for the toolkit and its plug-ins. Configuration properties are available to both Ant and Java processes, but unlike argument properties, they cannot be set at run time.

When DITA-OT starts the Ant process, it looks for property values in the following order and locations:

1.  Any property passed to Ant from the command line with -Dproperty or --property=value
2.  A custom property file passed with --propertyfile
3.  A local.properties file in the root directory of the DITA-OT installation
4.  The lib/org.dita.dost.platform/plugin.properties file
5.  The configuration.properties file

If a given property is set in multiple places, the first value “wins” and subsequent entries for the same property are ignored.

You can use this mechanism to override DITA-OT default settings for your environment by passing parameters to the dita command with --property=value, or using entries in .properties files.

-   **[The local.properties file](../parameters/local-properties-file.md)**  
A local.properties file in the root directory of the DITA-OT installation can be used to override the default values of various DITA-OT parameters.
-   **[The plugin.properties file](../parameters/plugin-properties-file.md)**  
The plugin.properties file is used to store configuration properties that are set by the plug-in installation process.
-   **[The configuration.properties file](../parameters/configuration-properties-file.md)**  
The configuration.properties file controls certain common properties, as well as some properties that control PDF processing.
-   **[Internal Ant properties](../parameters/internal-ant-properties.md)**  
Reference list of Ant properties used by DITA-OT internally.

**Parent topic:** [Setting DITA Open Toolkit parameters](../parameters/index.md)

