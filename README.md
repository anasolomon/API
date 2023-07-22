 - [Endpoints-Paths-Parameters-Auth](#Endpoints,-Paths,-Parameters-and-Authentication)
    - [Endpoints](#endpoint)
    - [Paths and Parameters](#Paths-and-Parameters)
    - [Complex API](#complex-api)
    - [Postman](#postman)
- [API with Express.js](#API-with-Express.js)



**API** stands for **Application Programming Interfaces**. The general definition is that API is ***a set of commands, functions, protocols, and objects that programmers can use to create software or interact with an external system***. You can view it as a *contract between the data provider and the developer*, the data provider gives a set of instructions on how to access certain pieces of information that they hold, through methods/objects/protocols.   
*Facebook*'s friends is an API used to interact with an external system (their server database), for example *Tinder* uses it to show what friends you have in common. So is the *Open Weather* API.  
## Endpoints, Paths, Parameters and Authentication  
When it comes to API we need to focus on 4 main concepts: **Endpoints, Paths, Parameters and Authentication.**  

### Endpoint  
Every API that **interacts** with an **external system**, like a server, will have an ***endpoint***. Let's take this *Kanye West* quote generator API for example: https://kanye.rest/  
Their website hosts a **database** of Kanye West quotes and we can access their data by using their API,  and the endpoint of this API is https://api.kanye.rest . If we were to paste the Endpoint into our browser then we would make a **GET request** to the Kanye Rest server and they send back a piece of data, in this case a random quote.   
### Paths and Parameters  
Let's try something a little bit more complex so we can understand how Paths and Parameters work.  
The Joke API https://sv443.net/jokeapi/v2/ , their **endpoint** being https://v2.jokeapi.dev/joke technically.... because if you paste this into the browser you will get an error from their side saying "*no matching jokes found for this category*" because to fully complete the endpoint we must provide what type of joke we want to see (*Any/Programming/Miscellaneous/Dark*), this way we complete the path. Eg: https://v2.jokeapi.dev/joke/Programming this way we choose the programming **branch** from the root which is just https://v2.jokeapi.dev/joke. If we wanted a more specific joke that contains the word "*debugging*" which is something the creators of Joke API couldn't of have planned ahead then we can do so by specifing it at the end of the path, this is called a **Parameter** and they usually go at the end of an URL eg: https://v2.jokeapi.dev/joke/Programming?contains=debugging (also called a **custom query**).  
In their documentation we can also see that we are allowed to blacklist certain specific topics like "nsfw" "religious" "racist" "sexist", these are also called queries and will go at the end of the URL. I'm also going to specify that I want a one part joke. We should get something like this: https://v2.jokeapi.dev/joke/Programming?blacklistFlags=nsfw&type=single&contains=debugging , we need the symbols in the URL in order to specify a parameter. The parameters come after the question mark. "contains=debugging" is called a **key value pair** with an equal sign in between. And if you want to have more than one parameter then you separate each of the key value pairs with an **ampersand symbol**.  

### Complex API  
Let's take *Openweathermap*, a more complex API that allows developers to **build** better web applications.  
If you have an account on their web page you can generate your own **key value** which is used for the "`appid`" key. This is made in order to check how many requests you are making per minute, so if you're a big organization they can monitize from you. Here is their [documentation](https://openweathermap.org/current).  
An example of a request's pathing would be "`api.openweathermap.org/data/3.0/weather?q={city name}&appid={your api key}`" so
"`api.openweathermap.org/data/3.0/weather?q=Paris&appid=635823c4bbb4444c36f1aee94f5a7e75`"  if you want to specify the viewing of temperature in metric units you can add it to the **pathing**: "`api.openweathermap.org/data/3.0/weather?q=Paris&appid=635823c4bbb4444c36f1aee94f5a7e75&units=metric`". The order of where we add a key value pair does not matter as long as it's after the ampersand &.  

### Postman  
So often, in order to not make any typos and test an API more efficiently we can use something like *'Postman'*.  
It *memorizes all of the key value pairs* for us and renders the response, which is in a **json format**, that we get from the website's into a nice readable format to the human eye. 
 - We just need to put in Postman the **API's endpoint**, for eg the *Openweathermap*'s is "`api.openweathermap.org/data/3.0/weather`"  
 - then we write down all the key value pairs, after that we just have to click which ones we want to add to this Endpoint, making it a very easy user interface to use.  
- After we're done adding all our key value pairs and click on "*send*" then we get a nicely formatted json file easy to read.  
 
When a user types in **our website's address** it's called a **GET request** towards our server, them trying to get our website's *html/css/js* into their browser. But if some of our data relies on another server then in turn our server will make a GET request to that other **external server**, we do this through the API thanks to the menus that each of them provide in their documentations that allows us to access their data. 

### API with Express.js
To see how to implement API with node.js/express.js go see my [Express.js notes](https://github.com/anasolomon/express.js)

