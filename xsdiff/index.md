---
layout: xsdiff
title: XsDiff XSD Diff Tools
is_project_page: true
---

# What is it

Do you need to compare 2 large XSD schemas (like ACORD schemas in insurance industry for example).

Or, possibly your schemas include other schemas, distributed over multiple files, which maybe were auto-generated via JAXB directly from Java classes, and therefore they might be subtly different, but possibly equivalent?
(You need to ignore different element order, positioning, attribute order - which all but mean the same thing?)

The usual text-based comparison tools fall down, because they show spurious changes which actually have no impact on schema semantics.

You need to compare XSD schemas structurally, and see if they are equivalent (i.e., no meaningful changes), or if they indeed have changed, which will impact you.

# How to run

To compare one XSD file against another file, run:
~~~~
java -jar XsDiff-app/target/xsdiff-app-{{ site.data.xsdiff.version}}.jar a.xsd b.xsd
~~~~
`report-yyyy-MM-dd` folder will be created to hold the generated html report file.


To compare control schemas in a/ folder vs new schemas in b/ folder, run:

~~~~
java -jar XsDiff-app/target/xsdiff-app-{{ site.data.xsdiff.version}}.jar a/ b/
~~~~

You need to have schema.lst file in b/ folder, that lists the files to compare.

Like this (shema.lst contents):
~~~~
f1.xsd
f2.xsd
~~~~

`report-yyyy-MM-dd` folder will be created to hold the generated html report files.
