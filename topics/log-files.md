# Log files

When you run the DITA-OT, key information is logged on the screen. This information can also be written to a log file. If you encounter a problem, you can analyze this information to determine the source of the problem and then take action to resolve it.

The logging behavior varies depending on whether you use the dita command or Ant to invoke a toolkit build.

-   **dita command**

    By default, only warning and error messages are written to the screen. If you use the -v option, logging will be more verbose and informative messages are also written out. The -l option can be used to write the log messages into a file.

-   **Ant**

    By default, status information is written to the screen. If you issue the -l parameter, the build runs silently and the information is written to a log file with the name and location that you specified.


## Using other Ant loggers

You also can use other Ant loggers; see [Listeners & Loggers](https://ant.apache.org/manual/listeners.html) in the Ant documentation for more information.

For example, you can use the **AnsiColorLogger** to colorize the messages written on the screen.

-   **dita command**

    To use a custom Ant logger with the dita command, add the logger to the `ANT_ARGS` environment variable by calling the following command before calling the dita command:

    ```
    export ANT_ARGS="-logger org.apache.tools.ant.listener.AnsiColorLogger"
    ```

    Now you will get colorized messages when the dita command runs.

    **Tip:** Environment variables can also be set permanently. See [How do I set or change the PATH system variable?](https://www.java.com/en/download/help/path.xml) for information on how to set the `PATH` environment variable. You can set the `ANT_ARGS` environment variable in the same way.

-   **Ant**

    If you prefer to launch the DITA-OT directly from Ant, you can also add the logger to the `ANT_ARGS` environment variable, as explained above. You can also set the logger with the `-logger` parameter when calling Ant.

    ```
    ant -logger org.apache.tools.ant.listener.AnsiColorLogger
    ```


## FOP debug logging

In PDF processing with Apache™ FOP, DITA-OT 3.1 now uses the Simple Logging Facade for Java \(SLF4J\), allowing for better control and formatting of FOP log messages. To reduce noise on the console, all FOP messages are set to the Info level and hidden by default.

To enable debug logging, modify the config/logback.xml file or add your own logback.xml to the classpath with a higher priority to override the default settings. For more information, see the [Logback configuration documentation](https://logback.qos.ch/manual/configuration.html).

**Attention:** Enabling FOP debug logging will dramatically increase the size of generated log files.

**Parent topic:** [Error messages and troubleshooting](../topics/troubleshooting-overview.md)

