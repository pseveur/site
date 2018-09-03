# Re-usable components

Warehouse topic used to store re-usable content for concept topics or other constructs that would not be valid in the existing warehouse task conref-task.dita.

## Upgrade stylesheets to XSLT 2.0

The Saxon project has announced plans to remove XSLT 1.0 support from the Saxon-HE library that ships with DITA-OT:

> …we’re dropping XSLT 1.0 backwards compatibility mode from Saxon-HE, and hope to eliminate it entirely in due course.

> [https://www.xml.com/news/release-saxon-98/](https://www.xml.com/news/release-saxon-98/)

DITA-OT 3.0 and 3.0.1 included Saxon-HE 9.8.0.5, which rejects XSLT stylesheets that specify `version="1.0"`. Plug-ins with XSLT templates specifying version 1.0 will fail with the message “XSLT 1.0 compatibility mode is not available in this configuration.”

To resolve this issue, change any occurrences of `<xsl:stylesheet version="1.0">` in custom plug-in stylesheets to at least `<xsl:stylesheet version="2.0">`.

**Tip:** DITA-OT 3.0.2 includes Saxon-HE 9.8.0.7, which restores XSLT 1.0 backwards-compatibility mode, but the DITA Open Toolkit project recommends upgrading all stylesheets to XSLT 2.0 to ensure plug-ins remain compatible with future versions of DITA-OT and Saxon-HE.

