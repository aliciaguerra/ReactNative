#Networking
Many mobile apps need to load resources from a remote URL. You may want to make a POST request to a REST API, or you need
to fetch a chunk of static content from another server. 

#Using Fetch
React Native provides the fetch API for your networking needs. Fetch will seem familiar if you have used XMLHttpRequest
or other networking APIs before. You may refer to MDN's guide on using Fetch for additional information.

#Making Requests
In order to fetch content from an arbitrary URL, just pass the URL to fetch:
   
                    fetch('https://mywebsite.com/mydata.json')
                    
Fetch requires an optional second argument that allows you to customize the HTTP request. You may want to specify
additional headers, or make a POST request:

                     fetch('https://mywebsite.com/endpoint/'
                      method: 'POST',
                      headers: {
                       'Accept': 'application/json',
                      },
                      body: JSON.stringify({
                       firstParam: 'yourValue',
                       secondParam: 'yourOtherValue',
                       })
                    })
                    
#Handling the Response
The above examples show how you can make a request. In many cases, you will want to do something with the response.

Networking is an inherently asynchronous operation. Fetch methods will return a Promise that make it straightforward to
write code that works in an asynchronous matter:

                        getMoviesfromApiAsync() {
                         return fetch('http://facebook.github.io/react-native/movies.json')
                          .then((response) => response.json())
                          .then((responseJson) => {
                           return responseJson.movies;
                          })
                          
                          .catch((error) => {
                           console.error(error);
                           });
                          }
                          
You can also use the proposed ES2017 async/await syntax in a React Native app:

                          async getMoviesFromApi() {
                           try {
                            let response = await fetch('http://facebook.github.io/react-native/movies.json');
                            let responseJson = await.response.json();
                            return responseJson.movies;
                            } catch(error) {
                             console.error(error);
                              }
                            }
                            
Don't forget to catch any errors that may be thrown by fetch, otherwise they will be thrown silently. 

By default, iOS will block any request that's not encrypted using SSL. If you need to fetch from a clearText URL
(one that begins with http) you will first need to add an App Transport Security exception. If you know ahead of time
what domains you will need access to, it is more secure to add exceptions just for these domains; if the domains are
not known until runtime you can disable ATS completely.

#Using Other Networking Libraries
The XMLHttpRequest API is built into React Native. This means that you can use third party libraries such as frisbee and
axios that depend on it, or you can use the XMLHttpRequest API directly if you prefer.

                          var request = new XMLHttpRequest();
                          request.onreadystatechange = (e) => {
                           if(reuest.readyState !== 4) {
                            return;
                            }
                            
                          if(request.status == 200) {
                           console.log('success', request.responseText);
                          } else {
                           console.warn('error');
                           }
                          };
                          
                          request.open('GET', 'https://mywebsite.com/endpoint/');
                          request.send();
                          
#WebSocket
React Native also supports WebSockets, a protocol which provides full-duplex communication channels over a simple TCP
connection.

                          var ws = new WebSocket('ws://host.com/path');
                          
                          ws.onopen = () => {
                              //connection opened
                              
                              ws.send('something'); //send a message
                              };
                              
                              ws.onmessage = (e) => {
                               //a message was recieved
                               console.log(e.data);
                               };
                               
                              ws.onerror = (e) => {
                               //an error occured
                               console.log(e.message);
                               };
                               
                               ws.onclose = (e) => {
                                //connection closed
                                console.log(e.code, e.reason);
                              };
                              
Your app can now display all sorts of data and you may soon need to organize this content into several screens.                               
                              
