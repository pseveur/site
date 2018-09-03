# Preview support for Lightweight DITA

DITA-OT provides preview support for the MDITA and HDITA authoring formats proposed for [Lightweight DITA](http://docs.oasis-open.org/dita/LwDITA/v1.0/cn01/LwDITA-v1.0-cn01.pdf), or “LwDITA”. These proposed formats are alternative representations of DITA content in Markdown or HTML.

## MDITA

MDITA is the LwDITA authoring format based on Markdown.

Recent proposals for LwDITA include two profiles for authoring MDITA topics:

-   The “Core profile” is based on [GitHub-Flavored Markdown](https://github.github.com/gfm/) and includes elements that are common to many other Markdown implementations.
-   The “Extended profile” borrows additional features from other flavors of Markdown to represent a broader range of DITA content with existing plain-text syntax conventions.

The Markdown DITA parser included in the `org.lwdita` plug-in provides preliminary support for these profiles and additional Markdown constructs as described in the syntax reference.

The `@format` attribute can be set to `mdita` to apply LwDITA-specific processing to Markdown topics:

```
<map>
  <topicref href="mdita-topic.md" **format="mdita"**/>
</map>
```

In this case, the first paragraph in the topic will be treated as a short description, for example, and additional metadata can be specified for the topic via a YAML front matter block.

**Note:** Setting the `@format` attribute to `mdita` triggers stricter parsing than the more lenient document parsing approach that is applied to `markdown` documents.

## HDITA

HDITA is the LwDITA authoring format based on HTML5, which is intended to support structured content authoring with tools designed for HTML authoring. HDITA also uses custom data attributes to provide interoperability with DITA.

The HDITA parser included in the `org.lwdita` plug-in provides preliminary support for these constructs.

The `@format` attribute can be set to `hdita` to apply LwDITA-specific processing to HTML topics:

```
<map>
  <topicref href="hdita-topic.html" **format="hdita"**/>
</map>
```

**Attention:** Since [Lightweight DITA](http://docs.oasis-open.org/dita/LwDITA/v1.0/cn01/LwDITA-v1.0-cn01.pdf) has not yet been released as a formal specification, the implementation for MDITA and HDITA authoring formats is subject to change. Future versions of DITA Open Toolkit will be updated as LwDITA evolves.

**Parent topic:** [Alternative authoring formats](../topics/alternative-input-formats.md)

**Related information**  


[Markdown content](../topics/markdown-input.md)

[Markdown DITA syntax reference](../topics/markdown-dita-syntax-reference.md)

