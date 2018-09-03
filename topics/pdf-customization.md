# Customizing PDF output

You can create custom DITA-OT plug-ins that build on the default DITA to PDF transformation. Plug-ins can customize covers and page layouts, modify formatting, override logic of the default PDF plug-in, and much more.

-   **[PDF customization approaches](../topics/pdf-customization-approaches.md)**  
Various methods may be used to customize the PDF output produced by the DITA Open Toolkit. Each of these approaches have advantages and shortcomings that should be considered when preparing a customization project. Some of these methods are considered “anti-patterns” with disadvantages that outweigh their apparent appeal. In most cases, you should create a custom PDF plug-in.
-   **[Types of custom PDF plug-ins](../topics/pdf-customization-plugin-types.md)**  
There are two common types of plug-ins: A plug-in that simply sets the DITA-OT parameters to be used when a PDF is generated, and a plug-in that overrides aspects of the base DITA-OT PDF transformation. A plug-in can, of course, do both of these things.
-   **[PDF plug-in structure](../topics/pdf-plugin-structure.md)**  
In cases that require substantial customizations, it is often useful to organize the files in a folder structure that mimics the hierarchy of the default PDF plug-in. This method facilitates comparisons with the default settings in the base PDF plug-in and makes it easier to migrate customizations to new toolkit versions.
-   **[Example: Creating a simple PDF plug-in](../topics/pdf-customization-example.md)**  
This scenario walks through the process of creating a very simple plug-in \(`com.example.print-pdf`\) that creates a new transformation type: print-pdf.
-   **[Resources for custom PDF plug-ins](../topics/pdf-customization-resources.md)**  
There are several external resources that can help you generate and refine custom PDF plug-ins for the DITA Open Toolkit.
-   **[Generating revision bars](../topics/pdf2-creating-change-bars.md)**  
If you use Antenna House Formatter or RenderX XEP, you can generate revision bars in your PDF output by using the `@changebar` attribute of the DITAVAL `revprop` element.

**Parent topic:** [Customizing the DITA Open Toolkit](../topics/extending-the-ot.md)

**Related information**  


[Best practices for custom plug-ins](../topics/plugin-best-practices.md)

[Plug-in coding conventions](../topics/plugin-coding-conventions.md)

