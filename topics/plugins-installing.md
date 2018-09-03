# Installing plug-ins

Use the dita command to install a plug-in.

1.   At the command-line prompt, enter the following command: 

    ```
    dita-ot-dir/bin/dita --install plug-in-zip
    ```

    where:

    -   dita-ot-dir is the DITA-OT installation directory.
    -   plug-in-zip is the filename or URL of the plug-in's distribution ZIP file \(optional\).
    **Note:** If no filename or URL argument is provided, the installation process reloads the current set of plug-ins from the plugins directory. This approach can be used to add or remove multiple plug-ins at once, or any individual plug-ins you have already copied to \(or removed from\) the plugins directory. 

    **Tip:** Add the absolute path for dita-ot-dir/bin to the PATH environment variable to run the dita command from any location on the file system without typing the path.


**Parent topic:** [Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)

**Related information**  


[Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)

[Arguments and options for the dita command](../parameters/dita-command-arguments.md)

