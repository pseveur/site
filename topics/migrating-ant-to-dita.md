# Migrating Ant builds to use the dita command

Although Ant builds are still supported in the DITA Open Toolkit, you might want to switch to use the new dita command.

Building output with the dita command is often easier than using Ant. In particular, you can use .properties files to specify sets of DITA-OT parameters for each build.

You can include the dita command in shell scripts to perform multiple builds.

**Tip:** Add the absolute path for dita-ot-dir/bin to the PATH environment variable to run the dita command from any location on the file system without typing the path.

1.   In your Ant build file, identify the properties set in each build target. 

    **Note:** Some build parameters might be specified as properties of the project as a whole. You can refer to a build log to see a list of all properties that were set for the build.

2.   Create a .properties file for each build and specify the needed build parameters, one per line, in the format `name = value`. 
3.   Use the dita command to perform each build, referencing your .properties with the --propertyfile=file option. 

## Example: Ant build

Sample build file: dita-ot-dir/docsrc/samples/ant\_sample/build-chm-pdf.xml 

```
<?xml version="1.0" encoding="UTF-8" ?>
<project name="build-chm-pdf" default="all" basedir=".">
  <property name="dita.dir" location="${basedir}/../../.."/>
  <target name="all" description="build CHM and PDF" depends="chm,pdf"/>
  <target name="chm" description="build CHM">
    <ant antfile="${dita.dir}/build.xml">
      <property name="args.input" location="../sequence.ditamap"/>
      <property name="transtype" value="htmlhelp"/>
      <property name="output.dir" location="../out/chm"/>
      <property name="args.gen.task.lbl" value="YES"/>
    </ant>
  </target>
  <target name="pdf" description="build PDF">
    <ant antfile="${dita.dir}/build.xml">
      <property name="args.input" location="../taskbook.ditamap"/>
      <property name="transtype" value="pdf"/>
      <property name="output.dir" location="../out/pdf"/>
      <property name="args.gen.task.lbl" value="YES"/>
      <property name="args.rellinks" value="nofamily"/>
    </ant>
  </target>
</project>
```

## Example: .properties files with dita command

The following .properties files and dita commands are equivalent to the example Ant build.

Sample .properties file: dita-ot-dir/docsrc/samples/properties/chm.properties

```
output.dir = out/chm
args.gen.task.lbl = YES
args.breadcrumbs = yes
```

Sample .properties file: dita-ot-dir/docsrc/samples/properties/pdf.properties

```
output.dir = out/pdf
args.gen.task.lbl = YES
args.rellinks = nofamily
```

Run from dita-ot-dir/docsrc/samples:

```
dita --input=sequence.ditamap --format=htmlhelp \
     --propertyfile=properties/chm.properties
dita --input=taskbook.ditamap --format=pdf \
     --propertyfile=properties/pdf.properties
```

## Example: Call the dita command from an Ant build

In some cases, you might still want to use an Ant build to implement some pre- or post-processing steps, but also want the convenience of using the dita command with .properties files to define the parameters for each build. This can be accomplished with Ant's `exec` task.

This example uses a `dita-cmd` Ant macro defined in the dita-ot-dir/docsrc/samples/ant\_sample/dita-cmd.xml file:

```
<macrodef name="dita-cmd">
  <attribute name="input"/>
  <attribute name="format"/>
  <attribute name="propertyfile"/>
  <sequential>
    <exec executable="${dita.dir}/bin/dita">
      <arg line="--input=@{input} --format=@{format} --propertyfile=@{propertyfile}"/>
    </exec>
  </sequential>
</macrodef>
```

You can use this macro in your Ant build to call the dita command and pass the input, format and propertyfile parameters as follows:

```
<dita-cmd input="sample.ditamap" format="pdf" propertyfile="sample.properties"/>
```

This approach allows you to use Ant builds to perform additional tasks at build time while allowing the dita command to set the classpath and ensure that all necessary JAR libraries are available.

**Note:** The attributes defined in the Ant macro are required and must be supplied each time the task is run. To set optional parameters in one build \(but not another\), use different .properties files for each build.

Sample build file: dita-ot-dir/docsrc/samples/ant\_sample/build-chm-pdf-hybrid.xml

```
<?xml version="1.0" encoding="UTF-8" ?>
<project name="build-chm-pdf-hybrid" default="all" basedir=".">
  <description>An Ant build that calls the dita command</description>
  <include file="dita-cmd.xml"/><!-- defines the <dita-cmd> macro -->
  <target name="all" depends="pre,main,post"/>
  <target name="pre">
    <description>Preprocessing steps</description>
  </target>
  <target name="main">
    <description>Build the CHM and PDF with the dita command</description>
    <dita-cmd input="../sequence.ditamap" format="htmlhelp"
              propertyfile="../properties/chm.properties"/>
    <dita-cmd input="../taskbook.ditamap" format="pdf"
              propertyfile="../properties/pdf.properties"/>
  </target>
  <target name="post">
    <description>Postprocessing steps</description>
  </target>
</project>
```

**Parent topic:** [Building output using the dita command](../topics/build-using-dita-command.md)

