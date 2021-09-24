# Use Case Title: Distribute SBOMs with Confidential Components

## Definitions
* Micro-SBOM - A small SBOM which describes one component or narrow scope of files or packages
* Top level SBOM - An SBOM representing a large distribution of software. The top level SBOM can be thought of as a "sum of parts" and references other Micro-SBOMs to describe the content of the whole
* Flattened SBOM - A Top level SBOM where the references to Micro-SBOMs are removed and instead replaced with the actual component level Micro-SBOM content. This is what we tend to think of today when we think of SBOMs.
* Enterprise Software - Propietary software created using a mix of in-house and open source software

## Actors
* Micro SBOM Producer (MS Producer) – Tools, organizations, and people who produce Micro SBOMs
* Enterprise SBOM producer (ES Producer) - An enterprise organization or company who needs to share SBOM information with their software consumers 
* Enterprise Consumer - An organization, individual or company who consumes Enterprise software and, therefore, has need to obtain an SBOM that describing the Enterprise software


## Goals
* MS Producers provide reliable, verifiable SBOM information in the form of a Micro-SBOM that can be utilized by ES Prodcuers.
* Enterprise consumers receive an SBOM describing relevant components of the Enterprise software they are consuming (i.e. relevant open source license/source/copyright infomation)
* ES Producer does not share SBOM information which may describe confidential components but can share relevant/required open source SBOM information in order to comply with all open source license obligations.

## Preconditions
* Software is available for MS Producer to produce all Micro-SBOMs
* Enterprise SBOM producer is able to collect Micro-SBOMs for any and all Enterprise Software components

## Steps
1. ES Producer creates a Top level SBOM for their Enterprise Software by collecting the Micro-SBOMs for components and referencing them in to a Top level SBOM.
2. ES Producer sets access control for the various Micro-SBOM documents referenced in the Top level SBOM.
3. Enterprise consumer can access Top level SBOM as well as the relevant open source Micro-SBOMs for which they are given access by the ES Producer. Propietary component Micro-SBOMs are not accessible by Enterprise consumers and, thus, ES Producer does not comprimise confidentiality or IP of non-open source components.

## Notes
* The typical SBOM that ES producers create and distribute currently are Flattened SBOMs. Flattened SBOMs are not able to provide access control for certain components as all of the information is in the same document. Micro-SBOMs can help address this confidentiality, IP and security concern by making it easier to distribute only certains parts of an SBOM while obfuscating the rest.
