# Resolve key references \(keyref\)

The `keyref` step examines all the keys that are defined in the DITA source and resolves the key references. Links that make use of keys are updated so that any `@href`value is replaced by the appropriate target; key-based text replacement is also performed, and the key definition list file is written to the temporary directory. This step is implemented in Java.

**Parent topic:** [Pre-processing modules](../reference/preprocessing.md)

**Previous topic:** [Copy related files \(copy-files\)](../reference/preprocess-copyfiles.md)

**Next topic:** [Copy topics \(copy-to\)](../reference/preprocess-copy-to.md)

