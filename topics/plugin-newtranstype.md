# Adding a new transformation type

Plug-ins can add an entirely new transformation type. The new transformation type can be very simple, such as an XHTML build that creates an additional control file; it also can be very complex, adding any number of new processing steps.

You can use the `dita.conductor.transtype.check` and `dita.transtype.print` extension points to define new transformation types.

When a transformation type is defined, the build expects Ant code to be integrated to define the transformation process. The Ant code must define a target based on the name of the transformation type; if the transformation type is "new-transform", the Ant code must define a target named dita2new-transform.

1.   Create an Ant project file for the new transformation. This project file must define a target named "dita2new-transtype," where new-transtype is the name of the new transformation type. 
2.   Create the following feature: 

    ```
    <plugin id="plugin-id ">
      <feature extension="dita.conductor.transtype.check" 
               value="new-transtype"/>
      **<feature extension="dita.transtype.print" value="new-transtype"/\>**
      <feature extension="dita.conductor.target.relative" file="ant-file"/>
    </plugin>
    ```

    where:

    -   plugin-id is the plug-in identifier, for example, com.dita-ot.pdf.
    -   new-transtype is the name of the new transformation, for example, dita-ot-pdf.
    -   ant-file is the name of the Ant file, for example, build-dita-ot-pdf.xml.
    Exclude the content that is highlighted in bold if the transformation is not intended for print.

3.   Install the plug-in. 

You now can use the new transformation.

## Examples

The following plugin.xml file defines a new transformation type named "newtext"; it also defines the transformation type to be a print type. The build will look for a dita2newtext target.

```
<plugin id="com.example.newtext">
  <feature extension="dita.conductor.transtype.check" value="newtext"/>
  <feature extension="dita.transtype.print" value="newtext"/>
  <feature extension="dita.conductor.target.relative" 
           file="build-newtext.xml"/>
</plugin>
```

While the org.dita.html5 plug-in was separated from `common-html` in version 2.4, the following example shows how earlier versions of that plug-in used the `transtype` element to extend the common HTML transformation with a new html5 transformation type and define a new nav-toc parameter with three possible values:

```
**<transtype name="html5" extends="common-html" desc="HTML5"\>**
  <param name="nav-toc" type="enum" 
         desc="Specifies whether to generate navigation in topic pages.">
    <val default="true" desc="No TOC">none</val>
    <val desc="Partial TOC that shows the current topic">partial</val>
    <val desc="Full TOC">full</val>
  </param>
</transtype>
```

**Parent topic:** [Plug-in applications](../topics/plugin-applications.md)

**Related information**  


[General extension points](../extension-points/plugin-extension-points-general.md)

[Plug-in descriptor file](../topics/plugin-configfile.md)

[Installing plug-ins](../topics/plugins-installing.md)

