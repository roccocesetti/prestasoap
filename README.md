Simple Prestashop SOAP v.0.2.1a


**INSTALLATION**

First, unzip the zip file to your hard disk and then upload the entire contents to your web server in core directory of your Prestashop.
That's all.

**DOCUMENTATION**

Coming soon...

**EXAMPLE**

Call method Category::getCategories($id\_lang, $active = true, $order = true)

```
<?xml version="1.0" encoding="ISO-8859-1"?>
<SOAP-ENV:Envelope SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/">
    <SOAP-ENV:Body>
        <ns8869:core xmlns:ns8869="http://tempuri.org">
            <login xsi:type="xsd:string">login@email.com</login>
            <password xsi:type="xsd:string">password</password>
            <class xsi:type="xsd:string">Category</class>
            <method xsi:type="xsd:string">getCategories</method>
            <params xsi:type="xsd:string">a:1:{i:0;i:3;}</params>
        </ns8869:core>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


NuSOAP example:
```
$result = $client->call(
    'core',                     // method name
    array(  'login' => 'login@email.com',
            'password' => 'assword',
            'class' => 'Category', 
            'method' => 'getCategories', 
            'params' =>serialize( array(3) ) 
    )   
);
```

Response:
```

<?xml version="1.0" encoding="ISO-8859-1"?>
<SOAP-ENV:Envelope SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/"
  xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/">
    <SOAP-ENV:Body>
        <SOAP-ENV:Fault>
            <faultcode>
                <status xsi:type="xsd:int">1</status>
                <result xsi:type="SOAP-ENC:Array" SOAP-ENC:arrayType="SOAP-ENC:Array[2]">
                    <item xsi:type="SOAP-ENC:Array" SOAP-ENC:arrayType="unnamed_struct_use_soapval[113]">
                        <item>
                            <infos>
                                <id_category xsi:type="xsd:string">97</id_category>
                                <id_parent xsi:type="xsd:string">1</id_parent>
                                <level_depth xsi:type="xsd:string">1</level_depth>
                                <active xsi:type="xsd:string">1</active>
                                <date_add xsi:type="xsd:string">2010-07-17 17:29:49</date_add>
                                <date_upd xsi:type="xsd:string">2010-07-17 17:29:49</date_upd>
                                <id_lang xsi:type="xsd:string">3</id_lang>
                                <name xsi:type="xsd:string"> BD</name>
                                <description xsi:type="xsd:string"></description>
                                <link_rewrite xsi:type="xsd:string"></link_rewrite>
                                <meta_title xsi:type="xsd:string"></meta_title>
                                <meta_keywords xsi:type="xsd:string"></meta_keywords>
                                <meta_description xsi:type="xsd:string"></meta_description>
                            </infos>
                        </item>
                        <item>
                            <infos>
                                <id_category xsi:type="xsd:string">107</id_category>
                                <id_parent xsi:type="xsd:string">1</id_parent>
                                <level_depth xsi:type="xsd:string">1</level_depth>
                                <active xsi:type="xsd:string">1</active>
                                <date_add xsi:type="xsd:string">2010-07-17 17:29:57</date_add>
                                <date_upd xsi:type="xsd:string">2010-07-17 17:29:57</date_upd>
                                <id_lang xsi:type="xsd:string">3</id_lang>
                                <name xsi:type="xsd:string"> CD-ROM</name>
                                <description xsi:type="xsd:string"></description>
                                <link_rewrite xsi:type="xsd:string"></link_rewrite>
                                <meta_title xsi:type="xsd:string"></meta_title>
                                <meta_keywords xsi:type="xsd:string"></meta_keywords>
                                <meta_description xsi:type="xsd:string"></meta_description>
                            </infos>
                        </item>
                    <item xsi:type="SOAP-ENC:Array" SOAP-ENC:arrayType="unnamed_struct_use_soapval[1]">
                        <item>
                            <infos>
                                <id_category xsi:type="xsd:string">1</id_category>
                                <id_parent xsi:type="xsd:string">0</id_parent>
                                <level_depth xsi:type="xsd:string">0</level_depth>
                                <active xsi:type="xsd:string">1</active>
                                <date_add xsi:type="xsd:string">2010-05-29 12:41:24</date_add>
                                <date_upd xsi:type="xsd:string">2010-05-29 12:41:24</date_upd>
                                <id_lang xsi:type="xsd:string">3</id_lang>
                                <name xsi:type="xsd:string">Home</name>
                                <description xsi:type="xsd:string"></description>
                                <link_rewrite xsi:type="xsd:string">home</link_rewrite>
                                <meta_title xsi:nil="true"/>
                                <meta_keywords xsi:nil="true"/>
                                <meta_description xsi:nil="true"/>
                            </infos>
                        </item>
                    </item>
                </result>
            </faultcode>
            <faultactor xsi:type="xsd:string"></faultactor>
            <faultstring xsi:type="xsd:string"></faultstring>
            <detail xsi:type="xsd:string"></detail>
        </SOAP-ENV:Fault>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>

```