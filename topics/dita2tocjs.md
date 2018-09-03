# TocJS

The tocjs transformation generates XHTML output, a frameset, and a JavaScript-based table of contents with expandable and collapsible entries. The transformation was originally created by Shawn McKenzie as a plug-in and was added to the default distribution in DITA-OT release 1.5.4.

The tocjs transformation was updated so that it produces XHTML output and uses a default frameset.

To run the TocJS transformation, set the transtype parameter to tocjs, or pass the --format=tocjs option to the dita command line.

```
dita-ot-dir/bin/dita --input=input-file --format=tocjs
```

where:

-   dita-ot-dir is the DITA-OT installation directory.
-   input-file is the DITA map or DITA file that you want to process.

**Parent topic:** [DITA-OT transformations \(output formats\)](../topics/output-formats.md)

**Related information**  


[Common parameters](../parameters/parameters-base.md)

