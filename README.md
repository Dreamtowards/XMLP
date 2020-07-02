# XMLP
A Lightweight SingleFile XML Components in Java port.

# Getting start

### Create a XML element From existed XML String.
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
### Create a XML element From a InputStream. (can from ByteArray, Network, File, even Zip_Entry lmao)(String content)
testxml.xml File:
```xml
<?xml version="1.0" encoding="utf-8"?>
<?txt some texts?>
<!-- cmts -->

<RootEle attr1key="value1" attr2k="v2" xmlns:tstNs="http://tstns.example.com">

    <emptybodyele1></emptybodyele1>
    <emptybodyele2/>
    <emptybodyHadAttrEle1WithEscpAttrValue tstNs:attr1="valueWithEscp<>&apos;&quot;&amp;"/>

    <elep>
        <!-- cmts -->
        <jusTxtBodyEle>Some of Text</jusTxtBodyEle>
        <jusTxtBodyEle2WithMulLine>
            Some of Text2
            And MulLine
        </jusTxtBodyEle2WithMulLine>
        <CDATABodyTest>
            <![CDATA[
Some Text <>&'" In CDATA -only for input.
]]>
        </CDATABodyTest>
        <!-- cmts2 -->
    </elep>

</RootEle>
```
```java
```

## Supports

### CDATA

### <!--- Comments -->

### <? Processing Instructions ?>
