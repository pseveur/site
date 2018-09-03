# Types of custom PDF plug-ins

There are two common types of plug-ins: A plug-in that simply sets the DITA-OT parameters to be used when a PDF is generated, and a plug-in that overrides aspects of the base DITA-OT PDF transformation. A plug-in can, of course, do both of these things.

## Plug-in that only provides DITA-OT parameters

You might want to build a transformation type that uses a transformation as-is; however, you might want ensure that certain DITA-OT parameters are used. For example, consider the following scenario:

You want to ensure that PDFs generated for internal review have the following characteristics:

-   Use company style sheets
-   Make draft comments visible to the reviewers, as they contain queries from the information developers
-   Print the file names of the graphics underneath figures, so that graphic artists can more quickly respond to requested changes

To accomplish this, you can create a new plug-in. In the Ant script that defines the transformation type, specify the DITA-OT parameters. For example, to render draft comments and art labels, add `property` elements to specify the DITA-OT parameters:

```
<?xml version='1.0' encoding='UTF-8'?>
<project name="com.example.draft.pdf">
  <target name="dita2draft.pdf.init">
    <property name="customization.dir"
              location="${dita.plugin.com.example.draft.pdf.dir}/cfg"/>
    **<property name="args.draft" value="yes"/\>**
    **<property name="args.artlbl" value="yes"/\>**
  </target>
  <target name="dita2draft.pdf"
          depends="dita2draft.pdf.init, dita2production.pdf,dita2pdf2"/>
</project>
```

## Plug-in that overrides the base PDF transformation

Production uses of the DITA-OT typically rely on a custom PDF plug-in to render PDFs that are styled to match corporate or organizational guidelines. Such customization plug-ins often override the following aspects of the DITA-OT's default output:

-   Generated text strings
-   XSL templates
-   XSL-FO attribute sets

**Parent topic:** [Customizing PDF output](../topics/pdf-customization.md)

