# Extension points

The DITA Open Toolkit provides a series of extension points that can be used to integrate changes into the core code. Extension points are defined in the plugin.xml file for each plug-in. When plug-ins are installed, the DITA-OT makes each extension visible to the rest of the toolkit.

-   **[All DITA-OT extension points](../extension-points/all-extension-points.md)**  
The pre-defined extension points can be used to extend the functionality of the DITA-OT. If your toolkit installation includes custom plug-ins that define additional extension points, you can add to this list by rebuilding the DITA-OT documentation.
-   **[General extension points](../extension-points/plugin-extension-points-general.md)**  
These extension points enable you to extend the DITA-OT. You can add Ant targets or imports; add a Java library to the classpath parameter; add a new transformation type; extend a catalog file; add new diagnostic messages, and more.
-   **[Pre-processing extension points](../extension-points/plugin-extension-points-pre-processing.md)**  
You can use these extension points to run an Ant target before or after the pre-processing stage. If necessary, you can also run an Ant target before a specific pre-processing step — but this approach is not recommended.
-   **[XSLT-import extension points](../extension-points/plugin-extension-points-xslt-import.md)**  
You can use these extension points to override XSLT processing steps in pre-processing and certain transformation types. The value of the `@file` attribute in the `feature` element specifies a relative path to an XSL file in the current plug-in. The plug-in installer adds a XSL import statement to the default DITA-OT code, so that the XSL override becomes part of the normal build.
-   **[XSLT-parameter extension points](../extension-points/plugin-extension-points-xslt-parameters.md)**  
You can use theses extension points to pass parameters into existing XSLT steps in both the pre-processing pipeline and DITA-OT transformation. The parameters generally will be available as global `xsl:param` values with XSLT overrides.
-   **[Version and support information](../extension-points/plugin-extension-points-support.md)**  
You can use these extension points to define version and support information for a plug-in. Currently, the DITA-OT does not do anything with this information, but it might do so in the future.
-   **[Extension points by plug-in](../extension-points/extension-points-by-plugin.md)**  
The default plug-ins that ship with the DITA Open Toolkit include a series of extension points that can be used to modify various aspects of toolkit processing.

**Parent topic:** [Customizing the DITA Open Toolkit](../topics/extending-the-ot.md)

