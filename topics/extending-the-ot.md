# Customizing the DITA Open Toolkit

There are several ways to customize and extend the toolkit. You can adjust various aspects of the default output by setting parameters or using custom stylesheets. For more complex customizations, use custom DITA-OT plug-ins to override other parts of processing.

A single XSL file can be used as an override by passing it in as a parameter. For example, when building XHTML content, the XSL parameter allows users to specify a single local XSL file \(inside or outside of the toolkit\) that is called in place of the default XHTML code. Typically, this code imports the default processing code, and overrides a couple of processing routines. This approach is best when the override is very minimal, or when the style varies from build to build. However, any extension made with this sort of override is also possible with a plug-in.

Creating a plug-in can be very simple to very complex, and is generally the best method for changing or extending the toolkit. Plug-ins can be used to accomplish almost any modification that is needed for toolkit processing, from minor style tweaks to extensive, complicated new output formats.

Editing DITA-OT code directly is strongly discouraged. Modifying the code directly significantly increases the work and risk involved with future upgrades. It is also likely that such modifications will break plug-ins provided by others, limiting the functions available to the toolkit.

**Warning:** Any changes made directly in the code would be overwritten when upgrading to newer versions of DITA-OT, so users that have customized their toolkit installation in this way are often “stuck” on older versions of the toolkit and unable to take advantage of improvements in recent versions of DITA-OT.

-   **[Customizing HTML output](../topics/html-customization.md)**  
You can adjust the look and feel of your HTML output without creating a DITA-OT plug-in by including custom CSS, headers and footers, or table-of-contents navigation in topics.
-   **[Customizing PDF output](../topics/pdf-customization.md)**  
You can create custom DITA-OT plug-ins that build on the default DITA to PDF transformation. Plug-ins can customize covers and page layouts, modify formatting, override logic of the default PDF plug-in, and much more.
-   **[Globalizing DITA content](../topics/globalization.md)**  
The DITA standard supports content that is written in or translated to any language. In general, the DITA Open Toolkit passes content through to the output format unchanged. The DITA-OT uses the values for the `@xml:lang` and `@dir` attributes that are set in the source content to provide globalization support.
-   **[Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)**  
You can install or create DITA-OT plug-ins to change the default output types in various ways, add entirely new kinds of output formats, or implement DITA topic specializations.
-   **[Extension points](../extension-points/plugin-extension-points.md)**  
The DITA Open Toolkit provides a series of extension points that can be used to integrate changes into the core code. Extension points are defined in the plugin.xml file for each plug-in. When plug-ins are installed, the DITA-OT makes each extension visible to the rest of the toolkit.
-   **[Migrating customizations](../topics/migration.md)**  
If you have XSL transformation overrides, plug-ins or other customizations written prior to DITA-OT 3.1, you may need to make changes to ensure your overrides work properly with the latest toolkit versions.
-   **[Rebuilding the DITA-OT documentation](../topics/rebuilding-the-dita-ot-documentation.md)**  
The DITA-OT ships with a [Gradle](https://gradle.org) build script that enables you to rebuild the toolkit documentation. This is especially helpful if your environment contains plug-ins that add new extension points, messages, or parameters to the toolkit.

