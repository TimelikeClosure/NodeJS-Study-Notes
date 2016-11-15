## Overview

* Does jQuery work on **NodeJS**?  Why or why not?
> jQuery does work on NodeJS as long as a window with a document exists, which can be mocked with another library such as the package "jsdom". If this is used to update the DOM in a browser through a shadow DOM, it won't be as responsive as when running on the browser directly, since there is a communication delay between server and client.


## Launching a _Node app_

* What does `npm start` do?
> `npm start` runs the terminal script spcified in the `scripts.start` property in the `packages.json` file.


## NodeJS Packages

* Create a new _Node app_.  Add a `package.json` file
* What is the purpose of the `main` key/value in the `package.json` file?
* Install at least one **package** to the _project_
* What happens if you omit `--save` when installing a **package**?
* Install at least one **package** that is specific to the dev dependencies (HINT: testing usually will be dev specific (as in development, vs deployed to the end users and ready to use))
* Remove at least one **package** from the _project_
    * Validate that `package.json` reflects the change.  If not, figure out why and try again
* Install a specific _version_ of a package to the _project_
* What directory does NPM install _local_ **packages** to?
* What happens if you install a **package** at a different directory level than the application root directory?
* How can you avoid uploading **package** files to github?  (HINT: git.ignore... but how, specifically?)
* Install a _global_ package (`Nodemon`??)
* Can a _global_ **package** be a _dependency_ to your _Node app_?  Explain why or why not?
* Launch your **NodeJS** app using the dev configuration.


## Modules

* What is the difference between URL and a file system path? Why use one for `<SCRIPT>` tags and another for `require(...)` statements?
* What is the technical difference between the `exports.<member>` pattern and the `module.exports.<member>` pattern? (HINT: [A good explanation](http://www.sitepoint.com/understanding-module-exports-exports-node-js/)).  Why would you choose one over the other?
* Create a **module** and export a few functions or variables.  Use them from another part of your _Node app_.
  * Create another **module** using a different export pattern and use it from another part of your _Node app_.  Are there any differences?
* What happens if you `require("<url>");` instead of `require(<file system path>);`?


## Processing HTTP Requests with NodeJS

* Create a basic _HTTP_ server.  Try to recall it from memory, if possible.
* When using `response.end();`, what default status code will be used?
* Does `response.end();` exit the current function?
* Create a response that returns status 404 when an invalid URL is requested
* Visit [Wikipedia HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes).  What status code should be returned when:
  * Everything is successful/OK
  * A method is used that the _Node app_ is not prepared to process
  * An invalid URL is requested
  * Something bad happened
  * Something was created
  * _Node app_ encountered an internal error
* Whey should we respond with an appropriate error for each of the GET, POST, unknown, etc. methods and also each URL within it?
* Sometimes `request.url` and `url.parse(request.url).pathName` will return the same value.  Will this always be the case?  Why or why not?
* using the _RESTful_ architecture, should we submit a _request_ BODY with a GET method?  Why or why not?
* When receiving data, will it always arrive in a single `chunk`?
  * What is the default chunk size?  How can it be changed?
* Run the serversideconcepts.demo project as-is, observe the console log and form variables.  Note that those are the parsed key/value pairs.  Modify the example to show the raw form data.  Execute again.  Observe the output.
  * [optional]  Create an AJAX request on the client that POSTs JSON data instead, observe the difference and correctly parse it into a JSON object.
* What `Content-type` indicates an image file (JPEG, or PNG, or GIF)?
* Write code that uses `response.write(content);` before writing a custom _response_ header (such as a content-type).  What happens?
  * Visit [response.write documentation](https://nodejs.org/api/http.html#http_response_write_chunk_encoding_callback) to understand why.


## Processing Files with NodeJS

* When reading a file, why does `data` have to be converted to a string?  Under what circumstances do you NOT want to convert it to a string?
* Create a response that returns an image file when the user browses to it.
* Write code that determines whether a directory exists and creates one if it does not.
