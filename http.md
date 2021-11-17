# Hyper Text Transfer Protocol (HTTP)

HTTP is central to how modern web applications work and how they're built. 

## Brief Overview and History

* Under your browser's hood lies a collection of files -- CSS, HTML, Javascript, videos, images, etc. -- that makes displaying the page possible. All these files were sent from a server to your browser, the client, by an application protocol called HTTP.
    * HTTP follows a simple model where a client makes a request to a server and waits for a response - a request-response protocol. HTTP is effectively a system of rules with which clients and servers must comply if they wish to communicate over them.
* HTTP was invented by Tim Berners-Lee in the 1980s

## How the Internet Works

* The internet is composed of millions of interconnected networks that allow devices and computers to communicate with each other.
* By convention, an Internet Protocol (IP) address - akin to a unique label - is applied to every device and an optional port number help distinguish one device from another.
* The IP address serves as the identifier which aids in communication across the internet.
* A Domain Name System (DNS) helps map a website's URL with its IP address. Put simply, a DNS is a distributed database (residing on a hierarchy of DNS servers) which keeps track of domain names and their corresponding IP addresses on the internet.
* A typical interaction with the Internet starts with a web browser when you:
    1. Enter a URL like http://www.google.com into your web browser's address bar.
    2. The browser creates an HTTP request, which is packaged up and sent to your device's network interface.
    3. If your device already has a record of the IP address for the domain name in its DNS cache, it will use this cached address. If the IP address isn't cached, a DNS request will be made to the Domain Name System to obtain the IP address for the domain.
    4. The packaged-up HTTP request then goes over the Internet where it is directed to the server with the matching IP address.
    5. The remote server accepts the request and sends a response over the Internet back to your network interface which hands it to your browser.
    6. Finally, the browser displays the response in the form of a web page.
* Clients and servers - The most common client is an application you interact with on a daily basis, e.g., a web browser (mobile or desktop). Clients are responsible for issuing HTTP requests and processing the HTTP response in a user-friendly manner onto your screen. Servers, on the other hand, store the content you're requesting and are capable of handling inbound requests, and their job is to issue a response back. Often, the response will content relevant data as specified in the request.
* Resources - A generic term for things you interact with on the Internet via a URL. This may include images, videos, web pages, and other files. In fact, resources can also take the form of software that lets you trade stock or play a video game.
* Statelessness - A protocol is said to be stateless if it's designed in such a way that each request/response pair is completely independent of the previous one. In the context of HTTP, this means that the server does not need to hang on to information, or state, between requests.
    * Since HTTP is inherently stateless, web developers have to work hard to simulate a stateful experience in web applications.
    * Statelessness is what HTTP so resilient, distributed, and hard to control. It's also what makes it so difficult to secure and build on top of.

## What is a URL?
* Uniform Resource Locator (URL) is akin to the address or phone number one needs in order to visit or communicate with a friend.
* A URL is the most frequently used part of a general concept of a Uniform Resource Identifier (URI), which specifies how resources are located.
### URL Components
* A URL is comprised of several components. Take http://www.example.com:88/home?item=book as an example:
    1. http: The scheme. It always comes before the colon and two forward slashes and tells the web client how to access the resource. In this case it tells the web client to use the Hypertext Transfer Protocol or HTTP to make a request. Other popular URL schemes are ftp, mailto or git. You may sometimes see this part of the URL referred to as the protocol, and there is a connection between the two things in that the scheme can indicate which protocol (or system of rules) should be used to access the resource; in the context of of a URL however, the correct term for this component is the scheme.

    2. www.example.com: The host. It tells the client where the resource is hosted or located.

    3. :88 : The port or port number. It is only required if you want to use a port other than the default.

    4. /home/: The path. It shows what local resource is being requested. This part of the URL is optional.

    5. ?item=book : The query string, which is made up of query parameters. It is used to send data to the server. This part of the URL is also optional.

* Somtimes, the URL may point to a specific resource on the host e.g., http://www.example.com/home/index.html

* Unless otherwise noted, the default port number of HTTP requests is 80.

### Query Strings/Parameters
Given a simple URL with a query string - http://www.example.com?search=ruby&results=10

| Query String Component| Description|
|-----------------------|------------|
| ?                     | A reserved character that marks the start of the query string|
| search=ruby           | A parameter name/value pair  |
| &                     | A reserved character used when adding more parameters to the query string  |
| results=10            | A parameter name/value pair  |

* Although query strings are great to pass in additional information to the server, there are some limits to their usage:
    * Query strings have a maximum length
    * Name/value pairs used in query strings are visible in the URL and thus, passing sensitive information to the server in this manner is not recommended
    * Space and special characters cannot be used with query strings. They must be URL encoded.

### URL Encoding
URLs are designed to accept only certain characters in the standard 128-character ASCII character set. Characters not in this set have to be encoded so that they are used safely. URL encoding serves this purpose of replacing these non-conforming characters with a % symbol followed by two hexadecimal digits that represent the ASCII code of the character. Only alphanumeric and special characters $-_.+!'()", and reserved characters when used for their reserved purposes can be used unencoded.

* Characters must be encoded if:
    * They have no corresponding character within the standard ASCII character set
    * The use of the character is unsafe because it may be misinterpreted or modified by some systems
    * The character is reserved for special use e.g., /, ?, @, &

## Tools
### GUI Tools
1. Paw 3 - Paid
2. Insomnia - Free
3. Postman - Free

### Command Line Tools
1. CURL - Free; pre-installed with macOS

