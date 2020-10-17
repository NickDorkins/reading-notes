# API's Continued
 
## 201 Class 14b - [What Google Learned From Its Quest to Build the Perfect Team](https://www.google.com/amp/mobile.nytimes.com/2016/02/28/magazine/what-google-learned-from-its-quest-to-build-the-perfect-team.amp.html)
 
Groups that have similar behavioral traits, can be a bad thing. People trying to prove themselves and ensure that their voice is heard. 
 
Leadership roles could turn into a belittling dictatorship because the leaders felt that they had to prove something.
 
Julia Rozovsky latched onto another team members idea for ‘‘case competitions,’’ contests in which participants proposed solutions to real-world business problems that were evaluated by judges, who awarded trophies and cash.
 
Rozovsky's team had a diverse background, and skill set. They competed in the "case Competitions" and started winnning, this created synergy through the team. This expeience kept the team together throught the 2 years that they were in school together.
 
Rozovsky took the data and started tracking the statistics. 
 
Through gathering these statistics, she realized that the talents of the members is not always the most important factor. For some individuals it comes dwn to the environment, if they are able to be more casual they may be more successful.
 
> Remember diversity can be the key to a teams success, as it brings various experiences to the work that you are trying to accomplish. This may cause team members to evaluate the information differently and come up with solutions that they may have otherwise overlooked.
 
---
 
## [How I explained REST to my brother](https://gist.github.com/brookr/5977550)
 
Source: https://gist.github.com/brookr/5977550
 
| Acronym | Meaning | Definition |
| --- | --- | --- |
|  **HTTP** | Hypertext Transfer Protocol | standard application-level protocol used for exchanging files on the World Wide Web. |
| **REST** | Representational State Transfer | a software architectural style that defines a set of constraints to be used for creating Web services. |
| **URL** | Uniform Resource Locator | a reference to a web resource that specifies its location on a computer network and a mechanism for retrieving it.
| **URI** | Uniform Resource Identifier | a string of characters that unambiguously identifies a particular resource. |
| **URN** | Uniform Resource Name | globally unique persistent identifiers assigned within defined namespaces so they will be available for a long period of time, even after the resource which they identify ceases to exist or becomes unavailable. |
| **API** | Application Programming Interface | a software intermediary that allows two applications to talk to each other. |
| **---** | Web Services | a collection of open protocols and standards used for exchanging data between applications or systems. | 
| **---** | Redirect |  sending a signal, data, or other information to an alternate location. |
| --- | noun / verb | Each are usually associated with a URL if you are running query's on the webpage. |
| --- | HTTP GET | systems would retrieve information from each other |
| --- | HTTP POST | system needs to add something to another system |
| --- | HTTP PUT | system wants to replace something in another system |
| --- | PATCH | system wants to do a partial update on another system |
---
 
 
## [Documentation for SuperAgent](https://visionmedia.github.io/superagent/)
 
Source: https://visionmedia.github.io/superagent/
 
**What is SuperAgent?**
 
***SuperAgent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs.***
 
> SuperAgent works with Node.js
 
## [Test documentation](https://visionmedia.github.io/superagent/docs/test.html)
 
[Moca](https://mochajs.org/)
 
## Request
 
A request can be initiated by invoking the appropriate method on the request object, then calling `.then(`) (or `.end()` or [`await`](https://visionmedia.github.io/superagent/#promise-and-generator-support)) to send the request.
 
> HTTP method may also be passed as a string
 
>`.end()` is the old way of writing callbacks, `.then()` is the most recent way of performing callbacks.
 
## Example (Old):
```
request('GET', '/search').end(function(err, res){
  if (res.ok) {}
});
```
## Example (New):
```
request('GET', '/search').then(success, failure);
```
> Absolute URLs can be used, however absolute URLs work only if the server implements [CORS](https://visionmedia.github.io/superagent/#cors)
 
- The Node client supports making requests to [Unix Domain Sockets](https://en.wikipedia.org/wiki/Unix_domain_socket)
 
By changing the method name the user can use:
- `DELETE` - (DELETE can be also called as `.del()` for compatibility with old IE where `delete` is a reserved word.)
- `HEAD`
- `PATCH`
- `POST`
- `PUT` 
 
## Setting header fields
 
Setting header fields is simple, invoke `.set()` with a field name and value
> You may also pass an object to set several fields in a single call
 
|Request Type | Explaination|
| --- | --- |
| GET | The `.query()` method accepts objects, which when used with the GET method will form a query-string. |
| HEAD | You can also use the .query() method for HEAD requests. |
| POST / PUT | Typical - set the Content-Type header field appropriately, and "write" some data. |
| --- | Default - sending strings will set the Content-Type |
| --- | Sending a FormData object is also supported |
 
## Setting the Content-Type
| Set Type | Explaination |
| --- | --- |
| .set() | The usual solution is to use the .set() method |
|  .type() | accepting the canonicalized MIME type name complete with type/subtype, or simply the extension name. |
 

Once all of the types are defined, you can use `.retry()` method, this will automatically resend requests if they fail.
 
> This method has two optional arguments: number of retries (default 1) and a callback. It calls `callback(err, res)` before each retry. The callback may return `true` / `false` to control whether the request should be retried (but the maximum number of retries is always applied)
 
| By default the following status codes are retried: | By default the following error codes are retried: |
| --- | --- |
| 408 | 'ETIMEDOUT' |
| 413 | 'ECONNRESET' |
| 429 | 'EADDRINUSE' |
| 500 |'ECONNREFUSED' |
| 502 | 'EPIPE' |
| 503 | 'ENOTFOUND' |
| 504 | 'ENETUNREACH' |
| 521 | 'EAI_AGAIN' |
| 522 | --- |
| 524 | --- |