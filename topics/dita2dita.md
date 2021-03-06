# Normalized DITA

The `dita` transformation generates normalized topics and maps from DITA input. The normalized output includes the results of the DITA Open Toolkit pre-processing operations, which resolve map references, keys, content references, code references and push metadata back and forth between maps and topics.

In comparison to the source DITA files, the normalized DITA files are modified in the following ways:

-   References from one DITA map to another are resolved
-   Map-based links, such as those generated by map hierarchy and relationship tables, are added to the topics.
-   Link text is resolved.
-   Map attributes that cascade are made explicit on child elements.
-   Map metadata such as index entries and copyrights are pushed into topics.
-   Topic metadata such as navigation titles, link text and short descriptions are pulled from topics into the map.
-   XML comments are removed.

## Applications

Normalized output may be useful in situations where post-processing of DITA content is required, but the downstream systems are limited in their ability to resolve DITA references.

## Generating normalized DITA output

Run the dita command and set the value of the output --format option to dita:

```
dita-ot-dir/bin/dita --input=input-file --format=dita
```

where:

-   dita-ot-dir is the DITA-OT installation directory.
-   input-file is the DITA map or DITA file that you want to process.

**Parent topic:** [DITA-OT transformations \(output formats\)](../topics/output-formats.md)

**Related information**  


[Common parameters](../parameters/parameters-base.md)

