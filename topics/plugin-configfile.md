# Plug-in descriptor file

The plug-in descriptor file \(plugin.xml\) controls all aspects of a plug-in, making each extension visible to the rest of the toolkit. The file uses pre-defined extension points to locate changes, and then integrates those changes into the core DITA-OT code.

## Plug-in identifiers

Every DITA-OT plug-in must have a unique identifier composed of one or more dot-delimited tokens, for example, `com.example.rss`. This identifier is used to identify the plug-in to the DITA-OT for installation, processing, and when determining plug-in dependencies.

**Note:** The default DITA-OT plug-ins use a reverse domain naming convention, as in `org.dita.html5`; this is strongly recommended to avoid plug-in naming conflicts.

Each token can include only the following characters:

-   Lower-case letters \(a-z\)
-   Upper-case letters \(A-Z\)
-   Numerals \(0-9\)
-   Underscores \(\_\)
-   Hyphens \(-\)

## `plugin`

The root element of the plugin.xml file is `plugin`, which has a required `@id` attribute set to the unique plug-in identifier.

## Plug-in elements

The `plugin` element can contain the following child elements:

-   **`extension-point`**

    An optional element that defines a new extension point that can be used by other DITA-OT plug-ins.

    The following attributes are supported:

    |Attribute|Description|Required?|
    |---------|-----------|---------|
    |**id**|Extension point identifier|Yes|
    |**name**|Extension point description|No|

    Like plug-in identifiers, extension point identifiers are composed of one or more dot-delimited tokens.

    **Note:** Extension point identifiers should begin with the identifier of the defining plug-in and append one or more tokens, for example, `org.dita.example.pre`.

-   **`feature`**

    An optional element that supplies values to a DITA-OT extension point.

    The following attributes are supported:

    |Attribute|Description|Required?|
    |---------|-----------|---------|
    |**extension**|Identifier of the DITA-OT extension point|Yes|
    |**value**|Comma separated string value of the extension|Either the `@value` or `@file` attribute must be specified|
    |**file**|Name and path of a file containing data for the extension point. Depending on the extension point, this might be specified as an absolute path, a path relative to the plugin.xml file, or a path relative to the DITA-OT root.

|Either the `@value` or `@file` attribute must be specified|
    |**type**|Type of the `@value` attribute|No|

    If more than one `feature` element supplies values to the same extension point, the values are additive. For example, the following are equivalent:

    ```
    <feature extension="org.dita.example.extension-point" value="a,b,c"/>
    ```

    ```
    <feature extension="org.dita.example.extension-point" value="a"/>
    <feature extension="org.dita.example.extension-point" value="b"/>
    <feature extension="org.dita.example.extension-point" value="c"/>
    ```

-   **`meta`**

    An optional element that defines metadata.

    The following attributes are supported:

    |Attribute|Description|Required?|
    |---------|-----------|---------|
    |**type**|Metadata name|Yes|
    |**value**|Metadata value|Yes|

-   **`require`**

    An optional element that defines plug-in dependencies.

    The following attributes are supported:

    |Attribute|Description|Required?|
    |---------|-----------|---------|
    |**plugin**|The identifier of the required plug-in. To specify alternative requirements, separate plug-in identifiers with a vertical bar.

|Yes|
    |**importance**|Identifies whether the plug-in is `required` \(default\) or `optional`. The DITA-OT provides a warning if a required plug-in is not available.|No|

-   **`template`**

    An optional element that defines files that should be treated as templates.

    Template files can be used to integrate DITA-OT extensions. Templates typically extend the default transformation-type-specific build files via `dita:extension` elements. When the plug-in installation process runs, template files are used to recreate build files, and the specified extension points are replaced with references to the appropriate plug-ins.

    The following attributes are supported:

    |Attribute|Description|Required?|
    |---------|-----------|---------|
    |**file**|Name and path to the template file, relative to the plugin.xml file|Yes|

-   **`transtype`**

    An optional element that defines a new output format \(transformation type\).

    The following attributes are supported:

    |Attribute|Description|Required?|
    |---------|-----------|---------|
    |**name**|Transformation name|Yes|
    |**desc**|Transformation type description|No|
    |**abstract**|When true, sets the transformation type as “abstract”, meaning it can be extended by other plug-ins, but cannot be used directly. For example, the `org.dita.base` plug-in defines an abstract “base” transformation type that is extended by other DITA-OT plug-ins.

|No|
    |**extends**|Specifies the name of the transformation type being extended|No|

    The `transtype` element may define additional parameters for the transformation type using the following child elements.

    -   **`param`**

        An optional element that specifies a parameter for the transformation type.

        The following parameter attributes are supported:

        |Attribute|Description|Required?|
        |---------|-----------|---------|
        |**name**|Parameter name|Yes|
        |**desc**|Parameter description|No|
        |**type**|Parameter type \(enum, file, string\)|Yes|

    -   **`val`**

        A child of `param` \(when `@type`=enum\) that specifies an enumeration value.

        The following attributes are supported:

        |Attribute|Description|Required?|
        |---------|-----------|---------|
        |**default**|When true, sets the enumeration value as the default value of the parent `param`|Only for the default `val`|


Any extension that is not recognized by the DITA-OT is ignored. Since DITA-OT version 1.5.3, you can combine multiple extension definitions within a single plug-in.xml file; in older versions, only the last extension definition was used.

**Parent topic:** [Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)

**Related information**  


[Creating a new plug-in extension point](../topics/plugin-newextensions.md)

[Adding a new transformation type](../topics/plugin-newtranstype.md)

[Example plugin.xml file](../topics/plugin-sample.md)

