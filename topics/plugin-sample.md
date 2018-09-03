# Example plugin.xml file

The following is a sample of a plugin.xml file. This file adds support for a new set of specialized DTDs, and includes an override for the XHTML output processor.

This plugin.xml file would go into a directory such as DITA-OT/plugins/music/ and referenced supporting files would also exist in that directory. A more extensive sample using these values is available in the actual music plug-in, available on [SourceForge](https://sourceforge.net/projects/dita-ot/files/Plug-in_%20Music/).

```
<plugin id="org.metadita.specialization.music">
  <feature extension="dita.specialization.catalog.relative" 
           file="catalog-dita.xml"/>
  <feature extension="dita.xsl.xhtml" file="xsl/music2xhtml.xsl"/>
</plugin>
```

**Parent topic:** [Customizing DITA-OT with plug-ins](../topics/custom-plugins.md)

**Related information**  


[Plug-in descriptor file](../topics/plugin-configfile.md)

