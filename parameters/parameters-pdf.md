# PDF parameters

Certain parameters are specific to the PDF transformation.

-   **args.artlbl**

    Specifies whether to generate a label for each image; the label will contain the image file name. The allowed values are yes and no; the default value is no.

-   **args.bookmap-order**

    Specifies if the frontmatter and backmatter content order is retained in bookmap. The allowed values are retain and discard; the default value is discard.

-   **args.bookmark.style**

    Specifies whether PDF bookmarks are by default expanded or collapsed. The allowed values are EXPANDED and COLLAPSE.

-   **args.chapter.layout**

    Specifies whether chapter level TOCs are generated. The allowed values are MINITOC and BASIC; the default value is MINITOC.

-   **args.fo.userconfig**

    Specifies the user configuration file for FOP.

-   **args.xsl.pdf**

    Specifies an XSL file that is used to override the default XSL transformation.

    You must specify the fully qualified file name.

-   **axf.cmd**

    Specifies the path to the Antenna House Formatter executable.

-   **axf.opt**

    Specifies the user configuration file for Antenna House Formatter.

-   **custom.xep.config**

    Specifies the user configuration file for RenderX.

-   **customization.dir**

    Specifies the customization directory.

-   **maxJavaMemory**

    Specifies the amount of memory allocated to the RenderX process.

-   **org.dita.pdf2.i18n.enabled**

    Enables internationalization \(I18N\) font processing to provide per-character font selection for FO renderers that do not support the `font-selection-strategy` property \(such as Apache FOP\).

    When this feature is enabled, DITA-OT uses a font mapping process that takes the content language into consideration. The mapping process uses configuration files for each language to define characters that should be rendered with certain logical fonts, and font mappings that associate each logical font to physical font files.

    The following values are allowed:

    -   true \(default\) — Enables font mapping
    -   false — Disables font mapping
    **Tip:** If you don’t use custom character mappings, turning off font mapping makes it easier to define custom fonts simply by changing font names in the XSL attributes files of your custom PDF plug-in. For details, see [Font configuration in PDF2](http://www.elovirta.com/2016/02/18/font-configuration-in-pdf2.html).

-   **outputFile.base**

    Specifies the base file name of the generated PDF file.

    By default, the PDF file uses the base filename of the input .ditamap file.

-   **pdf.formatter**

    Specifies the XSL processor. The following values are supported:

    -   ah – Antenna House Formatter
    -   xep – RenderX XEP Engine
    -   fop \(default\) – Apache FOP
-   **publish.required.cleanup**

    Specifies whether draft-comment and required-cleanup elements are included in the output. The allowed values are yes, no, yes, and no.

    The default value is the value of the args.draft parameter. Corresponds to the XSLT parameter publishRequiredCleanup.

    **Note:** This parameter is deprecated in favor of the args.draft parameter.


**Parent topic:** [DITA-OT parameters](../parameters/parameters_intro.md)

**Related information**  


[PDF transformation](../topics/dita2pdf.md)

[Common parameters](../parameters/parameters-base.md)

