# Building output using the dita command

You can generate output using the DITA Open Toolkit dita command-line tool. Build parameters can be specified on the command line or with .properties files.

1.   At the command-line prompt, enter the following command: 

    ```
    dita-ot-dir/bin/dita --input=input-file --format=format \[options\]
    ```

    where:

    -   dita-ot-dir is the DITA-OT installation directory.
    -   input-file is the DITA map or DITA file that you want to process.
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
        **Tip:** See [DITA-OT transformations \(output formats\)](../resources/../topics/output-formats.md) for sample command line syntax and more information on each transformation.

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


For example, from dita-ot-dir/docsrc/samples, run:

```
dita --input=sequence.ditamap --format=html5 \
     --output=output/sequence \
     --args.input.dir=dita-ot-dir/docsrc/samples \
     --propertyfile=properties/sequence-html5.properties
```

This builds sequence.ditamap to HTML5 output in output/sequence using the following additional parameters specified in the properties/sequence-html5.properties file:

```
# Don't generate headings for sections within task topics:
args.gen.task.lbl = NO

# Directory that contains the custom .css file:
args.cssroot = ${args.input.dir}/css/

# Custom .css file used to style output:
args.css = style.css

# Copy the custom .css file to the output directory:
args.copycss = yes

# Location of the copied .css file relative to the output:
args.csspath = branding

# Generate a full navigation TOC in topic pages:
nav-toc = full

# Base name of the Table of Contents file:
args.xhtml.toc = toc
```

Usually, you will want to specify a set of reusable build parameters in a .properties file.

-   **[Setting build parameters with .properties files](../topics/using-dita-properties-file.md)**  
Usually, DITA builds require setting a number of parameters that do not change frequently. You can reference a set of build parameters defined in a .properties file when building output with the dita command. If needed, you can override any parameter by specifying it explicitly as an argument to the dita command.
-   **[Migrating Ant builds to use the dita command](../topics/migrating-ant-to-dita.md)**  
Although Ant builds are still supported in the DITA Open Toolkit, you might want to switch to use the new dita command.

**Parent topic:** [Building output](../topics/building-output.md)

**Related information**  


[Arguments and options for the dita command](../parameters/dita-command-arguments.md)

[Accessing help for the dita command](../topics/dita-command-help.md)

[DITA-OT parameters](../parameters/parameters_intro.md)

[Internal Ant properties](../parameters/internal-ant-properties.md)

