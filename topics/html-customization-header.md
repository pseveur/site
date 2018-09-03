# Adding custom headers and footers

You add a custom header to include a publication title, company logo, or other common branding elements in HTML output. A custom footer can also be added with copyright information, legal boilerplate, or other fine print.

In HTML5 output, the contents of the header file will be wrapped in an HTML5 `header` element with the `@role` attribute set to banner.

For example, the DITA-OT documentation includes a simple header banner with the publication title and a horizontal rule to separate the header from the generated topic content:

```
<div class="header">
  <p>DITA Open Toolkit</p>
  <hr/>
</div>
```

**Note:** Header and footer files should be specified using absolute paths and must contain valid XML. A common practice is to place all content into a `div` element.

1.   Set args.hdr to include an XML file as a running header that appears above the page content. 
2.   Set args.ftr to include an XML file as a running footer that appears below the page content. 
3.   Add custom CSS rules to style headers and/or footers. 

    For example, the DITA-OT documentation stylesheet includes the following header rules:

    ```
    div.header {
      font-size: 18pt;
      margin: 0;
      padding: 0 12px;
    }
    
    div.header p {
      color: #777;
      font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
      line-height: 1.3;
      margin: 0;
    }
    
    div.header hr {
      border: 0;
      border-bottom: 1px solid #eee;
      height: 0;
    }
    ```


**Tip:** For an example of HTML output generated using this method, see the HTML5 version of the DITA-OT documentation included in the installation folder under doc/index.html.

**Parent topic:** [Setting parameters for custom HTML](../topics/html-customization-parameters.md)

**Related information**  


[Adding navigation to topics](../topics/html-customization-navigation.md)

[Adding custom CSS](../topics/html-customization-css.md)

[Handling content outside the map directory](../parameters/generate-copy-outer.md)

