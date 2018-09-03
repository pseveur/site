# The configuration.properties file

The configuration.properties file controls certain common properties, as well as some properties that control PDF processing.

The contents of the config/configuration.properties file are added to the DITA-OT configuration in the `dost-configuration.jar` file when the plug-in integration process runs. The following properties are typically set in this file:

-   **otreleaseotversion**

    The DITA-OT release number and maintenance version stored here are read when version information is requested on the commmand line via dita --version.

-   **default.cascade**

    Specifies the processing default value for the DITA 1.3 `@cascade` attribute, which determines how map-level metadata attributes are applied to the children of elements where the attributes are specified. DITA-OT uses the merge value by default for backwards compatibility with DITA 1.2 and earlier.

    **Warning:** This property can only be set in configuration.properties and should not be modified.

-   **temp-file-name-scheme**

    This setting specifies the name of the Java class that defines how the source URL of a topic is mapped to the URL of the temporary file name. The current default method uses a 1:1 mapping, though future implementations may use alternative approaches such as hashes or full absolute paths as file names.

    **Warning:** This property can only be set in configuration.properties and should not be modified.

-   **cli.color**

    Specifies whether the dita command prints colored output on the command line console. When set to true, error messages in dita command output will appear in red on terminals that support [ANSI escape codes](https://en.wikipedia.org/wiki/ANSI_escape_code), such as on Linux or macOS. Set to false to disable the color. \(Colored output is not supported on Windows consoles such as cmd.exe or PowerShell\).

-   **plugindirs**

    A semicolon-separated list of directory paths that the DITA-OT searches for plug-ins to install; any relative paths are resolved against the DITA-OT base directory. Any immediate subdirectory that contains a plugin.xml file is installed.

-   **plugin.ignores**

    A semicolon-separated list of directory names to be ignored during plug-in installation; any relative paths are resolved against the DITA-OT base directory.

-   **plugin.order**

    Defines the order in which plug-ins are processed. In XML catalog files, the order of imports is significant. If multiple plug-ins define the same thing \(differently\), the first catalog entry “wins”. DITA-OT uses this property to define the order in which catalog entries are written. This mechanism is currently used to ensure that DITA 1.3 grammar files take precedence over their DITA 1.2 equivalents.

-   **org.dita.pdf2.i18n.enabled**

    Enables internationalization \(I18N\) font processing to provide per-character font selection for FO renderers that do not support the `font-selection-strategy` property \(such as Apache FOP\).

    When this feature is enabled, DITA-OT uses a font mapping process that takes the content language into consideration. The mapping process uses configuration files for each language to define characters that should be rendered with certain logical fonts, and font mappings that associate each logical font to physical font files.

    The following values are allowed:

    -   true \(default\) — Enables font mapping
    -   false — Disables font mapping
    **Tip:** If you don’t use custom character mappings, turning off font mapping makes it easier to define custom fonts simply by changing font names in the XSL attributes files of your custom PDF plug-in. For details, see [Font configuration in PDF2](http://www.elovirta.com/2016/02/18/font-configuration-in-pdf2.html).


**Parent topic:** [Configuration properties](../parameters/configuration-properties.md)

**Related information**  


[DITA 1.3 specification: Cascading of metadata attributes in a DITA map](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part1-base/archSpec/base/cascading-in-a-ditamap.html#cascading-in-a-ditamap)

[Example: How the @cascade attribute functions](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part1-base/archSpec/base/example-how-cascade-att-functions.html)

[Font configuration in PDF2](http://www.elovirta.com/2016/02/18/font-configuration-in-pdf2.html)

