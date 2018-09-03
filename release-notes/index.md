# DITA Open Toolkit 3.1.2 Release Notes

DITA Open Toolkit 3.1.2 is a maintenance release that fixes issues reported in DITA-OT 3.1, which includes support for DITA 1.3 SVG domain elements, enhanced `codeblock` processing, and incremental improvements to Lightweight DITA processing and PDF output.

DITA-OT releases follow [semantic versioning](https://semver.org) guidelines. Version numbers use the `major.minor.patch` syntax, where major versions may include incompatible API changes, minor versions add functionality in a backwards-compatible manner and patch versions are maintenance releases that include backwards-compatible bug fixes.

**Tip:** Download the dita-ot-3.1.2.zip package from the project website at [dita-ot.org/download](https://www.dita-ot.org/download).

## Requirements

DITA Open Toolkit Release 3.1 requires the Java Runtime Environment \(JRE\) version 8 or later.

## Maintenance Release 3.1.2

DITA Open Toolkit Release 3.1.2 includes the following bug fixes.

-   When a content reference was combined with `@conrefend` to reference a sequence of topics, all but the first topic were copied without a required `@id` attribute. This resulted in NullPointerExceptions from later processing steps that expected `@id` on all topics. The content reference behavior has been fixed to avoid the error. [\#2222](https://github.com/dita-ot/dita-ot/issues/2222), [\#3033](https://github.com/dita-ot/dita-ot/pull/3033)
-   In earlier versions, when a topic with index terms had an empty title \(or a title with only metadata\), HTML Help and Eclipse Help index processing would end in a NullPointerException. This error has been fixed. [\#2940](https://github.com/dita-ot/dita-ot/issues/2940), [\#3043](https://github.com/dita-ot/dita-ot/pull/3043) 
-   In earlier versions, when the input file was a topic that contained a `@conref` reference to itself, that topic would not generate output for XHTML or HTML5. The issue has been fixed. [\#2948](https://github.com/dita-ot/dita-ot/issues/2948), [\#3045](https://github.com/dita-ot/dita-ot/pull/3045) 
-   When processing without schema validation, it is possible to add `@keyref` attributes on elements where they are not legal. In earlier releases, this resulted in a NullPointerException from the keyref resolution module. These invalid attributes are now ignored. [\#3008](https://github.com/dita-ot/dita-ot/issues/3008), [\#3034](https://github.com/dita-ot/dita-ot/pull/3034)
-   The Lightweight DITA plug-in has been updated to version 2.0.6, which provides improved support for inline HTML elements. [\#3023](https://github.com/dita-ot/dita-ot/pull/3023) 
-   In DITA-OT 3.1, configuration data is read from two files, but some processes would incorrectly load only one file and miss properties in the other. This is fixed by removing lib/configuration.properties and storing all configuration properties in config/configuration.properties. [\#3024](https://github.com/dita-ot/dita-ot/pull/3024) 
-   In earlier releases, when the "same file" reference syntax `href="#./elementid` was pulled into another file as part of a content reference, the `@href` attribute was corrupted, resulting in broken links. These references have been fixed and now refer to the element with `id="elementid"` in the new resolved context. [\#3027](https://github.com/dita-ot/dita-ot/pull/3027) 
-   In DITA-OT 3.0 and 3.1, Saxon would generate XSLT errors when it encountered `cite` or `term` inside of a `linktext` element in the related links section of a topic. The XSLT syntax has been fixed to avoid this error. [\#3029](https://github.com/dita-ot/dita-ot/pull/3029) 
-   In earlier versions, the Ant build code for PDF2 set up a `CLASSPATH` variable that referenced JAR files that no longer exist. These references have been removed. [\#2832](https://github.com/dita-ot/dita-ot/issues/2832), [\#3040](https://github.com/dita-ot/dita-ot/pull/3040) 

For the complete list of changes since the previous release, see the [changelog](https://github.com/dita-ot/dita-ot/compare/3.1.1...3.1.2) on GitHub.

## Maintenance Release 3.1.1 released July 16, 2018

DITA Open Toolkit Release 3.1.1 includes the following bug fixes.

-   When generating PDF output with Antenna House Formatter, earlier versions would sometimes fail when interpreting the Antenna House log. Processing has been updated to improve test coverage and handle these cases more gracefully. [\#2662](https://github.com/dita-ot/dita-ot/issues/2662), [\#3012](https://github.com/dita-ot/dita-ot/issues/3012) 
-   Earlier versions treated image files referenced in `data` elements and certain other non-DITA resources as DITA topics. The map reader processing phase has been corrected to reliably collect non-DITA resources and record them as such in the .job.xml file. [\#2855](https://github.com/dita-ot/dita-ot/issues/2855), [\#3010](https://github.com/dita-ot/dita-ot/issues/3010) 
-   DITA-OT 3.0 failed to produce Eclipse help output. A missing library import has been restored to ensure that Eclipse help is generated correctly. [\#2870](https://github.com/dita-ot/dita-ot/issues/2870) 
-   When generating output for HTML-based formats, earlier versions failed to handle `@conkeyref` attribute references to topics outside the map directory hierarchy, resulting in missing content and invalid paths to CSS resources. Processing has been corrected to ensure the paths to such files are calculated correctly. [\#2983](https://github.com/dita-ot/dita-ot/issues/2983), [\#3014](https://github.com/dita-ot/dita-ot/issues/3014) 
-   A missing reference to the $file-being-processed parameter has been restored to ensure that the current file is correctly tracked while resolving map references in pre-processing. [\#3005](https://github.com/dita-ot/dita-ot/issues/3005) 
-   In earlier versions, key references to duplicate topics created via `@copy-to` attributes caused builds to fail. The original source information is now correctly recorded for copy-to targets, allowing builds to continue. [\#3007](https://github.com/dita-ot/dita-ot/issues/3007), [\#3015](https://github.com/dita-ot/dita-ot/issues/3015) 
-   In earlier versions, `screen` elements resulted in a build failure when published to troff. Updating the plugin to version 3.1.1 resolves the issue. [\#3017](https://github.com/dita-ot/dita-ot/issues/3017) 
-   The documentation includes minor [changes](https://github.com/dita-ot/docs/compare/3.1...3.1.1) with [corrections and improvements](https://github.com/dita-ot/docs/milestone/34?closed=1) to existing topics.


For the complete list of changes since the previous release, see the [changelog](https://github.com/dita-ot/dita-ot/compare/3.1...3.1.1) on GitHub.

## DITA-OT 3.1 released June 9, 2018

DITA Open Toolkit Release 3.1 includes support for DITA 1.3 SVG domain elements, enhanced `codeblock` processing, and incremental improvements to Lightweight DITA processing and PDF output.

### Features

DITA Open Toolkit Release 3.1 includes the following new features:

-   A new Java wrapper for the XSLT `mapref` map resolution module allows for better handling of content references and key references in nested maps. [\#2875](https://github.com/dita-ot/dita-ot/pull/2875) 
-   Updates to the Java code that calls Saxon now support integrated extension functions for Saxon HE \(versions ≥ 9.2\). [\#2880](https://github.com/dita-ot/dita-ot/pull/2880) 
-   A new end-to-end test case ensures a basic test is run for all supported transformation types with every update to DITA-OT. [\#2932](https://github.com/dita-ot/dita-ot/pull/2932) 
-   DITA-OT now supports the DITA 1.3 SVG domain elements, including `svgref` for pulling in external SVG markup. [\#2960](https://github.com/dita-ot/dita-ot/pull/2960) 
-   PDF output now supports key-based linking for phrase like elements, including `cite`, `ph`, and `dt`. When key definitions specify a URI for linking, the links will now appear in PDF. This markup already resulted in links in HTML output, and resulted in PDF links for key references on `keyword` and `term`. [\#2025](https://github.com/dita-ot/dita-ot/issues/2025), [\#2961](https://github.com/dita-ot/dita-ot/pull/2961) 
-   Processing for `codeblock` elements has been enhanced to support new `@outputclass` keywords that can be used to adjust the presentation of code samples.
    -   To remove leading whitespace in external code references, set the `@outputclass` attribute to include the `normalize-space` keyword. With this setting, DITA-OT trims any leading whitespace that is common to all lines in the code block to remove excess indentation and keep lines short. [\#2907](https://github.com/dita-ot/dita-ot/issues/2907), [\#2953](https://github.com/dita-ot/dita-ot/pull/2953) 
    -   To highlight whitespace characters in code blocks, set the `@outputclass` attribute to include the `show-whitespace` keyword. When PDF output is generated, space characters in the code will be replaced with a middle dot or “interpunct” character \( `·` \); tab characters are replaced with a rightwards arrow and three spaces \( `→   ` \). [\#2975](https://github.com/dita-ot/dita-ot/pull/2975) 
    -   To add line numbers to code blocks in PDF output, set the `@outputclass` attribute to include the `show-line-numbers` keyword.

        **Note:** Line numbering has been available since DITA-OT 2.0, but previously required custom PDF plug-ins to override the `codeblock.generate-line-number` template mode to return `true()`. DITA-OT 3.1 now checks for the keyword in the `@outputclass`, so line numbering can be enabled without custom PDF plug-ins.


### Enhancements and changes

DITA Open Toolkit Release 3.1 includes the following enhancements and changes to existing features:

-   The error message generated for duplicate key definitions has been updated for clarity. [\#2079](https://github.com/dita-ot/dita-ot/issues/2079) 
-   Ant scripts for DITA-OT builds now make use of `@if:set` and `@unless:set` attributes in the Ant namespace, which can be used to control whether parameters are passed to XSLT modules. These attributes replace custom implementations of `if` and `unless` logic introduced before Ant had this capability. [\#2890](https://github.com/dita-ot/dita-ot/pull/2890) 
-   The PDF build code has been refactored and simplified to use the `xmlcatalog` element instead of using a custom `xml.catalog.files` property. [\#2938](https://github.com/dita-ot/dita-ot/pull/2938) 
-   Alternate text for images is now preserved in the XSL-FO files generated for PDF, using the custom attributes necessary for Apache™ FOP, RenderX XEP, and Antenna House processors. The alternate text is now available in the final output file when processors generate accessible PDF. [\#2850](https://github.com/dita-ot/dita-ot/issues/2850), [\#2964](https://github.com/dita-ot/dita-ot/pull/2964)
-   In PDF processing with Apache FOP, DITA-OT 3.1 now uses the Simple Logging Facade for Java \(SLF4J\), allowing for better control and formatting of FOP log messages. To reduce noise on the console, all FOP messages are set to the Info level and hidden by default. [\#2967](https://github.com/dita-ot/dita-ot/pull/2967) 
-   The HTML5 XSLT stylesheets used to create TOC navigation have been refactored to use a new processing mode. This removes the "Duplicate import of map2html5Impl.xsl" message that appeared with DITA-OT 3.0. [\#2821](https://github.com/dita-ot/dita-ot/issues/2821) [\#2970](https://github.com/dita-ot/dita-ot/pull/2970) 
-   The distribution build has been updated to use the documentation Gradle build instead of Ant. [\#2972](https://github.com/dita-ot/dita-ot/issues/2972) 
-   The bundled Apache FOP version has been updated to 2.3. \(For details on recent changes, see the [Apache FOP 2.3 Release Notes](https://xmlgraphics.apache.org/fop/2.3/releaseNotes_2.3.html).\) [\#2974](https://github.com/dita-ot/dita-ot/issues/2974), [\#2976](https://github.com/dita-ot/dita-ot/pull/2976) 
-   The `@frame` attribute on `choicetable` elements is now respected in PDF output; previously all values for `@frame` on this element were ignored in PDF. [\#2978](https://github.com/dita-ot/dita-ot/pull/2978) 
-   The LwDITA plugin has been updated to version 2.0.5, pulling in a number of fixes for Lightweight DITA processing. \(Topic metadata is now preserved in YAML headers when generating Markdown for composite topics, autolinks in Markdown topics are treated as external cross references, and definition lists in Markdown input and links to ID fragments are now handled correctly.\) [\#2982](https://github.com/dita-ot/dita-ot/pull/2982), [\#2993](https://github.com/dita-ot/dita-ot/pull/2993) 
-   PDF processing now includes a hook that can be used to add custom `fo:marker` elements on any topic. New processing hooks are also available to add custom anchors on any topic or titled sub-topic element, intended as a way to enable stable links into a location within a PDF. [\#2984](https://github.com/dita-ot/dita-ot/pull/2984) 
-   The Gradle wrapper used to run the documentation build has been updated to version 4.8. [\#2991](https://github.com/dita-ot/dita-ot/pull/2991), [\#2994](https://github.com/dita-ot/dita-ot/issues/2994) 

### Bugs

DITA Open Toolkit Release 3.1 provides fixes for the following bugs:

-   When a nested map uses `@conref` to pull content from another map, but the root map does *not* use `@conref`, the content reference was not previously resolved. This is now fixed, and content references in all maps used by the build are resolved properly. [\#2494](https://github.com/dita-ot/dita-ot/issues/2494) 
-   When a `chapter` element refers to another map that is not a bookmap, PDF processing now formats the referenced content as a chapter. In earlier versions, the content could be formatted as a generic topic that did not match other chapters in the same map. [\#2898](https://github.com/dita-ot/dita-ot/issues/2898) 
-   The error message DOTJ007E, which appeared for duplicate filter conditions in DITAVAL properties, has been switched from an Error to a Warning. This message, which usually does not indicate a problem that results in broken output, will now appear as DOTJ007W. [\#2958](https://github.com/dita-ot/dita-ot/pull/2958) 
-   The empty temp/ directory included in DITA-OT 3.0 distribution packages has been removed. [\#2973](https://github.com/dita-ot/dita-ot/issues/2973) 
-   Several duplicate ID messages that appeared in PDF processing have been fixed by removing incorrect ID definitions. These messages could previously appear when nested elements inside of topic titles or topic short descriptions specified their own `@id` attribute; in DITA-OT 3.0, this also appeared for all `pt` elements that specified `@id`. [\#2985](https://github.com/dita-ot/dita-ot/pull/2985) 
-   Several unnecessary files have been removed from the docsrc/ folder of the distribution package. [\#2990](https://github.com/dita-ot/dita-ot/pull/2990) 

### Contributors

DITA Open Toolkit Release 3.1 includes [code contributions](https://github.com/dita-ot/dita-ot/graphs/contributors) by the following people:

1.  Jarno Elovirta
2.  Robert D. Anderson
3.  Roger Sheen
4.  Radu Coravu
5.  Alexey Mironov
6.  Stefan Eike
7.  Shane Taylor

For the complete list of changes since the previous release, see the [changelog](https://github.com/dita-ot/dita-ot/compare/2.5...3.0) on GitHub.

### Documentation updates

The documentation for DITA Open Toolkit Release 3.1 provides corrections and improvements to existing topics, along with new information in the following topics:

-    [Extended codeblock processing](../reference/extended-functionality.md)
-    [Plug-in coding conventions](../topics/plugin-coding-conventions.md)
-    [Migrating to release 3.1](../topics/migrating-to-3.1.md)
-    [Log files](../topics/log-files.md)

For additional information on documentation issues resolved in DITA Open Toolkit Release 3.1, see the [ 3.1 milestone](https://github.com/dita-ot/docs/issues?q=milestone%3A3.1+is%3Aclosed) in the documentation repository.

DITA Open Toolkit Release 3.1 includes [documentation contributions](https://github.com/dita-ot/docs/graphs/contributors) by the following people:

1.  Roger Sheen
2.  Robert D. Anderson
3.  Lief Erickson
4.  Stefan Eike
5.  Jarno Elovirta
6.  Eero Helenius
7.  François Violette

For the complete list of documentation changes since the previous release, see the [changelog](https://github.com/dita-ot/docs/compare/3.0...3.1).

