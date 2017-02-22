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

<hollow-button>
[Send us an email](mailto:hello@crystalknows.com)
</hollow-button>

## Endpoints

Here's a quick overview of our API endpoints:

Method | Endpoint | Usage   | Response Type
------ | -------  | ------- | -------
Post   | [/v1/person_search](#person-search)| Returns profile based on person attributes       | application/json
Get    | [/v1/me/text_sample](#text-sample)     | Returns profile based on text samples            | application/json
Get    | [/v1/results/:requestID](#request-id) | Retrieve user information for given access token | application/json

# Person Search

The `person_search` method returns a profile based on the persons attributes.

## PS Summary

> Example parameter data

```json
{
  "first_name": "Marty",
  "last_name": "McFly",
  "email": "example@example.com",
  "company_name": "Crystal Project",
  "location": "Hill Valley, California"
}
```

> Example cURL command

```shell
curl -X POST --header 'Content-Type: application/json' --header 'Accept: application/json' -d '{ \
  "first_name": "Marty", /
  "last_name": "McFly", /
  "email": "example@example.com", /
  "company_name": "Crystal Project", /
  "location": "Hill Valley, California" /
 }' 'https://enterprise-api.crystalknows.com/v1/person_search'
```

<indent>Method:</indent> Post

<indent>Endpoint:</indent> /v1/person_search

<indent>Usage:</indent> Returns profile based on person attributes

<indent>Response Type:</indent> application/json

## PS Response Parameters

> Example response

```json
{
  "status": "complete",
  "data": {
    "results": {
      "first_name": "Marty",
      "last_name": "McFly",
      "accuracy_rating": "5",
      "location": "Hill Valley, California",
      "company": "Crystal Project",
      "job_title": "Software Architect",
      "disc_scores": {
        "type": "C",
        "confidence": 90,
        "scores": {
          "d": 1451,
          "i": 1636,
          "s": 1766,
          "c": 4347
        }
      }
    },
    "type": "personSearch",
    "recommendations": {
      "email": {
        "overview": "",
        "phrases": [
          "Provide lots of detailed information and instructions",
          "Ask them something that will require a long and thoughtful response",
          "Send lots of extra information (like links and attachments)",
          "Use data to prove a point",
          "Use a formal greeting and closing"
        ],
        "hints": [
          "Be detailed",
          "Be logical",
          "Be clear",
          "Be detailed",
          "Be interesting"
        ],
        "tips": [
          "\"We have time\"",
          "Lots of detail",
          "\"What are your thoughts?\"",
          "\"...need more information\"",
          "\"These are the rules\""
        ],
        "suggestions": [
          "<b class=\"red\">Shouldn't of</b> should be <b class=\"green\">shouldn't have</b> This person notices grammatical mistakes.",
          "This person questions and challenges absolute claims, so instead of <b class=\"red\">there is absolutely</b>, use <b class=\"green\">there is almost certainly</b>.",
          "This person questions and challenges absolute claims, so instead of <b class=\"red\">there are absolutely</b>, use <b class=\"green\">there is almost certainly</b>.",
          "This person questions and challenges absolute claims, so don't say <b class=\"red\">\"definitely\"</b> unless you are 100% certain.",
          "This person questions and challenges absolute claims, so instead of <b class=\"red\">\"100% sure\"</b>, use <b class=\"green\">\"almost certainly\"</b>."
        ],
        "example": {
          "subject": "Request for a meeting",
          "greeting": "Hello This person,",
          "body": "Hi This person,\n\nMy name is [user_name], and I work for ABC company as a product manager. I have been reading your ideas on management, and many of them have resonated with me as I tackle similar challenges in my role.\n\nI am also located in Boston. If you have the time, I'd like to buy you a coffee at some point over the next few weeks to ask a few career-related questions. Would you be open to that?\n\nThanks,\n[user_name]",
          "description": "<p>This person will only want to meet if there is a <b>clear purpose</b> for the meeting, and you articulate your <b>motivations</b>.</p>",
          "call_to_action": "Reach out if this information is unclear or you'd like for anything to be explained in more detail.",
          "opening": "I appreciate you taking the time to review the following e-mail, in which I'd like to discuss ______.",
          "closing": "Thanks,"
        }
      },
      "motivation": {
        "overview": "This person will probably <b>avoid</b> <b>unpredictable</b> situations unless it's entirely necessary. They are well suited for roles that allow them to work independently, at a <b>careful</b>, <b>methodical</b> pace.",
        "phrases": [
          "Accuracy & precision",
          "Exploration & discovery",
          "Being correct",
          "Competence & skill",
          "Stability"
        ]
      },
      "speaking": {
        "overview": "This person is intentional and naturally reserved. Use <b>neutral</b>, <b>detached</b> tone and keep expressive gestures to a minimum when working with them.",
        "phrases": [
          "Give them enough time to think before responding",
          "Ask them to explain something in detail",
          "Provide your reasoning before you get to the bottom line",
          "Guide the conversation with questions",
          "Ask lots of questions to keep their attention"
        ]
      },
      "talent": {
        "overview": "When This person feels comfortable, they are <b>confident</b>, <b>insightful</b>, and enjoys <b>deep</b>, <b>detailed</b> discussion. This person might be <b>introverted</b> in high-pressure or formal environments.",
        "phrases": [
          "Read an instruction manual",
          "Like spreadsheets",
          "Pay close attention to all the details",
          "Make decisions based purely on logic",
          "Review all of the facts before making a big decision"
        ]
      },
      "trust": {
        "overview": "This person is naturally leery of people who treat their work with indifference. This person possesses an innate sense of self and will gravitate to people who have similar high principles.",
        "phrases": [
          "Project accuracy, rather than boldness",
          "Debate frequently and objectively",
          "Always prove your points with data",
          "Promptly admit when you are wrong",
          "Respect their time and space boundaries"
        ]
      },
      "use_case": {
        "overview": "",
        "phrases": [
          "Leave detailed voicemails",
          "Focus on the \"here and now\"",
          "Expect them to ask lots of questions",
          "Present proven facts and statistics instead of customer stories",
          "Ask primarily \"yes or no\" questions"
        ]
      },
      "workplace": {
        "overview": "",
        "phrases": [
          "Take time to work out logical conclusions",
          "Compliment quality of their work",
          "Spend time creating and maintaining high standards",
          "Use logical appeals if you argue",
          "Do your homework before a meeting"
        ]
      }
    },
    "id": "70b4843e-8453-4b26-88e4-0114ddea3cbc"
  }
}
```

<indent>`"status"`</indent>

<indent>`"accuracy_rating"`</indent>

<indent>`"job_title"`</indent>

<indent>`"disc_scores"`</indent> contains all of the information regarding the person's DISC ratings.

<secondary><indent>`"type"`</indent> is ... </secondary>

<secondary><indent>`"confidence"`</indent> is a `string` with a percentage between 0-100%. This is our metric for how confident we are in the accuracy of our analysis of this person's DISC profile.</secondary>

<secondary><indent>`scores`</indent> is an `array` of four integers; `d`, `i`, `s`, and `c`.</secondary>

<indent>`type`</indent> is a `string` that contains the type profile of this analyzed person. An example type would

<indent>`recommendations`</indent> contains all of the tips and hints for communicating with a person of this DISC profile.

<indent>`id`</indent> is the request ID from the API.


## PS Response Codes

Code | Meaning
---------- | -------
200 | Success -- Not an error, just happy things
400 | Missing Valid Param -- Check parameters for errors
401 | Key Was Invalid -- Your API key is wrong

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

### Summary

<indent>Method:</indent> Get

<indent>Endpoint:</indent> /v1/me/text_sample

<indent>Usage:</indent> Returns profile based on text samples

<indent>Response Type:</indent> application/json

### Response Codes

Code | Meaning
---------- | -------
200 | Success -- Not an error, just happy things
400 | Missing Valid Param -- Check parameters for errors
401 | Key Was Invalid -- Your API key is wrong

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

### Summary

<indent>Method:</indent> Get

<indent>Endpoint:</indent> /v1/results/:requestID

<indent>Usage:</indent> Retrieve user information for given access token

<indent>Response Type:</indent> application/json

### Response Codes

Code | Meaning
---------- | -------
200 | Success -- Not an error, just happy things
401 | Key Was Invalid -- Your API key is wrong
