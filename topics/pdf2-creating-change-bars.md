# Generating revision bars

If you use Antenna House Formatter or RenderX XEP, you can generate revision bars in your PDF output by using the `@changebar` attribute of the DITAVAL `revprop` element.

**Note:** FOP 1.1 does not support the XSL `fo:change-bar` formatting object.

The DITA specification for `@changebar` simply says:

-   > **`@changebar`**

    > When flag has been set, specify a changebar color, style, or character, according to the changebar support of the target output format. If flag has not been set, this attribute is ignored.


The syntax for `@changebar` is a sequence of name and value pairs that are delimited by semicolons, for example:

```
<revprop action="flag" val="rev01"
 **changebar="color:black;style:solid;width:0.5pt"**
/>
```

To produce a revision bar, you must specify a value for style and should specify a value for width so you get a visible rule.

Each name and value pair corresponds to an attribute of the [XSL-FO fo:change-bar-begin element](http://www.w3.org/TR/xsl/#fo_change-bar-begin). The following attributes and values are available:

-   **style**

    The style to use for the line, as for other XSL-FO rules \([@change-bar-style](http://www.w3.org/TR/xsl/#change-bar-style)\). The value solid produces a solid rule; the default value is none.

-   **color**

    Any color value recognized by XSL-FO, including the usual color names or a hex color value. The default value is black.

-   **offset**

    The space to offset the revision bar from the edge of the text column. You can use points \(pt\) or millimeters \(mm\).

-   **placement**

    The side of the text column on which to place the revision bar. The allowed values are start \(left side for left-to-right languages\) and end \(right side for left-to-right languages\). The default value is start.

-   **width**

    The width of the rule as a measurement value. Typical values are 1pt and 0.5pt, which renders a hairline rule.


XSL-FO 1.1 does not provide for revision bars that are not rules, so there is no way to get text revision indicators instead of rules, for example, using a number in place of a rule. Antenna House Formatter provides a proprietary extension to enable this, but the DITA-OT PDF transformation does not take advantage of it.

**Parent topic:** [Customizing PDF output](../topics/pdf-customization.md)

