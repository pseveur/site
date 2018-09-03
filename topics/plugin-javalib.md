# Adding a Java library to the DITA-OT classpath parameter

You can use the `dita.conductor.lib.import` extension point to add an additional Java library to the DITA-OT classpath parameter.

1.   If necessary, compile the Java code into a JAR file. 
2.   Create a plugin.xml file that contains the following code: 

    ```
    <plugin id="plugin-id">
      <feature extension="dita.conductor.lib.import" file="file"/>
    </plugin>
    ```

    where:

    -   plugin-id is the plug-in identifier, for example, com.example.addjar.
    -   file is the name of the JAR file, for example, myJavaLibrary.jar.
3.   Install the plug-in. 

The Ant or XSLT code now can make use of the Java code.

In the following extended example, the myJavaLibrary.jar file performs a validation step during processing, and you want it to run immediately before the `conref`step.

To accomplish this, you will need to use several features:

-   The JAR file must be added to the classpath.
-   The Ant target must be added to the dependency chain for conref.
-   An Ant target must be created that uses this class, and the Ant wrapper integrated into the code.

The files might look like the following:

```
<?xml version="1.0" encoding="UTF-8"?>
<plugin id="com.example.samplejava">
  *<!-- Add the JAR file to the DITA-OT CLASSPATH --\>*
  **<feature extension="dita.conductor.lib.import" 
           file="com.example.sampleValidation.jar"/\>**
  *<!-- Integrate the Ant code --\>*
  <feature extension="dita.conductor.target.relative"
           file="antWrapper.xml"/>
  *<!-- Define the Ant target to call, and when \(before conref\) --\>*
  <feature extension="depend.preprocess.conref.pre" 
           value="validateWithJava"/>
</plugin>
```

```
<?xml version="1.0" encoding="UTF-8"?>
<dummy>
  <import file="calljava-antcode.xml"/>
</dummy>
```

```
<?xml version="1.0" encoding="UTF-8"?>
<project default="validateWithJava">
  <target name="validateWithJava">
    <java classname="com.example.sampleValidation">
      <!-- The class was added to the DITA-OT classpath -->
      <classpath refid="dost.class.path"/>
    </java>
  </target>
</project>
```

**Parent topic:** [Plug-in applications](../topics/plugin-applications.md)

**Related information**  


[General extension points](../extension-points/plugin-extension-points-general.md)

[Installing plug-ins](../topics/plugins-installing.md)

