# HTMLCourse

> Essential Skills to know.

Every website has two parts the Front-end and the Back-end. The front-end is the part of the site that we interact with. All of the visual aspects.

The Back-end powers the front-end it is behind the scences and is mainly about
storing data in databases and providing it to the front-end.

For this tutorial we are going to focus on the front-end aspect.

Front-end Developers use HTML, CSS, and Javascript to build front-ends.

_HTML_: Hypertext Markup Language.
This is the building blocks for our web pages.

_CSS_: Cascading Stylesheet.
Used for styling the webpages and making them look awesome.

_Javascript_: Is used for adding functionality to the webpages. Javascript is a programming language, this allows us to add functionality to sites.

CSS and HTML are not programming language instead they are the building blocks for making pages and styling them.

## Frameworks

Building websites often include a lot of repetitive task. This is where front-end frameworks and libraries come in. A framework or a library comes with a lot of code that we can reuse in our website, they help us get the job done faster.

Some of these frameworks/libraries are:

- React (library)
- Angular
- Vue

Just a heads up we do not need to learn all of these. Different companies use different frameworks for different projects. React is the most popular tool.

## Version control systems

We use version control systems to track our project historty and to work collaboratively with others. There are plenty of systems out there such as:

- Git
- SubVersion (SVN)
- Mercurial
- and more!

## How the Web Works

Important concepts that we need to know to be a web developer.

_URL_: Uniform Resource Location.
This is basically a way to locate a resource on the internet. Resources can be web pages (HTML Documents), Images, video files and etc.

Once we type in the URL and hit enter there are 2 pieces in work here. The browser also known as the client and the computer or computers that host the target website known as the server. We know this as the client server model.

The client request a service and the server provides the service. So the browser sends a message to the server to get something back.

The message is formatted in a protocol called HTTP or Hypertext Transfer Protcol. HTTP is a language that clients and servers use to talk to each other. It is a plain textual language, not a programming language.
HTTPS is HTTP with encryption so the messages exchanged between the client and the server are encrypted.

So when the server recieves this message figures out what the client is asking and then it sends a message back.

The first message is called a HTTP request and the second is called a HTTP response every exchange using the http protocol involves 2 messages.

As the browser is reading the HTML document that is returned from the server it constructs what we call the DOM or the Document Object Model. This is the model that represents the elements or objects in the HTML document. This includes all of the building blocks of the page like images, links, paragraphs and etc.

When the browser discovers references to other resources like images, fonts, and etc.
Each of the resources has its own URL or Address. So for each resource the browser sends a seperate http request to the server
to fetch these resources. Many of these request are sent in parallel so we can see the page as quickly as possible. Once the browser has the necessary resources it will render the page.

Rendering a HTML document means displaying it.

In a nutshell, the browser sends a HTTP request to the server, the server responds with a HTML document. The browser reads that document to construct the DOM and render the page.
