## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
1. Protocol - A specific set of communications rules.
2. Domain - A server that can be accessed with a specific set of rules.
3. Path - defines the location of a file or folder in a computer/server's system.
4. Query String - Modifies the request to get more specific information
5. Port - A number that indicates what type of protocol a server is using to access the internet.
6. Anchor tag - allows user to jump to a specific point on the page.
```

* Name the pieces of the following urls:

```
	* `https://  === protocol
    www.google.com/` === domain

	* `https:// === protocol
  workbook.galvanize.com === domain
  /cohorts/41/learning_experiences/367` === path

  * `http:// === protocol
  locahost:5000 === domain
  /animals/puppies? === path
  onlycute=1&size=medium#firstpuppy` === query string

  * `https:// === protocol
  en.wikipedia.org === domain
  /wiki/List_of_HTTP_status_codes === path
  #4xx_Client_Error` === anchor tag
```

* Can a server use more than 1 port?

```
Yes
```

* Why is https different than http?

```
HTTPS encrypts the data before sending it.
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
Identifies the user only wants puppies named fido, max, and moxie.
Creates JSON data structure on the server.
```


```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```

__HTTP Request/Response__

* Name at least 4 http verbs

```
GET, POST, PUT, DELETE
```

* What is each verb useful for in your own words

```
GET - Simply gets a resource from the server. 
POST - Used when the client wants to send the server some new information. POST requests are not typically idempotent.
PUT - updates info on the server that already exists. PUT requests are usually idempotent.
DELETE - deletes something from the server.
```

* What does idempotent mean?

```
Does not change the state of something.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
Status codes are ment for the computer to know what happened.
1xx - Keep going, everything is ok.
2xx - Ok. You got what you want in some form.
3xx - You have to go somewhere else to get what you want. Redirects user.
4xx - Client side error. Server is ok.
5xx - Server side error.
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
That site has been permanetly moved to https://www.google.com/ and redirects the user to https://www.google.com/
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:

```
	* Accept - requests
	* Content-type - both
	* User-agent - request
	* Set-cookies - response
	* Cache-control - both
	* Cookie - request
```

* Is the following a http request or response?  How do you know for each?

```
Response
```


```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
Request
```


```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

__JSON__

* Describe what JSON is.  What is it used for.

```
Javascript Object Notation - A data-exchange fromat of the web.
```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```
var obj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');
console.log(obj.age)
```

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```

```
var myObj = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"} ]}');
myObj.Companies.forEach(function(companyObj) { 
    console.log(companyObj.company)
});
--Changed to forEach since we are only console.logging the company names. 
--We don't need to return anything. Map always needs to return an Array of the same length as the input.
```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```

```
console.log(JSON.stringify(myObj))
```


__MISC__

* Describe what DNS is.

```
Domain Name Service - Servers that look up IP addresses and convert them to a readable URL.
```

* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
-v Verbose - useful for debugging and finding out what's going on "under the hood."

-x Proxy - The proxy string can be specified with a protocol.
```

* What is TCP/IP?  How does it interact with HTTP?

```
Transmission Control Protocol - Makes sure data gets to/from a server quickly and reliably. If things fail, TCP resends data.
Internet Protocol - Makes sure packets get to the correct place. Similar to a physical address.
HTTP uses TCP/IP to send data.
```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No, TCP is resposible.
```
