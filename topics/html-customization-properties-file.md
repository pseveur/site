# Customizing HTML with a .properties file

You can also use a .properties file to reference a set of build parameters when building output with the dita command. The DITA-OT documentation uses a .properties file to include custom CSS, header branding, and table-of-contents navigation in the HTML5 output.

1.   Create a .properties file to store the parameter settings for your customization. 

    **Tip:** You can use the .properties for the DITA-OT documentation as a starting point for your own customizations. This file is available in the installation folder under docsrc/samples/properties/docs-build-html5.properties.

    For example:

    ```
    # Copy the custom .css file to the output directory:
    args.copycss = yes
    
    # Custom .css file used to style output:
    args.css = dita-ot-doc.css
    
    # Location of the copied .css file relative to the output:
    args.csspath = css
    
    # Directory that contains the custom .css file:
    args.cssroot = resources
    
    # Generate headings for sections within task topics:
    args.gen.task.lbl = YES
    
    # File that contains the running header content:
    args.hdr = ${basedir}/resources/header.xml
    
    # Base name of the Table of Contents file:
    args.html5.toc = toc
    
    # Generate a partial navigation TOC in topic pages:
    nav-toc = partial
    
    # Stop processing if there are any errors:
    processing-mode = strict
    ```

2.   Reference your .properties file with the dita command when building your output. 

    ```
    dita --input=my.ditamap --format=html5 --propertyfile=my.properties
    ```


**Note:** For an example of HTML output generated using this method, see the HTML5 version of the DITA-OT documentation included in the installation folder under doc/index.html.

**Parent topic:** [Customizing HTML output](../topics/html-customization.md)

**Related information**  


[Setting parameters for custom HTML](../topics/html-customization-parameters.md)

[Custom HTML plug-ins](../topics/html-customization-plugins.md)

