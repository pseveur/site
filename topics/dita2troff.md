# troff

The troff transformation produces output for use with the troff viewer on Unix-style platforms, particularly for programs such as the man page viewer.

Each DITA topic generally produces one troff output file. The troff transformation supports most common DITA structures, but it does not support `table` or `simpletable` elements. Most testing of troff output was performed using the Cygwin Linux emulator.

To run the troff transformation, set the transtype parameter to troff, or pass the --format=troff option to the dita command line.

```
dita-ot-dir/bin/dita --input=input-file --format=troff
```

where:

-   dita-ot-dir is the DITA-OT installation directory.
-   input-file is the DITA map or DITA file that you want to process.

**Parent topic:** [DITA-OT transformations \(output formats\)](../topics/output-formats.md)

**Related information**  


[Common parameters](../parameters/parameters-base.md)

