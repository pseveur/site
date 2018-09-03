# Enabling debug mode

When the debug mode is enabled, additional diagnostic information is written to the log file. This information, which includes environment variables and stack trace data, can help you determine the root cause of a problem.

1.   From the command prompt, add the following parameters: 

    |Application|Parameters|
    |-----------|----------|
    |**dita command**|--debug, -debug, or -d|
    |**Ant**|`-v -Dargs.debug=yes`|

    You also can add a `property` element to an Ant target in your build file, for example:

    ```
    <property name="args.debug" value="yes"/>
    ```


**Parent topic:** [Error messages and troubleshooting](../topics/troubleshooting-overview.md)

