# Common parameters

Certain parameters apply to all transformations that are supported by the DITA Open Toolkit.

-   **args.debug**

    Specifies whether debugging information is included in the log. The allowed values are yes and no; the default value is no.

-   **args.draft**

    Specifies whether the content of <draft-comment\> and <required-cleanup\> elements is included in the output. The allowed values are yes and no; the default value is no.

    Corresponds to the XSLT parameter DRAFT in most XSLT modules.

    **Tip:** For PDF output, setting the args.draft parameter to yes causes the contents of the `titlealts` element to be rendered below the title.

-   **args.figurelink.style**

    Specifies how cross references to figures are styled in output. The allowed values are NUMBER, TITLE, and NUMTITLE.

    Specifying NUMBER results in "Figure 5"; specifying TITLE results in the title of the figure. Corresponds to the XSLT parameter FIGURELINK.

    **Note:** Support for PDF was added in DITA-OT 2.0. By default PDF uses the value NUMTITLE, which is not supported for other transformation types; this results in "Figure 5. Title".

-   **args.filter**

    Specifies filter file\(s\) used to include, exclude, or flag content. Relative paths are resolved against the DITA-OT base directory \(for backwards compatibility\) and internally converted to absolute paths.

    **Note:** The system path separator character is used to delimit individual file paths in the list of values \(semicolon ‘`;`’ on Windows, and colon ‘`:`’ on macOS and Linux\). DITAVAL files are evaluated in the order specified, so conditions specified in the first file take precedence over matching conditions specified in later files, just as conditions at the start of a DITAVAL document take precedence over matching conditions later in the same document.

-   **args.gen.task.lbl**

    Specifies whether to generate headings for sections within task topics. The allowed values are YES and NO.

     Corresponds to the XSLT parameter GENERATE-TASK-LABELS.

-   **args.grammar.cache**

    Specifies whether the grammar-caching feature of the XML parser is used. The allowed values are yes and no; the default value is yes.

    **Note:** This option dramatically speeds up processing time. However, there is a known problem with using this feature for documents that use XML entities. If your build fails with parser errors about entity resolution, set this parameter to no.

-   **args.input**

    Specifies the master file for your documentation project.

    Typically this is a DITA map, however it also can be a DITA topic if you want to transform a single DITA file. The path can be absolute, relative to args.input.dir, or relative to the directory where your project's Ant build script resides if args.input.dir is not defined.

-   **args.input.dir**

    Specifies the base directory for your documentation project.

    The default value is the parent directory of the file specified by args.input.

-   **args.logdir**

    Specifies the location where the DITA-OT places log files for your project.

    **Attention:** The args.logdir parameter is obsolete and will be removed in an upcoming version of DITA-OT. To write the log to a file, use dita --logfile=file or ant -l file to set the path to the log. Unless an absolute path is specified, the value will be interpreted relative to the current directory.

-   **args.output.base**

    Specifies the name of the output file without file extension.

-   **args.rellinks**

    Specifies which links to include in the output. The following values are supported:

    -   none – No links are included.
    -   all – All links are included.
    -   noparent – Parent links are not included.
    -   nofamily – Parent, child, next, and previous links are not included.
    For PDF output, the default value is nofamily. For all other formats, the default value is all.

-   **args.tablelink.style**

    Specifies how cross references to tables are styled. The allowed values are NUMBER, TITLE, and NUMTITLE.

    Specifying NUMBER results in "Table 5"; specifying TITLE results in the title of the table. Corresponds to the XSLT parameter TABLELINK.

    **Note:** Support for PDF was added in DITA-OT 2.0. By default PDF uses the value NUMTITLE, which is not supported for other transformation types; this results in "Table 5. Title".

-   **clean.temp**

    Specifies whether the DITA-OT deletes the files in the temporary directory after it finishes a build. The allowed values are yes and no; the default value is yes.

-   **conserve-memory**

    Conserve memory at the expense of processing speed The allowed values are true and false; the default value is false.

