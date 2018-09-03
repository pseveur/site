# HTML5 parameters

The HTML5 transformation shares common parameters with other HTML-based transformations and provides additional parameters that are specific to HTML5 output.

-   **args.artlbl**

    Specifies whether to generate a label for each image; the label will contain the image file name. The allowed values are yes and no; the default value is no.

-   **args.copycss**

    Specifies whether to copy the custom .css file to the output directory. The allowed values are yes and no; the default value is no.

    If an external process will copy your custom .css file to the output directory, leave this parameter unset \(or set it to no\). If DITA-OT should copy the file when generating output, set it to yes.

-   **args.css**

    Specifies the name of a custom .css file.

    The value of this parameter should be only the file name \(or an absolute path to the file\). A relative path can be specified with args.cssroot.

-   **args.csspath**

    Specifies the **destination** directory to which .css files are copied \(relative to the output directory\).

    Corresponds to the XSLT parameter CSSPATH.

    DITA-OT will copy the file **to** this location.

    **Tip:** If args.csspath is not set, the custom CSS file \(and the default CSS files\) will be copied to the root level of the output folder. To copy CSS files to an output subfolder named css, set args.csspath to css.

-   **args.cssroot**

    Specifies the **source** directory that contains the custom .css file.

    DITA-OT will copy the file **from** this location.

    **Tip:** The value you enter here will be interpreted relative to the location of the input map file. If your map is stored at the root level of your project folder and the CSS file is stored in a subfolder named resources, set args.cssroot to resources.

-   **args.dita.locale**

    Specifies the language locale file to use for sorting index entries.

-   **args.ftr**

    Specifies an XML file that contains content for a running footer.

     Corresponds to the XSLT parameter FTR. 

    **Note:** The footer file should be specified using an absolute path and must contain valid XML. A common practice is to place all content into a `div` element.

-   **args.gen.default.meta**

    Specifies whether to generate extra metadata that targets parental control scanners, meta elements with name="security" and name="Robots". The allowed values are yes and no; the default value is no.

    Corresponds to the XSLT parameter genDefMeta.

-   **args.hdf**

    Specifies an XML file that contains content to be placed in the document head.

    The contents of the header file will be inserted in the `head` element of the generated HTML files.

    **Tip:** The header file should be specified using an absolute path and must contain valid XML. If you need to insert more than one element into the HTML page head, wrap the content in a `div` element. The division wrapper in the header file will be discarded when generating HTML files, and the contents will be inserted into each page head.

-   **args.hdr**

    Specifies an XML file that contains content for a running header.

     Corresponds to the XSLT parameter HDR. 

    **Note:** The header file should be specified using an absolute path and must contain valid XML. A common practice is to place all content into a `div` element.

-   **args.hide.parent.link**

    Specifies whether to hide links to parent topics in the HTML5 output. The allowed values are yes and no; the default value is no.

     Corresponds to the XSLT parameter NOPARENTLINK. 

    **Note:** This parameter is deprecated in favor of the args.rellinks parameter.

-   **args.html5.classattr**

    Specifies whether to include the DITA class ancestry inside the HTML5 elements. The allowed values are yes and no; the default value is yes.

-   **args.html5.contenttarget**

    Specifies the value of the @target attribute on the <base\> element in the TOC file.

-   **args.html5.toc**

    Specifies the base name of the TOC file.

-   **args.html5.toc.class**

    Specifies the value of the @class attribute on the <body\> element in the TOC file.

-   **args.html5.toc.xsl**

    Specifies a custom XSL file to be used for TOC generation.

-   **args.indexshow**

    Specifies whether the content of <indexterm\> elements are rendered in the output. The allowed values are yes and no; the default value is no.

-   **args.outext**

    Specifies the file extension for HTML5 output.

     Corresponds to the XSLT parameter OUTEXT. 

-   **args.xsl**

    Specifies a custom XSL file to be used instead of the default XSL transformation.

    The parameter must specify a fully qualified file name.

-   **nav-toc**

    Specifies whether to generate a table of contents \(ToC\) in the HTML5 `nav` element of each page. The navigation can then be rendered in a sidebar or menu via CSS.

    The following values are supported:

    -   none \(default\) – No table of contents will be generated
    -   partial – Include the current topic in the ToC along with its parents, siblings and children
    -   full – Generate a complete ToC for the entire map

**Parent topic:** [DITA-OT parameters](../parameters/parameters_intro.md)

**Related information**  


[HTML5 transformation](../topics/dita2html5.md)

[Setting parameters for custom HTML](../topics/html-customization-parameters.md)

[HTML-based output parameters](../parameters/parameters-base-html.md)

