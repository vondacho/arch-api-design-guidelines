## Standards

**Use nouns not verbs**

* get `GET /clients/1dbd456aa-c129-4904-a44b-f115a6e851a3`
* list `GET /clients`
* create `POST /clients`
* update `PATCH /accounts/c47a0e82-e956-437d-8801-5d21a4f1b7f0`
* replace`PUT /orders/e7c07022-f583-4245-80a8-f20222e55e46`
* remove `DELETE /addresses/0659c040-1a73-4437-bf0a-86c33e44ce64`

**Use plurals to manage both collection and instance resources**

* Collection: `/users`
* Instance: `/users/johndoe`

**Use hierarchical URLs to imply structure (aggregation or composition)**

`GET /orders/e7c07022-f583-4245-80a8-f20222e55e46/products/2d2d6af5-e37c-408b-981e-f834bf4c162e`

**Use business unique identifiers or opaque and hard to guess ones**

Do not expose a database primary key as identifier but a logical unique one.  

`/organisations/Lumberjacks`
`/citizens/756-1234-4321-01`
`/clients/1dbd456aa-c129-4904-a44b-f115a6e851a3`

# Access to one resource

The investment proposal resource identified by 5558fba8-104f-464a-a2d2-76837a1895a6

`GET /investment-proposals/5558fba8-104f-464a-a2d2-76837a1895a6`

The user resource identified by johndoe inside the organisation resource identified by Lumberjacks

`GET /organisations/Lumberjacks/users/johndoe`

The one default strategy resource attached to the portfolio resource identified by 0c92d1b7-04f4-48ab-9333-83ec916b08a6

`GET /portfolios/0c92d1b7-04f4-48ab-9333-83ec916b08a6/default-strategy`

The singleton user information resource

`GET /user-info`

# Access to more than one resource

All the organisations

`GET /organisations`

A list of identified organisations: Lumberjacks,Lions

`GET /organisations?id=Lumberjacks&id=Lions`

All the organisations with name `lumb`

`GET /organisations?name=lumb`

The users of the organisation `Lumberjacks`

`GET /organisations/Lumberjacks/users`

The users of all organisations with first name `doe` and last name `doe`

`GET /organisations/*/users?firstName=john&lastName=doe`
`GET /organisations/users?firstName=john&lastName=doe`

# Access to some fields (projection)

Name, tags, and partner of the users of the organisation `Lumberjacks`

`GET /organisations/Lumberjacks?fields=name,tags,partner`

List all the organisations with all their attributes

`GET /organisations?view=full`

A predefined and minimal subset of the attributes of all the organisations

`GET /organisations?view=minimalistic`