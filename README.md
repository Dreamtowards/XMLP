## Copyrights Declarations
This is produced From OTS/UtilS Lib. as a Open, Semi-Independent Term.

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
### Create a XML element From a InputStream. (String content)
File testxml.xml:
```xml
<?xml version="1.0" encoding="utf-8"?>
<?txt some texts?>
<!-- commts -->

<RootEle xmlns:tstNs="http://tstns.example.com" attr1key="value1" attr2k="v2" >

    <emptybodyele1></emptybodyele1>
    <emptybodyele2/>
    <emptybodyHadAttrEle1WithEscpAttrValue tstNs:attr1="valueWithEscp<>&apos;&quot;&amp;"/>

    <elep>
        <!-- commts1 -->
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
        <!-- commts2 -->
    </elep>

</RootEle>
```
```java
  XML tn2 = new XML(new FileInputStream("testxml.xml"));
  System.out.println(tn2.toString(2));

  System.out.println("attrs: "+tn2.getChildren().get(2).getAttributes());
```
Output:
```
<RootEle attr2k="v2" attr1key="value1" xmlns:tstNs="http://tstns.example.com">
  <emptybodyele1/>
  <emptybodyele2/>
  <emptybodyHadAttrEle1WithEscpAttrValue tstNs:attr1="valueWithEscp&lt;&gt;&apos;&quot;&amp;"/>
  <elep>
    <jusTxtBodyEle>Some of Text</jusTxtBodyEle>
    <jusTxtBodyEle2WithMulLine>Some of Text2
            And MulLine</jusTxtBodyEle2WithMulLine>
    <CDATABodyTest>
Some Text &lt;&gt;&amp;&apos;&quot; In CDATA -only for input.
</CDATABodyTest>
  </elep>
</RootEle>
attrs: {tstNs:attr1=valueWithEscp<>'"&}
```

## Supports

## Who Uses OTS/UtilS XMLP.?

- DaeLoader

