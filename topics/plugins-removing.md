# Removing plug-ins

Use the dita command to uninstall a plug-in.

1.   At the command-line prompt, enter the following command: 

    ```
    dita-ot-dir/bin/dita --uninstall plug-in-id
    ```

    where:

    -   dita-ot-dir is the DITA-OT installation directory.
    -   plug-in-id is the unique ID of the plug-in, as defined in the plug-in's configuration file \(plugin.xml\).
    **Attention:** The --uninstall option also removes the corresponding subdirectory from the plugins folder.

    **Tip:** Add the absolute path for dita-ot-dir/bin to the PATH environment variable to run the dita command from any location on the file system without typing the path.


**Parent topic:** [Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)

**Related information**  


[Arguments and options for the dita command](../parameters/dita-command-arguments.md)

