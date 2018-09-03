# Adding navigation to topics

In HTML5 output, you can set a parameter to include table-of-contents navigation in the `nav` element of each page. The navigation can be rendered in a sidebar or menu via CSS.

Earlier versions of DITA-OT used the TocJS transformation to render a JavaScript-based table of contents in an XHTML frameset for topic navigation. While this approach is still supported for XHTML output, recent toolkit versions provide a modern HTML5 navigation alternative.

As of DITA-OT 2.2, the nav-toc parameter can be used in HTML5 transformations to embed navigation directly in topics using native HTML5 elements without JavaScript or framesets.

1.   Set the nav-toc parameter to one of the following options: 
    -   The partial option creates a table of contents with the portion of the navigation hierarchy that contains the current topic \(along with its parents, siblings and children\).
    -   The full option embeds the complete navigation for the entire map in each topic.
2.   Add custom CSS rules to style the navigation. 

    For example, the DITA-OT documentation stylesheet includes the following rules to place the table of contents on the left side of the browser viewport and highlight the current topic in bold:

    ```
    nav[role=toc] {
      float: left;
      width: 300px;
    }
    
    nav[role=toc] li.active > a {
      font-weight: bold;
    }
    ```


**Tip:** For an example of HTML output generated using this method, see the HTML5 version of the DITA-OT documentation included in the installation folder under doc/index.html.

**Parent topic:** [Setting parameters for custom HTML](../topics/html-customization-parameters.md)

**Related information**  


[Adding custom CSS](../topics/html-customization-css.md)

[Adding custom headers and footers](../topics/html-customization-header.md)

[Handling content outside the map directory](../parameters/generate-copy-outer.md)

