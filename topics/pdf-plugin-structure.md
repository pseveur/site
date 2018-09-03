# PDF plug-in structure

In cases that require substantial customizations, it is often useful to organize the files in a folder structure that mimics the hierarchy of the default PDF plug-in. This method facilitates comparisons with the default settings in the base PDF plug-in and makes it easier to migrate customizations to new toolkit versions.

**Note:** For simpler customizations, you may want to structure your plug-in differently, but the information in this topic may help you to locate the files you need to customize.

The original Idiom plug-in used its own extension mechanism to provide overrides to the PDF transformation. With this approach, a dedicated folder within the plug-in was used to store customized files. While this method is no longer recommended, the same organization principles can be used in custom PDF plug-ins.

To begin creating a new custom plug-in, you can copy the plugins/org.dita.pdf2/Customization folder to a new folder, such as plugins/com.company.pdf.

DITA-OT provides template files that you can start with throughout the Customization directory structure. These files end in the suffix `.orig` \(for example, catalog.xml.orig\). To enable these files, copy them to your custom plug-in and remove the `.orig` suffix. For example, copy catalog.xml.orig to catalog.xml. You can then make modifications to the copy in your custom plug-in folder.

Things you can currently override include:

-   Custom XSL via xsl/custom.xsl and attrs/custom.xsl
-   Layout overrides via layout-masters.xsl
-   Font overrides via font-mappings.xml
-   Per-locale variable overrides via common/vars/\[language\].xml
-   I18N configuration via i18n/\[language\].xml
-   Index configuration via index/\[language\].xml

When customizing any of these areas, modify the relevant file\(s\) in your custom plug-in folder. Then, to enable the changes in the publishing process, you find the corresponding entry for each file you modified in the catalog.xml file.

It should look like this:

```
<!--uri name="cfg:fo/attrs/custom.xsl" uri="fo/attrs/custom.xsl"/-->
```

Remove the comment markers `!--` and `--` to enable the change:

```
<uri name="cfg:fo/attrs/custom.xsl" uri="fo/attrs/custom.xsl"/>
```

Your customization should now be enabled as part of the publishing process.

When your custom plug-in is installed, the files in its subfolders will override the out-of-the-box settings from their counterparts in org.dita.pdf2/cfg/fo/attrs and org.dita.pdf2/xsl/fo.

## Custom artwork: the common/artwork folder

This folder houses custom artwork files that override the standard ones in org.dita.pdf2/cfg/common/artwork. These files are used to graphically identify different types of DITA `note` element.

The mapping between `note` type and graphic is contained in a subset of the locale-dependent variable files, such as

```
cfg/common/vars
```

The variables that control `note` graphics all follow the form

```
<variable id="{type} Note Image Path"> {Path to image file} </variable>
```

where \{type\} contains a possible value for the `note` `@type` attribute.

## Index configuration: the common/index folder

This folder houses custom index definition files that override the standard ones in org.dita.pdf2/cfg/common/index. Each file contains data for a single language, and should take that language’s ISO 639-1 language designator as its name \(for example, pt.xml for Portuguese\). If necessary, locale-specific customizations can be provided by adding a region designator to the file name \(for example, pt\_BR.xml for Brazilian Portuguese\).

The index files consist of `index.group` elements which contain sorting information on one or more characters. Index groups are listed in sort order \(“specials” before numbers, numbers before the letter ‘A‘, etc\), and the `char.set` entries they contain are also listed in sort order \(uppercase before lowercase\).

The best way to start editing a custom index file is by making a copy of the original from org.dita.pdf2/cfg/common/index and making changes as desired.

In order to apply a custom index definition to your publishing outputs, edit catalog.xml and uncomment the appropriate entry in the “Index configuration override entries” section.

## Variable overrides: the common/vars folder

This folder houses custom variable definitions that override the standard ones in org.dita.pdf2/cfg/common/vars. As with index configuration, Each file contains data for a single language, and should take that language’s ISO 639-1 language designator as its name.

Variable files contain a set of `variable` elements, identified by their `@id` attribute. The variable definitions are used to store static text that is used as part of the published outputs. For example, page headers, hyperlinks, etc. The id attribute for each variable should make it clear how the variable text is being used.

Some variables contain `param` elements which indicate parameter values that are substituted at publish time by the XSL. For example, a page number that is being generated as part of the publishing process might be identified by <param ref-name="number"/\> When editing or translating a variable file, these should be included in the translation, though they can be moved and rearranged within the `variable` content as needed.

The best way to start editing a custom variables file is by making a copy of the original from org.dita.pdf2/cfg/common/vars and making changes as desired. When adding a new language, start from an existing language’s list of variables and translate each entry as needed.

Note that unchanged `variable` elements can be omitted: the custom variables file need only include those `variable` elements which you have modified. Variables not found in the custom file will are taken from the standard variable files.

Applying a custom variable does not require modifying the catalog.xml file. The publishing process will automatically use any custom variables definitions in place of the original ones.

## Custom attributes: the fo/attrs folder

This folder houses custom attribute configuration files that override the standard ones in org.dita.pdf2/cfg/fo/attrs. These files define the appearance of different elements in XML assets when they are rendered to PDF output. The different DITA elements are organized into files by element type – index-related definitions in index-attr.xsl, table-related definitions in tables-attr.xsl, etc.

The XSL attribute sets defined in these files can be used to override the presentation of DITA elements, including font size, color, spacing, etc.

## Internationalization configuration: the fo/i18n folder

This folder houses custom configuration files that override the standard ones in org.dita.pdf2/cfg/fo/i18n. As with index configuration and variable overrides, each file contains data for a single language, and should take that language’s ISO 639-1 language designator as its name.

Each configuration file contains mappings of certain symbols to the Unicode codepoint which should be used to represent them in the given locale.

The best way to start editing a custom configuration is by making a copy of the original from org.dita.pdf2/cfg/fo/i18n and making changes as desired.

In order to apply a custom configuration to your publishing outputs, edit catalog.xml and uncomment the appropriate entry in the “I18N configuration override entries” section.

## Custom stylesheets: the fo/xsl folder

This folder houses custom stylesheet files that override the default stylesheets in org.dita.pdf2/xsl/fo.

You can use custom stylesheets to implement additional processing routines or adjust the output generated by the default toolkit processing.

**Parent topic:** [Customizing PDF output](../topics/pdf-customization.md)

