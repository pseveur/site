# Resolve map references \(mapref\)

The `mapref` step resolves references from one DITA map to another. This step is implemented in XSLT.

Maps reference other maps by using the following sorts of markup:

```
<topicref href="other.ditamap" format="ditamap"/>
...
<mapref href="other.ditamap"/>
```

As a result of the mapref step, the element that references another map is replaced by the topic references from the other map. Relationship tables are pulled into the referencing map as a child of the root element \(`map` or a specialization of `map`\).

**Parent topic:** [Pre-processing modules](../reference/preprocessing.md)

**Previous topic:** [Debug and filter \(debug-filter\)](../reference/preprocess-debugfilter.md)

**Next topic:** [Branch filtering \(branch-filter\)](../reference/preprocess-branch-filter.md)

