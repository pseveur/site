# Migrating to release 3.1

DITA-OT 3.1 includes support for DITA 1.3 SVG domain elements, enhanced `codeblock` processing, and incremental improvements to Lightweight DITA processing and PDF output.

**Note:** This topic provides a summary of changes in DITA-OT 3.1 that may require modifications to custom stylesheets or plug-ins.

## Custom if/unless attributes in Ant scripts

Ant scripts for DITA-OT builds now make use of `@if:set` and `@unless:set` attributes in the Ant namespace, which can be used to control whether parameters are passed to XSLT modules. These attributes replace custom implementations of `if` and `unless` logic introduced before Ant had this capability.

If your plug-ins include Ant scripts that use `@if` or `@unless` on `param` elements that pass XSLT parameters, add the following namespace attributes to the root project:

-   `xmlns:if`=`"ant:if"`
-   `xmlns:unless`=`"ant:unless"`

In custom Ant build files and in any files that supply parameters to existing DITA-OT XSLT modules, replace all occurrences of `if="property"` on `param` elements with `if**:set**="property"` \(and `unless` → `unless**:set**` respectively\).

```
<root xmlns:if="ant:if" xmlns:unless="ant:unless">
  <param name="antProperty" expression="${antProperty}"
         if**:set**="antProperty"/>
</root>
```

For more information on passing parameters to existing XSLT steps, see [XSLT-parameter extension points](../extension-points/plugin-extension-points-xslt-parameters.md).

## PDF – Enabling line numbers in codeblocks

The `codeblock.generate-line-number` template mode default has been changed to check for the `show-line-numbers` keyword in the `@outputclass` attribute. Earlier versions of DITA-OT required custom PDF plug-ins to override the template mode to return `true()`.

**Parent topic:** [Migrating customizations](../topics/migration.md)

