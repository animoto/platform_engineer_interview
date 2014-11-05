# Word Count Validator

## Objective

Recently the internet has exploded to reach across the galaxy.  There is a hostile species of troll aliens that have started infesting the internet with disruptive, angry comments on internet forums.  Scientists have determined that
the troll aliens are really bad at counting words.  Thus they have tasked you with creating a type of CAPTCHA for troll aliens to keep them out of the forums. (http://en.wikipedia.org/wiki/CAPTCHA)

## Description

We want to verify that a client can count words. As such, we need a web service that supplies clients with a "test" and allows the client to submit an answer. If the client and the service were people, their conversation might go something like this:

> **Client**: Service, can you give me some words to count?
> 
> **Service**: Sure. Please count the frequency of the words in "The quick brown fox jumped over the lazy dog" but please ignore the words "the" and "dog".
> 
> **Client**: Ok, here are my results: "quick" appeared once, "brown" appeared once, "fox" appeared once, "jumped" appeared once, "over" appeared once, "lazy" appeared once, and "the" appeared twice.
> 
> **Service**: Hmm, looks like some of the counts are not what I'd expect.
> 
> **Client**: Opps, I included "the" when you told me not to. Here are the counts again ... *[omitted]*
> 
> **Service**: Looks great.


## Requirements

Write a server that does 2 things

### 1. Respond to a client HTTP request

Respond to a client HTTP request with at least the following in the response body:

1. A random body of text. Some sample texts are included in the file: texts.tar.gz
2. A list of some but not all words in that body of text (exception: texts with only one unique word should use an empty list)

### 2. Receive a client HTTP request

Receive a client HTTP request with at least the following in the request

1. A body of text
2. A list of some but not all words in that body of text (exception: texts with only one unique word should have an empty list)
3. A count of the frequency of every word in the body of text excluding words from the list

and respond with:

1. If the word frequency count is correct, then `200 OK`
2. If the word frequency count is incorrect or the request is otherwise invalid, then `400 Bad Request`

You are *not* required to write the client application, but you can assume that a client for this server should:

1. Request from 1
2. Count the frequency of each word in the given body of text minus all of the given exclusion words
3. Send to 2 the word frequency count result with the original response body from 1.

### Readme

Writing software in a fast-paced, independent environment involves discovering and resolving many ambiguities. Your ability to make good assumptions and trade-offs is key. Keep the objective of the assignment in mind when making such decisions.  Please include a readme document in your submission that describes any assumptions or decisions.

## Guidelines

1. You should feel free to write your solution in whichever language you are most comfortable writing.
2. Style, algorithms, data structures, request/response format, etc. are all up to you. However, keep in mind that we will be looking at these choices.
2. If your service can run on a Unix environment (e.g. ) Mac OSX, then please include the following:
    1. Any installation instructions or notes to set up our Mac OSX laptops to run your server
    2. A script `./run` to start the server
    3. The server should run on `localhost:8000` and serve a single path `/`
3. If your service _cannot_ run on Mac OSX, then please run your server on a remote host and provide us the hostname, port, and path to access it.

## Bonus

1. **Tests**: You verify that your own service works as expected
3. **Cheating Protection**: When the server receives text, exclusion words, and a word count from the client, it verifies that the text and exclusion words that it previously gave a client.
4. **Stateless/Idempotent**: Remove as much "state" as possible from the server. Any new request to the server does not depend on the state of a previous request.

