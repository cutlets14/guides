# Hyper Text Transfer Protocol (HTTP)

HTTP is central to how modern web applications work and how they're built. 

## Brief Overview and History

* Under your browser's hood lies a collection of files -- CSS, HTML, Javascript, videos, images, etc. -- that makes displaying the page possible. All these files were sent from a server to your browser, the client, by an application protocol called HTTP.
    * HTTP follows a simple model where a client makes a request to a server and waits for a response - a request-response protocol
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
