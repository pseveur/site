# HTML-based output parameters

Certain parameters apply to all HTML-based transformation types: HTML5, XHTML, HTML Help, Eclipse help, and TocJS.

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

    **Note:** This parameter is not available for the XHTML transformation.

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

    Specifies whether to hide links to parent topics in the HTML or XHTML output. The allowed values are yes and no; the default value is no.

     Corresponds to the XSLT parameter NOPARENTLINK. 

    **Note:** This parameter is deprecated in favor of the args.rellinks parameter.

-   **args.indexshow**

    Specifies whether the content of <indexterm\> elements are rendered in the output. The allowed values are yes and no; the default value is no.

-   **args.outext**

    Specifies the file extension for HTML or XHTML output.

     Corresponds to the XSLT parameter OUTEXT. 

-   **args.xhtml.classattr**

    Specifies whether to include the DITA class ancestry inside the XHTML elements. The allowed values are yes and no; the default value is yes.

    For example, the `prereq` element \(which is specialized from `section`\) would generate `class="section prereq"`. Corresponds to the XSLT parameter PRESERVE-DITA-CLASS.

    **Note:** Beginning with DITA-OT release 1.5.2, the default value is yes. For release 1.5 and 1.5.1, the default value was no.

-   **args.xsl**

    Specifies a custom XSL file to be used instead of the default XSL transformation.

    The parameter must specify a fully qualified file name.


**Parent topic:** [DITA-OT parameters](../parameters/parameters_intro.md)

**Related information**  


[Eclipse help transformation](../topics/dita2eclipsehelp.md)

[HTML help transformation](../topics/dita2htmlhelp.md)

[XHTML transformation](../topics/dita2xhtml.md)

[Setting parameters for custom HTML](../topics/html-customization-parameters.md)

[HTML5 transformation](../topics/dita2html5.md)

[Bundling CSS in a custom HTML plug-in](../topics/html-customization-plugin-bundle-css.md)

[Eclipse Help parameters](../parameters/parameters-eclipsehelp.md)

[HTML5 parameters](../parameters/parameters-html5.md)

[Microsoft Compiled HTML Help parameters](../parameters/parameters-htmlhelp.md)

[XHTML parameters](../parameters/parameters-xhtml.md)

