# Architecture of the DITA Open Toolkit

The DITA Open Toolkit is an open-source implementation of the OASIS specification for the Darwin Information Typing Architecture. The toolkit uses Ant, XSLT, and Java to transform DITA content \(maps and topics\) into different deliverable formats.

-   **[Processing structure](../reference/processing-structure.md)**  
The DITA-OT implements a multi-stage, map-driven architecture to process DITA content. Each stage in the process examines some or all of the content; some stages result in temporary files that are used by later steps, while others stages result in updated copies of the DITA content. Most of the processing takes place in a temporary working directory; the source files themselves are never modified.
-   **[Map-first preprocessing](../reference/map-first-preprocessing.md)**  
DITA-OT 3.0 provides a map-first preprocessing option as an alternative to the default `preprocess` operation. The method, which was introduced in DITA-OT 2.5 as an experimental feature, has been improved and is ready for use in many production scenarios. Map-first-preprocessing provides the same functionality as the default `preprocess`, but takes a different approach.
-   **[Processing modules](../reference/processing-pipeline-modules.md)**  
The DITA-OT processing pipeline is implemented using Ant. Individual modules within the Ant script are implemented in either Java or XSLT, depending on such factors as performance or requirements for customization. Virtually all Ant and XSLT modules can be extended by adding a plug-in to the toolkit; new Ant targets may be inserted before or after common processing, and new rules may be imported into common XSLT modules to override default processing.
-   **[Processing order](../reference/processing-order.md)**  
The order of processing is often significant when evaluating DITA content. Although the DITA specification does not mandate a specific order for processing, the DITA-OT has determined that performing filtering before conref resolution best meets user expectations. Switching the order of processing, while legal, may give different results.
-   **[Pre-processing modules](../reference/preprocessing.md)**  
The pre-processing operation is a set of steps that typically runs at the beginning of every DITA-OT transformation. Each step or stage corresponds to an Ant target in the build pipeline; the `preprocess` target calls the entire set of steps.
-   **[HTML-based processing modules](../reference/XhtmlWithNavigation.md)**  
The DITA-OT ships with several varieties of HTML output, each of which follows roughly the same path through the processing pipeline. All HTML-based transformation begin with the same call to the pre-processing module, after which they generate HTML files and then branch to create the transformation-specific navigation files.
-   **[PDF processing modules](../reference/pdf-transform.md)**  
The PDF \(formerly known as PDF2\) transformation process runs the pre-processing routine and follows it by a series of additional targets. These steps work together to create a merged set of content, convert the merged content to XSL-FO, and then format the XSL-FO file to PDF.

**Parent topic:** [Reference](../reference/index.md)

