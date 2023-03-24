# Reference guidelines

Status: **DRAFT**

## API design criteria

What does make a good web API? A good API has to provide some functionality that users want to use programmatically. Here is a set of quality criteria.

ID | Name | Description
--- | --- | ---
AQC-1 | Simplicity | The API must expose the functionality that users want in the most straightforward way possible; To keep the most frequent scenarios easy and simple; To make the common case awesome and the advanced case possible.
AQC-2 | Expressive | The API must allow the users to express what they want to do; The functionaly supported by the API must be easy to be accessed by the users.
AQC-3 | Predictability | The API must rely on repeated, consistently applied, predictable patterns that are easier and faster to learn.
AQC-4 | Operational | The API must do what the users actually want to do.
AQC-5 | Sustainability | The API must rely on solid concepts mainly related to the domain; APIs are generally very rigid and therefore not easy to change.
AQC-6 | Consistency | The API must stick with one set of naming conventions, patterns and principles.

These quality criteria are supported by a set of standard design principles and standard design patterns.

## API design principles

A design principle is a standard design rule or guideline that has to be applied consistently. It aims to guide the designer towards building a good API.

ID | Name | Description
--- | --- | ---
AP-1 | Expressive naming | A name must clearly convey the thing that it’s naming.
AP-2 | Simple naming | A name should not be excessively long nor oversimplified either; Each additional part of a name must add value to justify its presence.
AP-3 | Predictable naming | The same name should be used to represent the same thing and different names to represent different things; To allow users of the API to learn one name and continue building on that knowledge; To choose a naming design and stick to it.
AP-4 | Naming language | The maximum interoperability across the world; English language concepts should be used and common American-style spellings should generally be preferred; To choose one language and stick to it.
AP-5 | Naming grammar | To use imperative actions, to avoid prepositions, and to use pluralization for naming collection name of a bunch of REST resources; To choose one grammar and stick to it.
AP-6 | Naming syntax | URL names take on kebab case and field names take on camel case; To choose one syntax and stick to it.
AP-7 | Naming terminology | To reflect the domain language and model on the API language and model or resource layout.
AP-8 | Contextual naming | The naming is specific to one domain language and model. 
AP-9 | Resource | One separate resource for one concept, if it is needed to atomically interact with that concept.
AP-10 | Resource relationship | To only store relationships if they provide important functionality to the API; To avoid overly deep hierarchical relationships.
AP-11 | Typing | To think in terms of the data types offered by the chosen serialization format. To ensure types are documented well enough so that clients are never surprised by their behavior.
AP-12 | Missing values |
AP-13 | Default values |
AP-14 | Less is more | To expose a minimal set of attributes to avoid sustainable coupling by the clients
AP-15 | Hide your internals | To not expose the technical implementation details to the outside

## API design patterns

A design pattern is a standard, well-known, approved, reusable, and adaptable piece of design. It acts as a blueprint for solving similarly structured problems and focuses on a structural or a behavioural aspect. Finally, design patterns help minimize the need for large structural changes.

### REST

ID | Name | Solves
--- | --- | ---
[APAT-1](apat-1-resource-identification.md) | Resource identification | How to identify resources in an API
APAT-2 | Standard methods | The set of standard methods for use in resource-oriented APIs
APAT-3 | Partial updates and retrievals | How to interact with portions of resources
APAT-4 | Custom methods | Using custom (non-standard) methods in resource-oriented APIs
APAT-5 | Association resources | How to manage many-to-many relationships with metadata
APAT-6 | Long-running | How to handle methods that are not instantaneous
APAT-7 | Rerunnable jobs | Running repeated custom functionality in an API
APAT-8 | Cross references | How to reference other resources in an API
APAT-9 | Association resources | How to manage many-to-many relationships with metadata
APAT-10 | Add and remove custom methods | How to manage many-to-many relationships without metadata
APAT-11 | Polymorphism | Designing resources with dynamically-typed attributes
APAT-12 | Copy and move | Duplicating and relocating resources in an API
APAT-13 | Batch operations | Extending methods to apply to groups of resources atomically
APAT-14 | Criteria-based deletion | Deleting multiple resources based on a set of filter criteria
APAT-15 | Anonymous writes | Ingesting unaddressable data into an API
APAT-16 | Pagination | Consuming large amounts of data in bite-sized chunks
APAT-17 | Filtering | Limiting result sets according to a user-specified filter
APAT-18 | Importing and exporting | Moving data into or out of an API by interacting directly with a storage system
APAT-19 | Versioning and compatibility | Defining compatibility and strategies for versioning APIs
APAT-20 | Soft deletion | Moving resources to the “API recycle bin”
APAT-21 | Request deduplication | Preventing duplicate work due to network interruptions in APIs
APAT-22 | Request validation | Allowing API methods to be called in “safe mode”
APAT-23 | Resource revisions | Tracking resource change history
APAT-24 | Request retrial | Algorithms for safely retrying API requests
APAT-25 | Request authentication | Verifying that requests are authentic and untampered with
