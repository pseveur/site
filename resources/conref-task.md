# Conref file for tasks

DITA-OT releases follow [semantic versioning](https://semver.org) guidelines. Version numbers use the `major.minor.patch` syntax, where major versions may include incompatible API changes, minor versions add functionality in a backwards-compatible manner and patch versions are maintenance releases that include backwards-compatible bug fixes.

Custom plug-ins developed for a previous major version may require changes to work correctly with recent toolkit versions. Most plug-ins should be compatible with subsequent minor and patch versions of the major release for which they were originally developed.

-   **Standard Path / Directory Names**

    dita-ot-dir

    dita-ot-dir/bin/dita

    dita-ot-dir/docsrc/samples

-   **Plug-In Info**

    -   plug-in-id is the unique ID of the plug-in, as defined in the plug-in's configuration file \(plugin.xml\).
    -   plug-in-zip is the filename or URL of the plug-in's distribution ZIP file \(optional\).
    -   If no filename or URL argument is provided, the installation process reloads the current set of plug-ins from the plugins directory. This approach can be used to add or remove multiple plug-ins at once, or any individual plug-ins you have already copied to \(or removed from\) the plugins directory.
    -   **Attention:** The --uninstall option also removes the corresponding subdirectory from the plugins folder.


1.    Download the dita-ot-3.1.2.zip package from the project website at [dita-ot.org/download](https://www.dita-ot.org/download).  
2.   Open a command prompt or terminal session, and then change to the directory where the DITA Open Toolkit is installed. 

    -   dita-ot-dir is the DITA-OT installation directory.
    -   input-file is the DITA map or DITA file that you want to process.
    -    format is the output format \(transformation type\). This argument corresponds to the common parameter transtype. Use the same values as for the transtype build parameter, for example html5 or pdf.

    -    format is the output format \(transformation type\). This argument corresponds to the common parameter transtype. Use the same values as for the transtype build parameter, for example html5 or pdf.

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
        **Tip:** See [DITA-OT transformations \(output formats\)](../topics/output-formats.md) for sample command line syntax and more information on each transformation.

    -   \[options\] include the following optional build parameters:
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

    If processing is successful, nothing is printed in the terminal window. The built output is written to the specified output directory \(by default, in the out subdirectory of the current directory\).

    **Tip:** Add the absolute path for dita-ot-dir/bin to the PATH environment variable to run the dita command from any location on the file system without typing the path.

3.   Extending pre-processing 

    **Tip:** For maximum compatibility with future versions of DITA-OT, most plug-ins should use the extension points that run **before** or **after** pre-processing.

    CAUTION:

    The internal order of preprocessing steps is subject to change between versions of DITA-OT. New versions may remove, reorder, combine, or add steps to the process, so the extension points **within** the preprocessing stage should only be used if absolutely necessary.


**Tip:** Copy dita-ot-dir/docsrc/samples/properties/template.properties; this template describes each of the properties you can set.

**Tip:** If you are building in different environments where the location of the input files is not consistent, set args.input.dir with the dita command and reference its value with `${args.input.dir}` in your .properties file.

