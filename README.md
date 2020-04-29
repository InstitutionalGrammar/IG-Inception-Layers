# IG Inception Layers

Institutional Grammar Layers for Inception Annotation Platform

## Content

This repository contains [Inception](https://inception-project.github.io/) Annotation Layers for the IG Core specification, alongside additional features.

The annotation layers are provided as json files that have to be imported into Inception projects. Layer files that represent relationships amongst layer annotations include the associated layer in addition to the annotation layer. Selected layer files thus expand into multiple layers when imported into Inception. 

The layer files included in this release are the following (where containing multiple layers, those are listed explicitly):
 * IG Check Indication - this layer allows the flagging of annotations in preparation for coding or analysis discussions
 * IG Collection Relationship - this layer allows the representation of collection constructs by annotation. This file contains the following layers:
   * IG Collection (containing collection elements and characterization by type)
   * IG Collection Relationship (containing logical relationships amongst elements)
 * IG Core Component Relationship - this layer contains the IG Core component specifications, alongside additional Context taxonomies. This file contains the following layers:
   * IG Core (containing syntactic component annotations of the institutional grammar, along with context type taxonomy)
   * IG Core Component Relationship (containing logical relationship annotations amongst institutional grammar components)
 * IG Institutional Statement Relationship - this layer facilitates the representation of relationships amongst institutional statements. This file contains the following layers:
   * IG Institutional Statement (containing institutional statement types and characterization by rule type, statement nature, etc.)
   * IG Institutional Statement Relationships (containing logical relationship annotations amongst institutional statements)
 * IG Policy Resource Reference Relationship - this layer facilitates the representation of references to policy resource as well as their relationships. This file contains the following layers:
   * IG Policy Resource Reference (containing annotation of reference to policy resource)
   * IG Policy Resource Reference Relationship (containing annotation of logical relationships amongst references to policy resources)
 * IG Policy Resource - this layer facilitates the annotation of policy resources

In addition to layers, the package contains constraints for the UI configuration:
 * IGCoreConstraints.txt - Context-dependent UI layout for Context components and properties

## Contact

Christopher Frantz (cf@christopherfrantz.org)

## Version History
 
 * IG-Inception v0.1 (29/04/2020, C. Frantz) - Initial release
