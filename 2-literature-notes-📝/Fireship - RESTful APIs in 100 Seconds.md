# Fireship - RESTful APIs in 100 Seconds

Week 14.4 | Thursday, April 06, 2023 | 06:40 PM

author : [Fireship](https://www.youtube.com/@Fireship)
source : https://youtu.be/-MTSQjw5DrM
topics : [RESTful APIs](RESTful APIs) [REST API](REST API)
related : [NodeJS Express](NodeJS Express) [Application Programming Interface (API)](Application Programming Interface (API))

## Takeaways and Inspirations

API

- A way for two computer to talk to each other
- Instead of buttons and filling out forms we use code to interface and request data from a server
- Can comb though the web page OR request the data via code that returns a JSON file

APIs that are RESTful

- APIs that follow a standardized set of rules, specifications, and constraints AKA REpresentational State Transfer
- A RESTful API organizes data entities or resources into a bunch of unique URIs (Uniform Resources Identifiers) that differentiate different types of data resources on a server

### API Format

#### API Start Line

- A client can get data about a resource by making a request to that endpoint over http

  - The request message has a specific format : HTTP verb or request method followed by the URI : `POST /astroids`

- Standardize API calls (and more)
  - `GET` : to read data
  - `POST` : to create data
  - `PATCH` : to update data
  - `DELETE` : to remove/destroy data

#### API Headers

Beneath the Start line we have the headers which contains the metadata of the request

- `Accept` : tell there server in a particular format
- `Authorization` : tells the server we are allowed to make that request

#### API Body

Contains the custom payload of data

#### In the end

This request is given to the server where it executes some code to read from a database that can then be formatted into a response message

### RESTful APIs are stateless

The two systems client and server don't need to store any information about each other and every request is independent from all other communication
