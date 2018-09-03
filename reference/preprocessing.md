# Pre-processing modules

The pre-processing operation is a set of steps that typically runs at the beginning of every DITA-OT transformation. Each step or stage corresponds to an Ant target in the build pipeline; the `preprocess` target calls the entire set of steps.

1.  [Generate lists \(gen-list\)](../reference/preprocess-genlist.md)  
The `gen-list` step examines the input files and creates lists of topics, images, document properties, or other content. These lists are used by later steps in the pipeline. This step is implemented in Java.
2.  [Debug and filter \(debug-filter\)](../reference/preprocess-debugfilter.md)  
The `debug-filter` step processes all referenced DITA content and creates copies in a temporary directory. As the DITA content is copied, filtering is performed, debugging information is inserted, and table column names are adjusted. This step is implemented in Java.
3.  [Resolve map references \(mapref\)](../reference/preprocess-mapref.md)  
The `mapref` step resolves references from one DITA map to another. This step is implemented in XSLT.
4.  [Branch filtering \(branch-filter\)](../reference/preprocess-branch-filter.md)  
The `branch-filter` step filters topics using DITAVAL files defined in the map.
5.  [Copy related files \(copy-files\)](../reference/preprocess-copyfiles.md)  
The `copy-files` step copies non-DITA resources to the output directory, such as HTML files that are referenced in a map or images that are referenced by a DITAVAL file. Which files are copied depends on the transformation type.
6.  [Resolve key references \(keyref\)](../reference/preprocess-keyref.md)  
The `keyref` step examines all the keys that are defined in the DITA source and resolves the key references. Links that make use of keys are updated so that any `@href`value is replaced by the appropriate target; key-based text replacement is also performed, and the key definition list file is written to the temporary directory. This step is implemented in Java.
7.  [Copy topics \(copy-to\)](../reference/preprocess-copy-to.md)  
The `copy-to` step makes a copy of original topic resources to new resources defined by the `@copy-to` attribute.
8.  [Conref push \(conrefpush\)](../reference/preprocess-conrefpush.md)  
The `conrefpush` step resolves "conref push" references. This step only processes documents that use conref push or that are updated due to the push action. This step is implemented in Java.
9.  [Resolve content references \(conref\)](../reference/preprocess-conref.md)  
The `conref` step resolves content references, processing only the DITA maps or topics that use the `@conref` attribute. This step is implemented in XSLT.
10. [Filter conditional content \(profile\)](../reference/preprocess-profile.md)  
The `profile` step removes content from topics and maps based on the rules in DITAVAL files or the `@print` attribute setting. Output can differ based on when filtering is done.
11. [Resolve topic fragments and code references \(topic-fragment\)](../reference/preprocess-topic-fragment.md)  
The `topic-fragment` step expands content references to elements in the same topic and resolves references made with the `coderef` element. This step is implemented in SAX pipes.
12. [Chunk topics \(chunk\)](../reference/preprocess-chunk.md)  
The `chunk` step breaks apart and assembles referenced DITA content based on the @chunk attribute in maps. This step is implemented in Java.
13. [Move metadata \(move-meta-entries\) and pull content into maps \(mappull\)](../reference/preprocess-metadata.md)  
The `move-meta-entries` step pushes metadata back and forth between maps and topics. For example, index entries and copyrights in the map are pushed into affected topics, so that the topics can be processed later in isolation while retaining all relevant metadata. This step is implemented in Java.
14. [Map based linking \(maplink\)](../reference/preprocess-maplink.md)  
This step collects links based on a map and moves those links into the referenced topics. The links are created based on hierarchy in the DITA map, the `@collection-type` attribute, and relationship tables. This step is implemented in XSLT and Java.
15. [Pull content into topics \(topicpull\)](../reference/preprocess-topicpull.md)  
The `topicpull` step pulls content into `xref` and `link` elements. This step is implemented in XSLT.
16. [Flagging \(flag-module\)](../reference/preprocess-flagging.md)  
Beginning with DITA-OT 1.7, flagging support is implemented as a common `flag-module` preprocessing step. The module evaluates the DITAVAL against all flagging attributes, and adds DITA-OT–specific hints to the topic when flags are active. Any extended transformation type may use these hints to support flagging without adding logic to interpret the DITAVAL.
17. [Map cleanup \(clean-map\)](../reference/preprocess-clean-map.md)  
The `clean-map` step removes any elements and attributes that were added to files to support preprocessing.

**Parent topic:** [Architecture of the DITA Open Toolkit](../reference/architecture.md)

