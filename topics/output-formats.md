# DITA-OT transformations \(output formats\)

The DITA Open Toolkit ships with several core transformations that generate different output formats from DITA content. Each transformation represents an implementation of the processing that is defined by OASIS in the DITA specification.

-   **[PDF](../topics/dita2pdf.md)**  
The pdf transformation generates output in Portable Document Format.
-   **[HTML5](../topics/dita2html5.md)**  
The html5 transformation generates HTML5 output and a table of contents \(TOC\) file.
-   **[Eclipse help](../topics/dita2eclipsehelp.md)**  
The eclipsehelp transformation generates XHTML output, CSS files, and the control files that are needed for Eclipse help.
-   **[HTML Help](../topics/dita2htmlhelp.md)**  
The htmlhelp transformation generates HTML output, CSS files, and the control files that are needed to produce a Microsoft Compiled HTML Help \(.chm\) file.
-   **[Markdown](../topics/dita2markdown.md)**  
Along with Markdown input, DITA-OT now provides three new transformation types to convert DITA content to Markdown, including the original syntax, GitHub-Flavored Markdown, and GitBook.
-   **[Normalized DITA](../topics/dita2dita.md)**  
The `dita` transformation generates normalized topics and maps from DITA input. The normalized output includes the results of the DITA Open Toolkit pre-processing operations, which resolve map references, keys, content references, code references and push metadata back and forth between maps and topics.
-   **[TocJS](../topics/dita2tocjs.md)**  
The tocjs transformation generates XHTML output, a frameset, and a JavaScript-based table of contents with expandable and collapsible entries. The transformation was originally created by Shawn McKenzie as a plug-in and was added to the default distribution in DITA-OT release 1.5.4.
-   **[troff](../topics/dita2troff.md)**  
The troff transformation produces output for use with the troff viewer on Unix-style platforms, particularly for programs such as the man page viewer.
-   **[XHTML](../topics/dita2xhtml.md)**  
The xhtml transformation generates XHTML output and a table of contents \(TOC\) file. This was the first transformation created for the DITA Open Toolkit, and originally served as the basis for all HTML-based transformations.

**Parent topic:** [Building output](../topics/building-output.md)

