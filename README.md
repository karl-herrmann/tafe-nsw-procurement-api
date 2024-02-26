# tafe-nsw-procurement-api
Demo TAFE NSW Procurement API

# use case 1: A client can periodically consume the API to enable it (the client) to maintain a copy of the provider API's staff records

GET:: /unsecured/staff endpoint, allows the API to, Retrieve a list of all staff members

# use case 2: The API should provide an endpoint that allows the HR system to notify the API of a changed record(s), this can be dispersed to any interested listeners

POST:: /listener/staff/notify endpoint, allows the API to, Notify API of changed record(s).

# use case 3: The creation and removal of a staff member requires a special privilege that only certain applications can have (such as a recruitment system notifying the HR system of a new joiner)

POST:: /special-privilege/staff/create endpoint, allows the API to, Create a new staff member with special privilege. Apply a trait to that endpoint around creation of that account (authentication), then apply another trait to the endpoints for creating and removing users around authorization. Namely 'secured' endpoints UPDATE:: /secured/staff/{id} for updating and DELETE:: /secured/staff/{id} for removing. I would apply policies via say an OAUTH token validation for authenticating the staff member with a 'special privilege' to call these end points to allow the update and removal of accounts. The special privilege is similar to an 'admin' style of account

