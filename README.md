# IG Inception Layers

Institutional Grammar Layers for Inception Annotation Platform

**Note: This project is under development and currently undergoing evaluation.**

## Content

This repository contains [Inception](https://inception-project.github.io/) Annotation Layers for the IG Core specification of the [Institutional Grammar](https://arxiv.org/abs/2008.08937), alongside selected additional features. 

This Readme file provides 
* instructions for download and import of the layers into Inception, 
* a high-level overview of the layers provided as part of this repository,
* a workaround for multi-line annotations in Inception, and
* the changelog for all versions of the IG Inception layers.

### Download 

Please refer to the [Releases](../../releases) page to download any of the IG-Inception layers releases. All releases will be retained so as to maintain long-term compability with and accessibility of encoded datasets. Ensure that you document the specific release used during encoding alongside your dataset.

### Overview

The annotation layers are provided as json files that have to be imported into Inception projects. Layer files that represent relationships amongst layer annotations include the associated layer in addition to the annotation layer. Selected layer files thus expand into multiple layers when imported into Inception as introduced in the following. The import process is described in the following [video](https://youtu.be/wnXzSNxmLec).

The layer files included in this release are the following (where containing multiple layers, those are listed explicitly):
 * *IG Coding Review Indication* - this layer allows the flagging of annotations in preparation for coding or analysis discussions
 * IG Collection Relationship - this layer allows the representation of collection constructs by annotation. This file contains the following layers:
   * *IG Collection* (containing collection elements and characterization by type)
   * *IG Collection Relationship* (containing logical relationships amongst elements)
 * IG Complex Data Structure Relationship - this layer provides a schema for the decomposition of complex data structures.
 * IG Core Constitutive Component Relationship - this layer contains the IG Core constitutive component specifications, alongside additional Context taxonomies. This file contains the following layers:
   * *IG Core Constitutive Syntax* (containing syntactic component annotations for constitutive institutional statements, along with relevant taxonomies)
   * *IG Core Constitutive Component Relationship* (containing logical relationship annotations amongst institutional grammar components)
 * IG Core Regulative Component Relationship - this layer contains the IG Core regulative component specifications, alongside additional Context taxonomies. This file contains the following layers:
   * *IG Core Regulative Syntax* (containing syntactic component annotations for regulative institutional statements, along with context type taxonomy and further relevant taxonomies)
   * *IG Core Regulative Component Relationship* (containing logical relationship annotations amongst institutional grammar components)
 * IG Institutional Statement Relationship - this layer facilitates the representation of relationships amongst institutional statements. This file contains the following layers:
   * *IG Institutional Statement* (containing institutional statement types and characterization by rule type, statement nature, etc.)
   * *IG Institutional Statement Relationship* (containing logical relationship annotations amongst institutional statements)
 * IG Policy Resource Reference Relationship - this layer facilitates the representation of references to policy resource as well as their relationships. This file contains the following layers:
   * *IG Policy Resource Reference* (containing annotation of reference to policy resource)
   * *IG Policy Resource Reference Relationship* (containing annotation of logical relationships amongst references to policy resources)
 * *IG Policy Resource* - this layer facilitates the annotation of policy resources

In addition to layers, the package contains constraints for the UI configuration and Coding Guidelines:
 * *IGCoreConstraints.txt* - Context-dependent UI layout for Context components and properties of constitutive and regulative statements
 * *IGLayersCodingGuidelines.txt* - Coding guidelines for the general Institutional Grammar annotation in Inception
 
## Document Preparation Workaround (Multi-line annotations in Inception)

A specific challenge of Inception-based coding is the expansion of multi-line annotations. Whenever the coder annotates a statement across line boundaries, the annotated text is expanded onto a single line, requiring extensive horizontal scrolling in the coding process. This problem is specific to Inception and not related to the provided layers. A workaround to alleviate this is to preprocess documents with fixed line boundaries and adjust the editor settings accordingly.

The following workaround addresses this by introducing a forced line break after 100 characters (this can be adjusted by substituting the corresponding value in the 'Find what:' field described below). Note that this can lead to arbitrary word separation, which may require further post-processing.

Preparation:
* Ensure the document is available in plain text format 
* Create a backup copy of the original document prior to performing the following steps

Instructions for reformatting:
* Open document in Notepad++
* Press *Ctrl-A* to mark the complete text
* Open the Search dialog (*Ctrl-F*) and switch to the 'Replace' tab
* In the 'Search Mode' area at the bottom of the 'Replace' tab, select 'Regular Expression'
* In the 'Find what:' field, enter: *\s(?<=.{100})*
* In the 'Replace with:' field, enter: *\n*
* Click 'Replace All' button
* Save the reformatted document

Adjust annotation editor setting:
* Import the reformatted document in the Inception project
* Open annotation editor
* Open editor settings (cogwheel button)
* Switch to 'brat (line-oriented)'
* Click 'Save' button

Now multi-line coding should operate without horizonal expansion.

As mentioned above, this is a workaround established based on Inception coding experience and does not imply recommendation for general use. If applied in production settings, further refinement (e.g., word alignment along line breaks) is recommended to ensure high-quality annotations.

## Contact

Christopher Frantz (christopher.frantz@ntnu.no)

## Version History
 
 * IG-Inception v0.2.8 (in preparation)
   * Fixed Statement level characterization (Collective Choice Level)
 * IG-Inception v0.2.7 (02/11/2020, C. Frantz)
   * Updated Context Taxonomy with Event category
   * Comprehensive review of Context Taxonomy category descriptions
 * IG-Inception v0.2.6 (09/10/2020, C. Frantz)
   * Updated and renamed context taxonomy in line with Codebook revisions
   * Added Inception workaround description
 * IG-Inception v0.2.5 (08/10/2020, C. Frantz)
   * Added novel circumstance category (Cause/Reason)
   * Extended constitutive functions taxonomy in line with Codebook
   * Renamed and clarified logical relationship characterization for institutional statements and components
   * Updated guidelines accordingly
 * IG-Inception v0.2.4 (22/09/2020, C. Frantz)
   * Added novel circumstance category (Concept) and fixed various keybindings
 * IG-Inception v0.2.3 (09/09/2020, C. Frantz)
   * Resolved inconsistent component naming (activation conditions, execution constraint) in constitutive and regulative syntax
   * Unified handling of animacy annotations
 * IG-Inception v0.2.2 (30/08/2020, C. Frantz)
   * Fixed conflicting keybindings in IG Institutional Statement Layer
   * Added ability to indicate negation for constitutive components
   * Minor refinements of descriptions
 * IG-Inception v0.2.1 (19/06/2020, C. Frantz)
   * Revised terminology for regulative statements, renamed regulative and constitutive components to simplicity
   * Reviewed tag sets for consistency across different layers, refined configuration for visible annotations to improve legibility
   * Introduced institutional function annotation
   * Revised UIMA namespaces
 * IG-Inception v0.2.0 (15/06/2020, C. Frantz)
   * Refined and completed full constitutive syntax layer, reviewed underlying naming schema, added coding guidelines
   * Revised UIMA namespaces
 * IG-Inception v0.1.2 (02/05/2020, C. Frantz)
   * Added constitutive syntax layer (components, corresponding tagsets, conditional annotations); renamed 'IG Core' Layer to 'IG Core Regulatory Syntax'
   * Added policy relationship specification
 * IG-Inception v0.1.1 (01/05/2020, C. Frantz)
   * Intermediate release with modified context taxonomy
 * IG-Inception v0.1 (29/04/2020, C. Frantz) - Initial release
