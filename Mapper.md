# Steps To Trigger the Map.

### Map Trigger


Mapper

--->Validate
--->Generate
--->Publish

--->Active agruments

--->CRS945 + Media Setup

--->MNS 260 Setup

--->Create Event analytics Rules

--->Add company & Division to BOD Processor

---> Finally - Trigger the map(MNS260)


# The Inbound File Demo

``` xsd
<?xml version="1.0" encoding="UTF-16" ?>
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:jxb="http://java.sun.com/xml/ns/jaxb" jxb:version="2.0">
	<xs:element name="EventData" type="EventDataType"/>
	<xs:complexType name="EventDataType">
		<xs:sequence>
			<xs:element ref="TenantId"/>
			<xs:element ref="Publisher"/>
			<xs:element ref="DocumentName"/>
			<xs:element ref="Operation"/>
			<xs:element ref="TrackingId"/>
			<xs:element ref="EventId"/>
			<xs:element ref="SentTimestamp"/>
			<xs:element name="Document" type="DocumentType"/>
		</xs:sequence>
	</xs:complexType>
	<xs:complexType name="DocumentType">
		<xs:sequence>
			<xs:element name="ElementData" type="ElementDataType" minOccurs="0" maxOccurs="unbounded"/>
		</xs:sequence>
	</xs:complexType>
	<xs:complexType name="ElementDataType">
		<xs:sequence>
			<xs:element ref="Name"/>
			<xs:element ref="Value" minOccurs="0"/>
			<xs:element ref="OldValue" minOccurs="0"/>
		</xs:sequence>
	</xs:complexType>
	<xs:element name="TenantId" type="xs:string"/>
	<xs:element name="Publisher" type="xs:string"/>
	<xs:element name="DocumentName" type="xs:string"/>
	<xs:element name="Operation" type="xs:string"/>
	<xs:element name="TrackingId" type="UUID"/>
	<xs:element name="EventId" type="UUID"/>
	<xs:element name="SentTimestamp" type="xs:dateTime"/>
	<xs:element name="Name" type="xs:string"/>
	<xs:element name="Value" type="xs:string"/>
	<xs:element name="OldValue" type="xs:string"/>
	<xs:simpleType name="UUID">
		<xs:restriction base="xs:string">
			<xs:pattern value="[a-f0-9]{8}-[a-f0-9]{4}-[a-f0-9]{4}-[a-f0-9]{4}-[a-f0-9]{12}"/>
		</xs:restriction>
	</xs:simpleType>
</xs:schema>
```
