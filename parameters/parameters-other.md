# Other parameters

These parameters enable you to reload style sheets that the DITA-OT uses for specific pre-processing stages.

-   ** dita.html5.reloadstylesheet dita.preprocess.reloadstylesheet dita.preprocess.reloadstylesheet.clean-map dita.preprocess.reloadstylesheet.conref dita.preprocess.reloadstylesheet.lag-module dita.preprocess.reloadstylesheet.mapref dita.preprocess.reloadstylesheet.mappull dita.preprocess.reloadstylesheet.maplink dita.preprocess.reloadstylesheet.topicpull dita.xhtml.reloadstylesheet **

    Specifies whether the DITA-OT reloads the XSL style sheets that are used for the transformation. The allowed values are true and false; the default value is false.

    During the pre-processing stage, DITA-OT processes one DITA topic at a time, using the same XSLT stylesheet for the entire process. These parameters control whether Ant will use the same `Transformer` object in Java, the object that handles the XSLT processing, for all topics, or create a separate `Transformer` for each topic.

    The default \(false\) option uses the same `Transformer`, which is a little faster, because it will not need to parse/compile the XSLT stylesheets and only needs to read the source trees with `document()` once. The downside is that it will not release the source trees from memory, so you can run out of memory.

    **Tip:** For large projects that generate Java out-of-memory errors during transformation, set the parameter to true to allow the XSLT processor to release memory. You may also need to increase the memory available to Java.


**Parent topic:** [DITA-OT parameters](../parameters/parameters_intro.md)

**Related information**  


[Increasing Java memory allocation](../topics/increasing-the-jvm.md)

[Other error messages](../topics/other-errors.md)

