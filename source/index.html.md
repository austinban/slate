---
title: API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://www.crystalknows.com/'>Crystal Home Site</a>
  - <a href='mailto:hello@crystalknows.com'>Contact Us</a>

includes:
  - errors

search: true
---

<header>
Documentation
</header>

# Introduction

Welcome to the Crystal API! You can use our API to access Crystal API endpoints to return personality profiles, analyze text samples, or retrieve user information with an access token.

This is the first implementation of our API and would love to hear your feedback and questions.

[Send us an email here.](mailto:hello@crystalknows.com)

## Endpoints

Here's a quick overview of our API endpoints:

Method | Endpoint | Usage   | Response Type
------ | -------  | ------- | -------
Post   | [/v1/person_search](#person-search)| Returns profile based on person attributes       | application/json
Get    | [/v1/me/text_sample](#text-sample)     | Returns profile based on text samples            | application/json
Get    | [/v1/results/:requestID](#request-id) | Retrieve user information for given access token | application/json

# Person Search

> Example parameter data

```json
{
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "companyName": "string",
  "location": "string"
}
```

> Example cURL command

```shell
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \
   "firstName": "string", \
   "lastName": "string", \
   "email": "string", \
   "companyName": "string", \
   "location": "string" \
 }' 'https://enterprise-api.crystalknows.com/v1/person_search'
```

> Example response

```json
{
  "requestID": "string"
}
```

The `person_search` method returns a profile based on the persons attributes.

<indent>Method:</indent> Post

<indent>Endpoint:</indent> /v1/person_search

<indent>Usage:</indent> Returns profile based on person attributes

<indent>Response Type:</indent> application/json

To check error codes, reference [our guide](#errors).

# Text Sample

> Example parameter data

```json
{
  "textSample": "string"
}
```

> Example cURL command

```shell
curl -X GET --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \
   "textSample": "string" \
 }' 'https://enterprise-api.crystalknows.com/v1/me/text_samples'
```

> Example response

```json
{
  "requestID": "string"
}
```

The `text_sample` method returns a profile based on the passed text samples.

<indent>Method:</indent> Get

<indent>Endpoint:</indent> /v1/me/text_sample

<indent>Usage:</indent> Returns profile based on text samples

<indent>Response Type:</indent> application/json


To check error codes, reference [our guide](#errors).

# Request ID

> Example cURL command

```shell
curl -X GET --header 'Accept: application/json' 'https://enterprise-api.crystalknows.com/v1/results/:requestId'
```

> Example response

```json
{
  "results": {
    "text_type": 0,
    "confidence": "string",
    "scores": {
      "d": 0,
      "i": 0,
      "s": 0,
      "c": 0
    }
  },
  "type": "string",
  "id": "string"
}
```

The `requestID` method retrieves user information for a given access token.

<indent>Method:</indent> Get

<indent>Endpoint:</indent> /v1/results/:requestID

<indent>Usage:</indent> Retrieve user information for given access token

<indent>Response Type:</indent> application/json

To check error codes, reference [our guide](#errors).
