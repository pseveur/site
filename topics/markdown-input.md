# Markdown content

 [Markdown](https://daringfireball.net/projects/markdown/) is a lightweight markup language that allows you to write using an easy-to-read plain text format and convert to structurally valid markup as necessary.

In the words of its creators:

> “The overriding design goal for Markdown’s formatting syntax is to make it as readable as possible. The idea is that a Markdown-formatted document should be publishable as-is, as plain text, without looking like it’s been marked up with tags or formatting instructions.”

DITA Open Toolkit now allows you to use Markdown files directly in topic references and export DITA content as Markdown.

These features enable lightweight authoring scenarios that allow subject matter experts to contribute to DITA publications without writing in XML, and support publishing workflows that include DITA content in Markdown-based publishing systems.

## Adding Markdown topics

To add a Markdown topic to a DITA publication, create a topic reference in your map and set the `@format` attribute to `markdown` so the toolkit will recognize the source file as Markdown and convert it to DITA:

```
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "map.dtd">
<map>
  <topicref href="markdown-dita-topic.md" **format="markdown"**/>
</map>
```

The `markdown` format uses a relatively lenient document parsing approach to support a wide range of content and Markdown syntax constructs.

**Note:** The Markdown support is based on [CommonMark](http://commonmark.org), a strongly defined, highly compatible specification of Markdown.

**Parent topic:** [Alternative authoring formats](../topics/alternative-input-formats.md)

**Related information**  


[Preview support for Lightweight DITA](../topics/lwdita-input.md)

[Markdown DITA syntax reference](../topics/markdown-dita-syntax-reference.md)

