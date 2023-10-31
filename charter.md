# JSON Schema IDL charter

The purpose of this charter is to give a brief introduction to the project, the SIG, and the community how they all relate.

## Section 0: Guiding Principles

Because of the nature of JSON Schema (constraints, not data definition), trying to interpret these rules definitions is a pain point for many. Providing a clear description of how this can be achieved would standardize the behavior improving the user experience and thus help any developers working with JSON Schema.

## Section 1: Scope

Help and clarify how data definition and JSON Schema's validation rules can interact. This includes how those validation rules can represent code in any programming language. To accommodate the JSON Schema spec and the interpretation process, a code generation vocabulary will be created.

Implementations are neither in nor out of scope for the project, but it is not a high prioritization.

A test suite is expected to be produced along side the work, to better discuss and formulate specific cases.

## Section 2: Relationship with JSON Schema organization.

The project is not directly involved with the actual JSON Schema specification development, however contributors may be contributors of both. The JSON Schema organization and community may provide guidance and review on vocabulary proposals and proposed releases. It is expected that this project and resulting artifacts will be maintained by teams other than those part of the JSON Schema organization.

The JSON Schema organization will force this project to comply with the organization-level code of conduct if required, and may require other project level changes such as workflow changes.

## Section 3: The Special interest group

The SIG members are no different from the regular community besides it is their responsibility to understand all points of view of the community and push the project forward.

The community can get involved by jumping into discussions in issues, pull requests, etc, as long as the [Code of Conduct](https://github.com/json-schema-org/.github/blob/main/CODE_OF_CONDUCT.md) and [git workflow](./git_workflow.md) is adhered to.

SIG memberships are not time-limited. There is no maximum size of the SIG. It is expected that the SIG members actively participate in discussions and maintain the repository, otherwise they will remain a contributor.

Any SIG members that do not actively participate in discussions or maintain the repository within 30 days will be removed from the SIG list and return to being contributors.

The SIG group is currently made up of the following individuals. Feel free to submit an issue requested to be added. 

- [Greg Dennis](https://github.com/gregsdennis)
- [Jonas Lagoni](https://github.com/jviotti)
- [Jason Desrosiers](https://github.com/jdesrosiers)

## Section 4: Definitions

Definitions that should be clarified to align meaning.

- **Validation rules**, i.e. a JSON Schema as such `{ "type": "string" }` defines that data, as represented in the JSON data model, should be a string; it does not define that the data must be a string in programming languages.  For example,`"2023-10-31"` is a string in JSON; however, this value represents a date, for which there will likely be a dedicated type separate from a string in many programming languages. For small validation rules, there is almost no difference, but with more complex ones it becomes apparent. 
- **Data definition**, i.e. it defines the exact structure of the data.  This is often how programming languages build types.  These type systems are generally considerably more extensive than the JSON data model.
