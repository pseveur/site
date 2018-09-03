# HTML5

The html5 transformation generates HTML5 output and a table of contents \(TOC\) file.

The HTML5 output is always associated with the default DITA-OT CSS file \(commonltr.css or commonrtl.css for right-to-left languages\). You can use toolkit parameters to add a custom style sheet that overrides the default styles, or generate a `nav` element with a navigation TOC in topic pages.

To run the HTML5 transformation, set the transtype parameter to html5, or pass the --format=html5 option to the dita command line.

```
dita-ot-dir/bin/dita --input=input-file --format=html5
```

where:

-   dita-ot-dir is the DITA-OT installation directory.
-   input-file is the DITA map or DITA file that you want to process.

**Parent topic:** [DITA-OT transformations \(output formats\)](../topics/output-formats.md)

**Related information**  


[Setting parameters for custom HTML](../topics/html-customization-parameters.md)

[Common parameters](../parameters/parameters-base.md)

[HTML-based output parameters](../parameters/parameters-base-html.md)

[HTML5 parameters](../parameters/parameters-html5.md)

[Handling content outside the map directory](../parameters/generate-copy-outer.md)

