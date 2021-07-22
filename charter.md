# JSON Schema IDL charter
The purpose of this charter is to give a brief introduction to the project, the SIG, and the community how they all relate.

## Section 0: Guiding Principles

Because of the nature of JSON Schema, you don't define the data structure but the validation rules that data should comply with, trying to interpret these rules definitions is a pain point for many. Providing a clear description of how this can be achieved would help not only the developer that uses JSON Schema in this area, but also helps standardize the behavior improving the user experience.

## Section 1: Scope

Help and clarify how JSON Schema can be interpreted from validation rules to data definition. This extends to how those data definitions can be represented in any programming language. To accommodate the JSON Schema spec and the interpretation process a code generation vocabulary will be created.

Implementations are neither in nor out of scope for the project, but it is not a high prioritization.

A test suite is expected to be produced along side the work, to better discuss and formulate specific cases.

## Section 2: Relationship with JSON Schema organization.

The project is not directly involved with the actual JSON Schema specification development, however contributors may be contributors of both. The JSON Schema organization and community may provide guidance and review on vocabulary proposals and proposed releases. It is expected that this project and resulting artifacts will be maintained by teams other than those part of the JSON Schema organization.

The JSON Schema organization will force this project to comply with the organization-level code of conduct if required, and may require other project level changes such as workflow changes.

## Section 3: The Special interest group

The SIG members are no different from the regular community besides it is their responsibility to understand all points of view of the community and push the project forward. 

The community can get involved by jumping into discussions in issues, pull requests, etc, as long as the [Code of Conduct](./CODE_OF_CONDUCT.md) and [git workflow](./git_workflow.md) is adhered to.


SIG memberships are not time-limited. There is no maximum size of the SIG. It is expected that the SIG members actively participate in discussions and maintain the repository, otherwise they will remain a contributor.

Any SIG members that do not actively participate in discussions or maintain the repository within 30 days will be removed from the SIG list and return to being contributors.

The SIG group is currently made up of the following individuals. Feel free to submit an issue requested to be added. 

- Jonas Lagoni ([Senior Software Engineer at Postman, working on AsyncAPI](https://www.linkedin.com/in/jonaslagoni/))
- [Jason Desrosiers](https://github.com/jdesrosiers)

## Section 4: Definitions

Definitions that should be clarified to align meaning.

- **Validation rules**, i.e. a JSON Schema as such `{type: string}` define that data should validate against a string, it does not define that the data is a string. For small validation rules, there is almost no difference, but with more complex ones it becomes apparent. 
- **Data definition**, i.e. it defines the exact structure of the data.
