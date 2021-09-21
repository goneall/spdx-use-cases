# Use Case Title: Flatten Micro SBOM’s

## Definitions
* Micro-SBOM - A small SBOM which describes a narrow scope of files, packages by creating references to external SBOMs whenever feasible
* Top level Micro-SBOM - A Micro-SBOM representing a large distribution of software referencing other Micro-SBOMs to describe the content
* Flattened SBOM - An SPDX document representing a large distribution with no external document references - all data for all elements are contained within the Flattened SBOM

## Actors
* Micro SBOM Producer (MS Producer) – Tools, organizations, and people who produce Micro SBOMs
* Flattened SBOM Producer (FS Producer) - Tools, organizations, and people who produce Flattened SBOMs
* Flattened SBOM Consumer (FS Consumer) - Tools, organizations, and people who consume Flattened SBOMs
* Auditor - Tools, organizations and people to validate the information contained in the SBOM's

## Goals
* MS Producers provide reliable, verifiable SBOM information for a complete distribution using a set of Micro SBOMs
* FS Producer provides the FS Consumer a Flattened SBOM containing all of the information present in a set of Micro SBOMs
* FS Consumer can validate the contents of the flattened SBOMs
* Auditor and FS Producer can validate Flattened SBOM accurately represents SBOM data in the Micro SBOMs

## Preconditions
* Software is available for MS Producer to produce all Micro SBOMs
* Micro SBOMs are available to FS Producer
* Micro SBOMs, Flattened SBOM, and software is available for Auditor to audit
* NOTE: The FS Consumer is assumed to only need access to the distribution and SBOM

## Steps
1. MS Producer produces a set of Micro SBOM representing tightly scoped artificats
2. MS Producer produces a Top Level Micro-SBOM for a distribution referencing all included software components using External Document References
3. FS Producer takes the Top Level Micro-SBOM as the primary input and "copies" all of the information from the top-level Micro-SBOM and all referenced Micro-SBOMs into a single SBOM
4. FS Producer adds sufficient information to allow for verification when comparing the Flattend SBOM to the distribution artifacts
5. FS Producer adds sufficient information for Auditor to confirm the Flattened SBOM was created successfully (e.g. relationships)
6. FS Consumer recieves the Flattened SBOM from the FS Producer
7. FS Consumer uses the information local to the Flattened SBOM to verify software receieved
8. Auditor uses information from the Flattend SBOM, Micro SBOMs and software to validate the Flattened SBOM

## Notes
* The FS Consumer and Auditor could be the same tool, person, and/or organization
