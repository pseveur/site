# Plug-in coding conventions

To ensure custom plug-ins work well with the core toolkit code and remain compatible with future releases, the DITA Open Toolkit project recommends that plug-ins use modern development practices and common coding patterns.

## Upgrade stylesheets to XSLT 2.0

The Saxon project has announced plans to remove XSLT 1.0 support from the Saxon-HE library that ships with DITA-OT:

> …we’re dropping XSLT 1.0 backwards compatibility mode from Saxon-HE, and hope to eliminate it entirely in due course.

> [https://www.xml.com/news/release-saxon-98/](https://www.xml.com/news/release-saxon-98/)

DITA-OT 3.0 and 3.0.1 included Saxon-HE 9.8.0.5, which rejects XSLT stylesheets that specify `version="1.0"`. Plug-ins with XSLT templates specifying version 1.0 will fail with the message “XSLT 1.0 compatibility mode is not available in this configuration.”

To resolve this issue, change any occurrences of `<xsl:stylesheet version="1.0">` in custom plug-in stylesheets to at least `<xsl:stylesheet version="2.0">`.

**Tip:** DITA-OT 3.0.2 includes Saxon-HE 9.8.0.7, which restores XSLT 1.0 backwards-compatibility mode, but the DITA Open Toolkit project recommends upgrading all stylesheets to XSLT 2.0 to ensure plug-ins remain compatible with future versions of DITA-OT and Saxon-HE.

## Use custom `pipeline` elements

In Ant scripts, use the XSLT module from DITA-OT instead of Ant’s built-in `xslt` or `style` tasks.

The XSLT module allows access to DITA-OT features like using the job configuration to select files in the temporary folder based on file metadata and custom XSLT extension functions.

Instead of:

```
<xslt style="${dita.plugin.example.dir}/custom.xsl"
      basedir="${dita.temp.dir}"
      destdir="${dita.output.dir}"
      includesfile="${dita.temp.dir}/${fullditatopicfile}"/>
```

use:

```
<pipeline>
  <xslt style="${dita.plugin.example.dir}/custom.xsl"
        destdir="${dita.output.dir}">
    <ditafileset format="dita" />
  </xslt>
</pipeline>
```

## Use the plug-in directory property

In Ant scripts, always refer to files in other plug-ins using the `dita.plugin.plugin-id.dir` property.

Instead of:

```
<property name="base" location="../example/custom.xsl"/>
```

use:

```
<property name="base" location="${dita.plugin.example.dir}/custom.xsl"/>
```

This fixes cases where plug-ins are installed to custom plug-in directories or the plug-in folder name doesn’t match the plug-in ID.

## Use `ditafileset` to select files

In Ant scripts, use `ditafileset` to select resources in the temporary directory.

For example, to select all images referenced by input DITA files, instead of:

```
<copy todir="${copy-image.todir}">
  <fileset dir="${user.input.dir}">
    <includes name="*.jpg"/>
    <includes name="*.jpeg"/>
    <includes name="*.png"/>
    <includes name="*.gif"/>
    <includes name="*.svg"/>
  </fileset>
</copy>
```

use:

```
<copy todir="${copy-image.todir}">
  <ditafileset format="image" />
</copy>
```

The `ditafileset` resource collection can be used to select different types of files.

|Example|Description|
|-------|-----------|
|`<ditafileset format="dita"/>`|Selects all DITA topics in the temporary directory.|
|`<ditafileset format="ditamap"/>`|Selects all DITA maps in the temporary directory.|
|`<ditafileset format="image"/>`|Selects images of all known types in the temporary directory.|

## Use the `plugin` URI scheme

In XSLT, use the `plugin` URI scheme in `xsl:import` and `xsl:include` to reference files in other plug-ins.

Instead of:

```
<xsl:import href="../../org.dita.base/xsl/common/output-message.xsl"/>
```

use:

```
<xsl:import href="plugin:org.dita.base:xsl/common/output-message.xsl"/>
```

As with the plug-in directory property in Ant, this allows plug-ins to resolve to the correct directory even when a plug-in moves to a new location. The plug-in is referenced using the syntax `plugin:plugin-id:path/within/plugin/file.xsl`.

**Parent topic:** [Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)

**Related information**  


[Customizing PDF output](../topics/pdf-customization.md)

[PDF customization approaches](../topics/pdf-customization-approaches.md)

[Best practices for custom plug-ins](../topics/plugin-best-practices.md)

