# Migrating customizations

If you have XSL transformation overrides, plug-ins or other customizations written prior to DITA-OT 3.1, you may need to make changes to ensure your overrides work properly with the latest toolkit versions.

In some cases, you may be able to remove old code that is no longer needed. In other cases, you may need to refactor your code to point to the modified extension points, templates or modes in recent toolkit versions.

**Note:** 

DITA-OT releases follow [semantic versioning](https://semver.org) guidelines. Version numbers use the `major.minor.patch` syntax, where major versions may include incompatible API changes, minor versions add functionality in a backwards-compatible manner and patch versions are maintenance releases that include backwards-compatible bug fixes.

Custom plug-ins developed for a previous major version may require changes to work correctly with recent toolkit versions. Most plug-ins should be compatible with subsequent minor and patch versions of the major release for which they were originally developed.

-   **[Migrating to release 3.1](../topics/migrating-to-3.1.md)**  
DITA-OT 3.1 includes support for DITA 1.3 SVG domain elements, enhanced `codeblock` processing, and incremental improvements to Lightweight DITA processing and PDF output.
-   **[Migrating to release 3.0](../topics/migrating-to-3.0.md)**  
DITA-OT 3.0 adds support for Markdown, normalized DITA output, and the alternative authoring formats proposed for Lightweight DITA. The map-first preprocessing approach provides a modern alternative to the default `preprocess` operation.
-   **[Migrating to release 2.5](../topics/migrating-to-2.5.md)**  
In DITA-OT 2.5, several frequently-overridden legacy style settings were removed from the default PDF plug-in. A separate plug-in can be used to restore the original settings.
-   **[Migrating to release 2.4](../topics/migrating-to-2.4.md)**  
In DITA-OT 2.4, the HTML5 transformation was refactored as an independent plug-in that no longer depends on the XHTML plug-in.
-   **[Migrating to release 2.3](../topics/migrating-to-2.3.md)**  
In DITA-OT 2.3, HTML5 table processing has been refactored to use HTML5 best practices and improved CSS properties. In PDF output, table heads and key columns no longer include shading, and unused localization variables have been deprecated. The template for generated error messages has been updated to use a single `id` variable that contains the entire message ID.
-   **[Migrating to release 2.2](../topics/migrating-to-2.2.md)**  
In DITA-OT 2.2, the HTML5 transformation was refactored as its own plug-in and separate plug-ins were created for each of the rendering engine-specific PDF transformations.
-   **[Migrating to release 2.1](../topics/migrating-to-2.1.md)**  
In DITA-OT 2.1, the `insertVariable` template was deprecated for PDF transformations and should be replaced with the `getVariable` template. Various `dita.**out.**map.*` targets have been deprecated in favor of updated `dita.map.*` equivalents.
-   **[Migrating to release 2.0](../topics/migrating-to-2.0.md)**  
In DITA-OT 2.0, XSLT templates were converted to XSLT 2.0, variable typing was implemented, and some older templates were refactored or removed. In addition, the dita command simplifies distribution of plugins by allowing installation from a URL.
-   **[Migrating to release 1.8](../topics/migrating-to-1.8.md)**  
In DITA-OT 1.8, certain stylesheets were moved to plug-in specific folders and various deprecated Ant properties, XSLT stylesheets, parameters and modes were removed from the XHTML, PDF and ODT transformations.
-   **[Migrating to release 1.7](../topics/migrating-to-1.7.md)**  
In DITA-OT 1.7, a new preprocessing step implements flagging for HTML-based output formats. PDF processing was corrected with regard to `shortdesc` handling, and a new XSLT template mode was introduced for HTML TOC processing. Several stylesheets were moved to plug-in specific folders and deprecated properties and XSLT variables were removed.
-   **[Migrating to release 1.6](../topics/migrating-to-1.6.md)**  
In DITA-OT 1.6, various demo plug-ins were removed along with many deprecated properties, targets, templates and modes. The PDF2 transformation no longer supports the beta version of DITA from IBM, the "bkinfo" demo plug-in, or layout-masters.xml configuration.
-   **[Migrating to release 1.5.4](../topics/migrating-to-1.5.4.md)**  
DITA-OT 1.5.4 adds new extension points to configure behavior based on file extensions, declare print transformation types and add mappings to the PDF configuration catalog file. PDF output supports mirrored page layout and uses new font family definitions. Support for several new languages was added for PDF and XHTML output.

**Parent topic:** [Customizing the DITA Open Toolkit](../topics/extending-the-ot.md)