-   **default.language**

    Specifies the language that is used if the input file does not have the `@xml:lang` attribute set on the root element. By default, this is set to en. The allowed values are those that are defined in IETF BCP 47, [Tags for Identifying Languages](https://tools.ietf.org/html/bcp47).

-   **dita.dir**

    Specifies where the DITA-OT is installed.

-   **dita.input.valfile**

    Specifies a filter file to be used to include, exclude, or flag content.

    **Note:** Deprecated in favor of the args.filter parameter.

-   **dita.temp.dir**

    Specifies the location of the temporary directory.

    The temporary directory is where the DITA-OT writes temporary files that are generated during the transformation process.

-   **filter-stage**

    Specifies whether filtering is done before all other processing, or after key and conref processing. The allowed values are early and late; the default value is early.

    **Note:** Changing the filtering stage may produce different results for the same initial data set and filtering conditions.

-   **force-unique**

    Generate copy-to attributes to duplicate topicref elements. The allowed values are true and false; the default value is false.

    Setting this to true ensures that unique output files are created for each instance of a resource when a map contains multiple references to a single topic.

-   **generate-debug-attributes**

    Specifies whether the @xtrf and @xtrc debugging attributes are generated in the temporary files. The following values are supported:

    -   true \(default\) – Enables generation of debugging attributes
    -   false – Disables generation of debugging attributes
    **Note:** Disabling debugging attributes reduces the size of temporary files and thus reduces memory consumption. However, the log messages no longer have the source information available and thus the ability to debug problems might deteriorate.

-   **generate.copy.outer**

    Specifies whether to generate output files for content that is not located in or beneath the directory containing the DITA map file. The following values are supported:

    -   1 \(default\) – Do not generate output for content that is located outside the DITA map directory.
    -   3 – Shift the output directory so that it contains all output for the publication.
    See [Handling content outside the map directory](generate-copy-outer.md) for more information.

-   **onlytopic.in.map**

    Specifies whether files that are linked to, or referenced with a @conref attribute, generate output. The allowed values are true and false; the default value is false.

    If set to true, only files that are referenced directly from the map will generate output.

-   **outer.control**

    Specifies how the DITA-OT handles content files that are not located in or below the directory containing the master DITA map. The following values are supported:

    -   fail – Fail quickly if files are going to be generated or copied outside of the directory.
    -   warn \(default\) – Complete the operation if files will be generated or copied outside of the directory, but log a warning.
    -   quiet – Quietly finish without generating warnings or errors.
    **Warning:** Microsoft HTML Help Compiler cannot produce HTML Help for documentation projects that use outer content. The content files must reside in or below the directory containing the master DITA map file, and the map file cannot specify ".." at the start of the `@href` attributes for `topicref` elements.

-   **output.dir**

    Specifies the name and location of the output directory.

    By default, the output is written to DITA-dir/out.

-   **processing-mode**

    Specifies how the DITA-OT handles errors and error recovery. The following values are supported:

    -   strict – When an error is encountered, the DITA-OT stops processing
    -   lax \(default\) – When an error is encountered, the DITA-OT attempts to recover from it
    -   skip – When an error is encountered, the DITA-OT continues processing but does not attempt error recovery
-   **remove-broken-links**

    Remove broken related links. The allowed values are true and false; the default value is false.

-   **root-chunk-override**

    Override for map chunk attribute value.

    Acceptable values include any value normally allowed on the `@chunk` attribute. If the map does not have a `@chunk` attribute, this value will be used; if the map already has a `@chunk` attribute specified, this value will be used instead.

-   **transtype**

    Specifies the output format \(transformation type\).

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

-   **validate**

    Specifies whether the DITA-OT validates the content. The allowed values are true and false; the default value is true.


**Parent topic:** [DITA-OT parameters](../parameters/parameters_intro.md)

**Related information**  


[Eclipse help transformation](../topics/dita2eclipsehelp.md)

[HTML help transformation](../topics/dita2htmlhelp.md)

[PDF transformation](../topics/dita2pdf.md)

[XHTML transformation](../topics/dita2xhtml.md)

[Setting parameters for custom HTML](../topics/html-customization-parameters.md)

[HTML5 transformation](../topics/dita2html5.md)

[Markdown transformations](../topics/dita2markdown.md)

[Normalized DITA transformations](../topics/dita2dita.md)

[TocJS transformation](../topics/dita2tocjs.md)

[troff transformation](../topics/dita2troff.md)

