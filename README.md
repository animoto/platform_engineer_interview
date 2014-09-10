# Word Count Validator

We've decided that we want the clients of our service to be able to count words. As such, we need a web service that supplies clients a "test" and allows the client to submit an answer. If the client and the service were people, their conversation might go something like this:

> **Client**: Service, can you give me some words to count?
> 
> **Service**: Sure. Please count the frequency of the words in "The quick brown > fox jumped over the lazy dog" but please ignore the words "the" and "dog".
> 
> **Client**: Ok, here are my results: "quick" appeared once, "brown" appeared > once, "fox" appeared once, "jumped" appeared once, "over" appeared once, > "lazy" appeared once, and "the" appeared twice.
> 
> **Service**: Hmm, looks like some of the counts are not what I'd expect.
> 
> **Client**: Opps, I included "the" when you told me not to. Here are the > counts again ... *[omitted]*
> 
> **Service**: Looks great.

## As a client of the service

### Acceptance Criteria

**Get Words**: As a client of the service I want to submit an HTTP request and get a `JSON`-formated response with a block of text to be analyzed and a list of words to be excluded from analysis.  Example output might look like:

```
{
    "text": "lorem ipsum",
    "excluded": ["lorem"]
}
```

**Submit Words**: As a client of the service I want do submit an HTTP request containing the analysis of text previously supplied by the service for verification. The request should at least include word counts. I expect that proper analysis will result in a `200` response code and a `400` response code if my analysis is incorrect.

**Setup and Run**: As the admin, I want to be able to run the service on `localhost`, port `8000`, with a single command `run`. There should be a single path served: `/`.

### Bonus

**Add Source Text**: As an administrator, I'd like to be able to easily add new sources of text to the system.

**Cheating Protection**: It should not be possible for a client to submit an incorrect analysis or an analysis for a text that was not given by the system.

**Statelessness**: Try to remove as much "state" as possible from the server.

## Guidelines

Write a web service that fulfils the above scenarios. Submit a pull request when you are done.

Not all the user stories are required, we understand that you have limited time.

The assumptions and details for the user stories are entirely up to you, add as much detail or as little detail as you like.

Style and design are also entirely up to you.

If you are unable to finish a user story, add a comment to the pull request explaining how you were planning to code the user story and why you were unable to do it.


