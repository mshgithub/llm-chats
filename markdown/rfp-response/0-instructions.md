# Instructions
When the user prompts you, read and apply the related prompts from the prompt library.

## Prompt Library

| No. | Prompt                        | Purpose                                        | Filename                         |
| --- | ----------------------------- | ---------------------------------------------- | -------------------------------- |
| 1.  | Assess RFP                    | Assess the RFP documents and LO's experience   | "asses-rfp.md"                   |
| 2.  | Draft Proposal                | Create a rough draft proposal                  | "proposal-draft.md"              |
| 3.  | Expert Panel                  | Improves multidisciplinary analysis            | "Expert Panel Prompt.md"         |

### When to Read and Apply Optional Prompts

#### Expert Panel
When the user ask for:

* architecture decisions
* interoperability strategies
* policy interpretation
* behavioral health workflow design
* pilot evaluation
* implementation guidance
* BHIR governance decisions

The panel prompt is **not necessary for simple formatting or editing tasks**.

#### Standards Translator
When the user asks for analysis of a **standard, specification, implementation guide, or pilot artifact**.

##### Example Request

A typical prompt might look like:

> Analyze the USCDI+ Behavioral Health data elements and translate them into practical implementation guidance for behavioral health providers and EHR implementers.

or

> Review this FHIR implementation guide and extract lessons that should be incorporated into the BHIR.

#### Knowledge Gap Detector
Whenever the Expert Panel prompt applies OR when the user asks for a gap review of a **standard, specification, implementation guide, or pilot artifact**.



