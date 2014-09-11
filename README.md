# Word Count Validator

### Description

We want to verify that a client can count words. As such, we need a web service that supplies clients with a "test" and allows the client to submit an answer. If the client and the service were people, their conversation might go something like this:

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


### Requirements

Write a server that does 2 things

1. Give a client at least the following:
    1. A random body of text
    2. A list of some but not all words in that body of text
2. Receive in a request at least the following:
    1. A body of text
    2. A list of some but not all words in that body of text
    3. A count of the frequency of every word in the body of text excluding words from the list
    and responds
    1. If the word frequency count is correct, then `200 OK`
    2. If the word frequency count is incorrect or the request is otherwise invalid, then `400 Bad Request`


A client for this server is expected to:

1. Request from 1
2. Count the frequency of each word in the given body of text minus all of the given exclusion words
3. Send to 2 the word frequency count result with the original response body from 1.

You are not required to write the client application.

### Guidelines

1. If your service _can_ run on Mac OSX, then please include the following:
    1. Any installation instrcutions or notes to set up our Mac OSX laptops to run your server
    2. A script `./run` to start the server
    3. The server should run on `localhost:8000` and serve a single path `/`
2. If your service _cannot_ run on Mac OSX, then please run your server on a remote host and provide us the hostname, port, and path to access it.
3. Style, algorithms, data structures, request/response format, etc. are all up to you. However, keep in mind that we will be looking at these choices.

### Bonus

1. **Tests**: You verify that your own service works as expected
2. **Add Source Text**: Add an admin tool to add new sources of text to the system.
3. **Cheating Protection**: When the server receives text, exclusion words, and a word count from the client, it verifies that the text and exclusion words that it previously gave a client.
4. **Stateless/Idempotent**: Remove as much "state" as possible from the server. Any new request to the server does not depend on the state of a previous request.

