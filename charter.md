# JSON Schema IDL charter
The purpose of this charter is to give a brief introduction to the project, the SIG and the community how they all relate.

## Section 0: Guiding Principles

Because of the nature of JSON Schema you don't define the data structure but the validation rules that data should comply with, trying to interpret these rules definitions are a pain-point for many. Providing a clear description of how this can be achieved would help not only the developer that uses JSON Schema in this area, but also help standardize the behavior improving the user experience.

## Section 1: Scope

Help and clarify how JSON Schema can be interpreted from validation rules to data definition. This extends to how those data definitions can be represented in any programming language. To accommodate the JSON Schema spec and the interpretation process a code generation vocabulary will be created.

Implementations is neither in or out of scope for the SIG, but it is not a high prioritization.

## Section 2: Relationship with JSON Schema organization.

The SIG is not involve with the actual JSON Schema specification, they are nothing more then a user of it. The JSON Schema organization may force this SIG group to comply with organization level code of conducts, workflow changes, etc. 

## Section 3: The Special interest group

SIG memberships are not time-limited. There is no maximum size of the SIG. It is expected that the SIG members actively participate in discussions and maintain the repository, otherwise they will remain a contributor.

Any SIG members that does not actively participate in discussions and maintain the repository within 30 days will be removed from the SIG list and be contributors.

The working group is currently made up of the following individuals, and feel free to submit issue requested to be added. 

- Jonas Lagoni ([Senior Software Engineer at Postman, working on AsyncAPI](https://www.linkedin.com/in/jonaslagoni/))
- Jason?

## Section 4: Roles & Responsibilities 

The SIG members are no different from the regular community beside it is their responsibility to understand all points of view of the community and push the project forward. 

The community can get involved by jumping into discussions in issues, pull requests, etc, as long as the [Code of Conduct](./CODE_OF_CONDUCT.md) and [git workflow](./git_workflow.md) is adhered to.

## Section 5: Definitions

Definitions that should be clarified to align meaning.

- **Validation rules**, i.e. a JSON Schema as such `{type: string}` define that data should validate against a string, it does not define that the data is a string. For small validation rules there is almost no difference, but more complex ones it become apparent. 
- **Data definition**, i.e. it defines the exact structure of the data.