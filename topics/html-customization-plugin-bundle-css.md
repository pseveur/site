# Bundling CSS in a custom HTML plug-in

You can create a DITA-OT plug-in that provides a custom stylesheet with the typography and colors that define your corporate identity. Coworkers can install this plug-in to ensure consistent HTML output across projects without having to copy the stylesheet to each project.

This scenario walks through the process of creating a very simple plug-in \(`com.example.html5.custom.css`\) that creates a new transformation type: html5-custom-css.

The html5-custom-css transformation includes a custom CSS file and sets three parameters to integrate the custom stylesheet in the generated HTML5 output. These parameter settings make the following changes:

-   Specify the name of the custom .css file with args.css.

    The value of this parameter tells DITA-OT to use the custom .css file provided by the plug-in.

-   Ensure that the custom .css file is copied to the output directory by setting args.copycss to yes.

-   Set the relative path for .css files in the output folder with args.csspath.

    CSS files are copied to the root level of the output folder by default. Setting this parameter places CSS files in a dedicated subfolder.


All three parameters are set in the Ant script \(build.xml\).

1.   In the plugins directory, create a directory named com.example.html5.custom.css. 
2.   In the new com.example.html5.custom.css directory, create a plug-in configuration file \(plugin.xml\) that declares the new html5-custom-css transformation and its dependencies. 

    ```
    <?xml version="1.0" encoding="UTF-8"?>
    *<!-- Plug-in to extend DITA-OT HTML5 output with a custom CSS file --\>*
    <plugin id="com.example.html5.custom.css">
      **<require plugin="org.dita.html5"/\>**
      **<feature extension="dita.conductor.transtype.check"
               value="html5-custom-css"/\>**
      <feature extension="dita.conductor.target.relative" file="build.xml"/>
    </plugin>
    ```

    **Note:** This plug-in will extend the default HTML5 transformation, so the `require` element explicitly defines org.dita.html5 as a dependency.

3.   In the com.example.html5.custom.css directory, create a subdirectory named css. 
4.   In the new css subdirectory, create a file named custom.css with your custom CSS rules. 

    ```
    */\* These custom styles extend the DITA Open Toolkit default styles \*/*
    
    body {
      color: red
    }
    ```

    **Tip:** When you first create the plug-in, you may want to include a rule in your custom stylesheet that makes it readily apparent when the custom styles are applied \(the example above will change body text to “red”\). Once you have verified that the plug-in works as intended, replace the placeholder rule with your own custom styles.

5.   Add an Ant script \(build.xml\) to define the transformation type. 

    ```
    <?xml version='1.0' encoding='UTF-8'?>
    *<!-- Plug-in to extend DITA-OT HTML5 output with a custom CSS file --\>*
    <project name="com.example.html5.custom.css">
      <target name="dita2html5-custom-css">
        <antcall target="dita2html5">
          *<!-- Custom .css file used to style output --\>*
          **<param name="args.css" 
                 value="$\{dita.plugin.com.example.html5.custom.css.dir\}/css/custom.css"/\>**
          *<!-- Copy the custom .css file to the output directory --\>*
          <param name="args.copycss" value="yes"/>
          *<!-- Location of the copied .css file relative to the output --\>*
          <param name="args.csspath" value="css"/>
        </antcall>
      </target>
    </project>
    ```


The new plug-in directory has the following layout and files:

```
com.example.html5.custom.css
├── build.xml
├── css
│   └── custom.css
└── plugin.xml
```

1.  Run dita-ot-dir/bin/dita --install to install the plug-in and make the html5-custom-css transformation available.
2.  Build output with the new transformation type to verify that the plug-in works as intended.

    ```
    dita-ot-dir/bin/dita --input=my.ditamap --format=html5-custom-css
    ```

3.  Refine the styles in your custom.css file as necessary.

**Parent topic:** [Custom HTML plug-ins](../topics/html-customization-plugins.md)

**Related information**  


[HTML-based output parameters](../parameters/parameters-base-html.md)

[Adding custom CSS](../topics/html-customization-css.md)

