# Internal Ant properties

Reference list of Ant properties used by DITA-OT internally.

-   **`include.rellinks`**

    A space-separated list of link roles to be output; the `#default` value token represents links without an explicit role \(those for which no `@role` attribute is defined\). Defined by `args.rellinks`, but may be overridden directly. Valid roles include:

    -   parent
    -   child
    -   sibling
    -   friend
    -   next
    -   previous
    -   cousin
    -   ancestor
    -   descendant
    -   sample
    -   external
    -   other
-   **`temp.output.dir.name`**

    An internal property for use with custom transform types; this property can be used to place all output in an internal directory, so that a final step in the transform type can do some form of post-processing before the files are placed in the specified output directory.

    For example, if a custom HTML5 transform sets the property to `zip_dir`, all output files \(including HTML, images, and CSS\) will be placed within the directory zip\_dir in the temporary processing directory. A final step can then be used to add more files, zip the directory, and return that zip to the designated output directory.


**Parent topic:** [Configuration properties](../parameters/configuration-properties.md)

