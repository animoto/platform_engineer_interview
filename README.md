# Word Count Validator

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

1. The server should run on `localhost:8000` and serve a single path `/`
2. Please include a script `./run` to run the server

### Bonus

1. **Add Source Text**: Add an admin tool to add new sources of text to the system.
2. **Cheating Protection**: When the server receives text, exclusion words, and a word count from the client, it verifies that the text and exclusion words that it previously gave a client.
3. **Stateless/Idempotent**: Remove as much "state" as possible from the server. Any new request to the server does not depend on the state of a previous request.

