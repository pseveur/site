# Customizing DITA-OT with plug-ins

You can install or create DITA-OT plug-ins to change the default output types in various ways, add entirely new kinds of output formats, or implement DITA topic specializations.

A plug-in consists of a directory, typically stored within the plugins/ directory inside of the DITA-OT. Every plug-in is controlled by a file named plugin.xml, which is located in the root directory of the plug-in.

## Plug-in benefits

Plug-ins allow you to extend the toolkit in a way that is consistent, easy-to-share, and possible to preserve through toolkit upgrades.

The DITA-OT plug-in mechanism provides the following benefits:

-   Plug-ins can easily be shared with other users, teams, or companies. Typically, all users need to do is to unzip and run a single installation command. With many builds, even that installation step is automatic.
-   Plug-ins permit overrides or customizations to grow from simple to complex over time, with no increased complexity to the extension mechanism.
-   Plug-ins can be moved from version to version of the DITA-OT simply by reinstalling or copying the directory from one installation to another. There is no need to re-integrate code based on updates to the core processing of the DITA-OT.
-   Plug-ins can build upon each other. If you like a plug-in, simply install that plug-in, and then create your own plug-in that builds on top of it. The two plug-ins can then be distributed to your team as a unit, or you can share your own extensions with the original provider.

## Working with plug-ins

Extended documentation for creating plug-ins is provided in the following topics.

-   **[Installing plug-ins](../topics/plugins-installing.md)**  
Use the dita command to install a plug-in.
-   **[Removing plug-ins](../topics/plugins-removing.md)**  
Use the dita command to uninstall a plug-in.
-   **[Plug-in descriptor file](../topics/plugin-configfile.md)**  
The plug-in descriptor file \(plugin.xml\) controls all aspects of a plug-in, making each extension visible to the rest of the toolkit. The file uses pre-defined extension points to locate changes, and then integrates those changes into the core DITA-OT code.
-   **[Plug-in dependencies](../topics/plugin-dependencies.md)**  
A DITA-OT plug-in can be dependent on other plug-ins. Prerequisite plug-ins are installed first, which ensures that the DITA-OT handles XSLT overrides correctly.
-   **[Plug-in applications](../topics/plugin-applications.md)**  
Plug-ins allow you to extend the functionality of the DITA-OT. This might entail adding support for specialized document types, integrating processing overrides, or defining new output transformations.
-   **[Example plugin.xml file](../topics/plugin-sample.md)**  
The following is a sample of a plugin.xml file. This file adds support for a new set of specialized DTDs, and includes an override for the XHTML output processor.
-   **[Best practices for custom plug-ins](../topics/plugin-best-practices.md)**  
Adhering to certain development practices will properly isolate your code from that of the DITA Open Toolkit. This will make it easier to you to upgrade to new versions of the DITA-OT when they are released.
-   **[Plug-in coding conventions](../topics/plugin-coding-conventions.md)**  
To ensure custom plug-ins work well with the core toolkit code and remain compatible with future releases, the DITA Open Toolkit project recommends that plug-ins use modern development practices and common coding patterns.

**Parent topic:** [Customizing the DITA Open Toolkit](../topics/extending-the-ot.md)

