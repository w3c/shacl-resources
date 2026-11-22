# SHACL Community Null Profile of POS

## Metadata

* **IRI**:
  * `https://w3id.org/profile/pos-null`
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
  * A null profile of the Basic Geo (WGS84 lat/long) Vocabulary also known as POS.

## Introduction

This is a [null profile](https://www.w3.org/TR/dx-prof-1.0/#null-profiles) of the 
[Basic Geo (WGS84 lat/long) Vocabulary](https://www.w3.org/2003/01/geo/) also known as POS.

This null profile was created for the publication of the [SHACL 1.2 Profiling](https://www.w3.org/TR/shacl12-profiling/)
specification and was included as an example of a simple null profile for a simple vocabulary. Its maintenance here is
mostly for null profile demonstration purposes, rather than for expected use.

For a null profile expected to be used widely, see the [SHACL Community Null Profile of SKOS](https://w3id.org/profile/skos-null). 

## Resources

This null profiles provides a [_validation_](https://www.w3.org/TR/dx-prof-1.0/#Role:validation) resource in the form of
a [SHACL Shapes Graph]() in addition to the existing [_specification_](https://www.w3.org/TR/dx-prof-1.0/#Role:specification)
and [_schema_](https://www.w3.org/TR/dx-prof-1.0/#Role:schema) resources provided by POS itself. 

This README file is a [_guidance_](https://www.w3.org/TR/dx-prof-1.0/#Role:guidance) for the null profile too.

The complete set of POS null profile resources are:

| **Resource** | **Role** | **Location** |
| --- | --- | --- |
| this README file | [guidance](https://www.w3.org/TR/dx-prof-1.0/#Role:guidance)<br />for use of this null profile| this file|
| Shapes Graph | [validation](https://www.w3.org/TR/dx-prof-1.0/#Role:validation) | ./validator.ttl|
| SKOS Reference web page | [specification](https://www.w3.org/TR/dx-prof-1.0/#Role:specification) | <https://www.w3.org/TR/skos-reference/> |
| SKOS Primer web page | [guidance](https://www.w3.org/TR/dx-prof-1.0/#Role:guidance)<br />for the general use of SKOS| <https://www.w3.org/TR/skos-primer/> |
| SKOS RDF vocabulary | [schema](https://www.w3.org/TR/dx-prof-1.0/#Role:schema) | <https://www.w3.org/2009/08/skos-reference/skos.rdf> |

## Requirements coverage

The authors of this null profile believe tests in its validation resource provide reasonable coverage of 
structural requirements in the specification but community input is needed to aim for close to complete coverage.

This is because, while many of SKOS' rules are easy to test for with SHACL shapes, 15+ years of SKOS' use by the 
community has lead to a deep understanding of corner cases which the initial direct translation of the SKOS vocabulary
and specification into validation shapes will likely have missed.
