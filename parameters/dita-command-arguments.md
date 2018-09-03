# Arguments and options for the dita command

The dita command takes mandatory arguments to process DITA content, manage plug-ins, or print information about the command. Options can be used to modify the command behavior or specify additional configuration parameters.

## Usage

 

>  `**dita** ` `**--input=** ` *file* `**--format=** ` *name* \[ *options* \]

 

>  `**dita** ` `**--install** ` \[ \{ *filename* *| URL* \} \]

 

>  `**dita** ` `**--uninstall** ` *id* 

 

>  `**dita** ` `**--help** ` 

 

>  `**dita** ` `**--version** ` 

**Note:** Most dita command options support several syntax alternatives. All options can be specified with a GNU-style option keyword preceded by two hyphens. In many cases, Unix-style single-letter options \(preceded by a single hyphen\) are also available for backwards compatibility.

## Arguments

-   ** --input=file -i file **

    Specifies the master file for your documentation project. This argument corresponds to the common parameter args.input. Typically this is a DITA map, however it also can be a DITA topic if you want to transform a single DITA file. The path can be absolute, relative to args.input.dir, or relative to the current directory if args.input.dir is not defined.

-   ** --format=name -f name **

    Specifies the output format \(transformation type\).

    This argument corresponds to the common parameter transtype.

    You can create plug-ins to add new output formats; by default, the following values are available:

    -   dita
    -   eclipsehelp
    -   html5
    -   htmlhelp
    -   markdown, markdown\_gitbook, and markdown\_github
    -   pdf
    -   tocjs
    -   troff
    -   xhtml
    **Tip:** See [DITA-OT transformations \(output formats\)](../resources/../topics/output-formats.md) for sample command line syntax and more information on each transformation.

-   ** --install filename --install URL**

    Install a single plug-in from a local ZIP file or from a URL.

-   ** --install **

    If no filename or URL argument is provided, the installation process reloads the current set of plug-ins from the plugins directory. This approach can be used to add or remove multiple plug-ins at once, or any individual plug-ins you have already copied to \(or removed from\) the plugins directory.

-   ** --uninstall id **

    Uninstall a plug-in with the specified ID.

    **Attention:** The --uninstall option also removes the corresponding subdirectory from the plugins folder.

-   ** --help -h **

    Print command usage help.

-   ** --version **

    Print version information and exit.


## Options

-   ** --output=dir -o dir **

    Specifies the path of the output directory; the path can be absolute or relative to the current directory.

    This argument corresponds to the common parameter output.dir. By default, the output is written to the out subdirectory of the current directory.

-   ** --filter=file **

    Specifies filter file\(s\) used to include, exclude, or flag content.

    This argument corresponds to the common parameter args.filter. Relative paths are resolved against the current directory and internally converted to absolute paths.

-   ** --temp=dir -t dir **

    Specifies the location of the temporary directory.

    This argument corresponds to the common parameter dita.temp.dir.

-   ** --verbose -v **

    Verbose logging.

-   ** --debug -d **

    Debug logging.

-   ** --logfile=file -l file **

    Write logging messages to a file.

-   ** --parameter=value -Dparameter=value **

    Specify a value for a DITA-OT or Ant build parameter.

    The GNU-style --parameter=value form is only available for parameters that are configured in the plug-in configuration file; the Java-style -D form can also be used to specify additional non-configured parameters or set system properties.

    Parameters not implemented by the specified transformation type or referenced in a .properties file are ignored.

    **Tip:** If you are building in different environments where the location of the input files is not consistent, set args.input.dir with the dita command and reference its value with `${args.input.dir}` in your .properties file.

-   ** --propertyfile=file **

    Use build parameters defined in the referenced .properties file.

    Build parameters specified on the command line override those set in the .properties file.


**Parent topic:** [Setting DITA Open Toolkit parameters](../parameters/index.md)

**Related information**  


[Building output using the dita command](../topics/build-using-dita-command.md)

[DITA-OT parameters](../parameters/parameters_intro.md)

[Internal Ant properties](../parameters/internal-ant-properties.md)

[Setting build parameters with .properties files](../topics/using-dita-properties-file.md)

