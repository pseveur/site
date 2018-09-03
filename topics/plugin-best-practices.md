# Best practices for custom plug-ins

Adhering to certain development practices will properly isolate your code from that of the DITA Open Toolkit. This will make it easier to you to upgrade to new versions of the DITA-OT when they are released.

-   Use a properly-constructed DITA-OT plug-in.
-   Use a version control system to store your code.
-   Never modify any of the core DITA-OT code.

    **Tip:** You may want to set the permissions on default plug-in directories such as org.dita.pdf2 to “read-only” to ensure that you do not accidentally modify the files within as you develop your customized plug-in.

-   Avoid copying entire DITA-OT files into your customization plug-in. When you only copy the attribute sets and templates that you need to override, there is less risk of impact from new features or fixes in the base code, making your code more stable and easier to upgrade between releases.
-   If you only need to change a few attribute sets and templates, you may prefer to store your overrides in custom.xsl files, or a simple folder hierarchy within your custom plug-in.
-   In cases that require substantial customizations, you may prefer to organize the files in a folder structure that mimics the hierarchy of the default plug-in you are customizing. This facilitates comparisons with the default settings in the base plug-in and makes it easier to migrate your changes to new toolkit versions.
-   Upgrade your customization plug-in to new versions of the DITA-OT regularly. Do not wait through several major releases before upgrading.

**Parent topic:** [Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)

**Related information**  


[Customizing PDF output](../topics/pdf-customization.md)

[PDF customization approaches](../topics/pdf-customization-approaches.md)

[Plug-in coding conventions](../topics/plugin-coding-conventions.md)

