# SHACL Community Null Profile of SKOS

## Metadata

* **IRI**:
  * `https://w3id.org/profile/skos-null`
* **Date Created**:
  * 2026-11-01
* **Date Modified**:
  * 2026-11-22
* **Version**:
  * 1
* **Creator**:
  * [Nicholas J. Car](https://orcid.org/0000-0002-8742-7730)
* **Publisher**:
  * [W3C SHACL Community Group](https://www.w3.org/groups/cg/shacl/)
* **Code Repository**:
  * <https://github.com/w3c/shacl-resources>
* **Description**
  * A null profile of the Simple Knowledge Organization System (SKOS) data model.

## Introduction

This is a [null profile](https://www.w3.org/TR/dx-prof-1.0/#null-profiles) of the widely-used 
[Simple Knowledge Organization System (SKOS)](https://www.w3.org/TR/skos-reference/) data model.

SKOS is one of the most commonly encountered RDF data models but at publication in 2009 it did not contain an official 
data validation resource.

Many 3rd party data validation and quality checking application for SKOS have been made, such as 
[qSKOS](https://www.w3.org/2001/sw/wiki/QSKOS) and [Skosify](https://github.com/NatLibFi/Skosify) and even many 
SHACL-based validators such as [VocPub](https://linked.data.gov.au/def/vocpub).

This null profile is a W3C community attempt to create and maintain a close-to canonical validator for SKOS.

## Resources

This null profiles provides a [_validation_](https://www.w3.org/TR/dx-prof-1.0/#Role:validation) resource in the form of
a [SHACL Shapes Graph]() in addition to the existing [_specification_](https://www.w3.org/TR/dx-prof-1.0/#Role:specification)
and [_schema_](https://www.w3.org/TR/dx-prof-1.0/#Role:schema) resources provided by POS itself. 

This README file is a [_guidance_](https://www.w3.org/TR/dx-prof-1.0/#Role:guidance) for the null profile too.

The complete set of POS null profile resources are:

| **Resource** | **Role** | **Location** |
| --- | --- | --- |
| this README file | [guidance](https://www.w3.org/TR/dx-prof-1.0/#Role:guidance) | this file|
| Shapes Graph | [validation](https://www.w3.org/TR/dx-prof-1.0/#Role:validation) | ./validator.ttl|
| POS web page | [specification](https://www.w3.org/TR/dx-prof-1.0/#Role:specification) | <https://www.w3.org/2003/01/geo/> |
| POS RDF vocabulary | [schema](https://www.w3.org/TR/dx-prof-1.0/#Role:schema) | <https://www.w3.org/2003/01/geo/wgs84_pos#><br />_with content negotiation for RDF_ |

## Requirements coverage

The authors of this null profile believe tests in its validation resource provide close to complete coverage of 
structural requirements in the specification.

This null profile's validator was partly auto-generated from POS' ontology constraints - RDFS domain, range & subclass 
axioms - and then manually edited to cater for description / usage note constraints within the vocabulary such as the
description for `pos:alt`: "The WGS84 altitude of a SpatialThing (decimal meters above the local reference ellipsoid)". 
In this case, we created a shape that tests that a value for `pos:alt` is a decimal. We cannot require it to be positive 
as a negative height can be sensibly interpreted as a depth. 
