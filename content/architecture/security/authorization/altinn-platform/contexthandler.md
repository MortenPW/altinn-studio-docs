---
title: Context Handler
description: Description of Context Handler in Altinn Studio Apps 
tags: [architecture, security]
weight: 100
linktitle: Context Handler
alwaysopen: false
---


The responsibility for the Context Handler is to enrich a decision request from a PEP
to PDP.

As an example a decision request could only contain instanceID and userId togheter with the action requested


```xml
<?xml version="1.0" encoding="utf-8"?>
<Request xsi:schemaLocation="urn:oasis:names:tc:xacml:3.0:core:schema:wd-17 http://docs.oasis-open.org/xacml/3.0/xacml-core-v3-schema-wd-17.xsd" ReturnPolicyIdList="false" CombinedDecision="false" xmlns="urn:oasis:names:tc:xacml:3.0:core:schema:wd-17" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Attributes Category="urn:oasis:names:tc:xacml:1.0:subject-category:access-subject">
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:user-id">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">1</AttributeValue>
    </Attribute>
  </Attributes>
  <Attributes Category="urn:oasis:names:tc:xacml:3.0:attribute-category:resource">
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:instance-id">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">cbdc7b44-9442-4fe0-854b-da278bf0b0e</AttributeValue>
    </Attribute>
  </Attributes>
  <Attributes Category="urn:oasis:names:tc:xacml:3.0:attribute-category:action">
    <Attribute IncludeInResult="false" AttributeId="urn:oasis:names:tc:xacml:1.0:action:action-id">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">Read</AttributeValue>
    </Attribute>
  </Attributes>
  <Attributes Category="urn:oasis:names:tc:xacml:3.0:attribute-category:environment" />
</Request>


```

The enriched decision request contains all the needed attributes so PDP can identify the correct policy and evauluate the request based on it.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Request xsi:schemaLocation="urn:oasis:names:tc:xacml:3.0:core:schema:wd-17 http://docs.oasis-open.org/xacml/3.0/xacml-core-v3-schema-wd-17.xsd" ReturnPolicyIdList="false" CombinedDecision="false" xmlns="urn:oasis:names:tc:xacml:3.0:core:schema:wd-17" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <Attributes Category="urn:oasis:names:tc:xacml:1.0:subject-category:access-subject">
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:user-id">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#integer">1</AttributeValue>
    </Attribute>
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:rolecode">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">DAGL</AttributeValue>
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">REGNA</AttributeValue>
    </Attribute>
  </Attributes>
  <Attributes Category="urn:oasis:names:tc:xacml:3.0:attribute-category:resource">
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:instance-id">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">cbdc7b44-9442-4fe0-854b-da278bf0b0e</AttributeValue>
    </Attribute>
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:org">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">SKD</AttributeValue>
    </Attribute>
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:app">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">TaxReport</AttributeValue>
    </Attribute>
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:task">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">FormFilling</AttributeValue>
    </Attribute>
    <Attribute IncludeInResult="false" AttributeId="urn:altinn:partyid">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#integer">123456</AttributeValue>
    </Attribute>
  </Attributes>
  <Attributes Category="urn:oasis:names:tc:xacml:3.0:attribute-category:action">
    <Attribute IncludeInResult="false" AttributeId="urn:oasis:names:tc:xacml:1.0:action:action-id">
      <AttributeValue DataType="http://www.w3.org/2001/XMLSchema#string">Read</AttributeValue>
    </Attribute>
  </Attributes>
  <Attributes Category="urn:oasis:names:tc:xacml:3.0:attribute-category:environment" />
</Request>

```

















