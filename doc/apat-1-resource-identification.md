# Access to one resource

## Standards

**Use nouns not verbs.**

* GET /clients/1
* POST /clients
* PATCH /accounts/1
* PUT /orders/1
* DELETE /addresses/1

**Use plurals to manage both collection and instance resources.**

* Collection: /users
* Instance: /users/007

**Use hierarchical URLs to imply structure (aggregation or composition).**

GET /orders/123/products/1

## Samples

The investment proposal resource identified by 123

`GET /investment-proposals/123`

The user resource identified by vondacho inside the organisation resource identified by Lumberjacks

`GET /organisations/Lumberjacks/users/ovondach`

The one default strategy resource attached to the portfolio resource identified by 123

`GET /portfolios/123/default-strategy`

The singleton user information resource

`GET /user-info`

# Access to more than one resource

All the organisations

`GET /organisations`

A list of identified organisations: 1,2,3

`GET /organisations?id=1&id=2&id=3`

All the organisations with name `lumb`

`GET /organisations?name=lumb`

The users of the organisation `lumberjacks`

`GET /organisations/lumberjacks/users`

The users of all organisations with first name `doe` and last name `doe`

`GET /organisations/users?firstName=john&lastName=doe`

# Access to some fields (projection)

Name, tags, and partner of the users of the organisation `lumberjacks`

`GET /organisations/lumberjacks?fields=name,tags,partner`

List all the organisations with all their attributes

`GET /organisations?view=full`

A predefined and minimal subset of the attributes of all the organisations

`GET /organisations?view=minimalistic`