# XMLP
A Lightweight SingleFile XML Components in Java port.

# Getting start

Create a XML element From existed XML String.
```java
XML nd1 = new XML("<ele1 attr1='attrValue1'><a></a><b>Some of Texts</b></ele1>");
System.out.println(nd1.toString(0));
System.out.println(nd1.toString());  // default indentFactor: 4.
```
Output:
```
<ele1 attr1="attrValue1"><a/><b>Some of Texts</b></ele1>
<ele1 attr1="attrValue1">
    <a/>
    <b>Some of Texts</b>
</ele1>
```

## Supports

### CDATA

### <!--- Comments -->

### <? Processing Instructions ?>
