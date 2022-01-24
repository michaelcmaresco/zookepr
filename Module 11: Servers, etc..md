Module 11: Express.js

Full Stack:
    HTML5,CSS3,JavaScript,React,Git,npm,Jest,Webpack,SQLite,MySQL,MongoDB, Express, Node.js

    We will create 'Notetaker" for this week. 

        In order to succeed in this Challenge, you’ll apply the following skills:

            Configure an Express.js back end to serve static HTML files.

            Configure an Express.js back end to create an API to handle GET and POST requests.

            Parse parameters in server-side routes.

            Submit form data to a server.

            Implement separation of concerns for routing.

            Deploy a server-side application to the Heroku platform.

    You’ll prepare for the Challenge by completing this week’s online lessons, in which you’ll create a web server using the Express.js framework, add it to a front-end application, and deploy your application to Heroku.


    What we will learn

        Configure an Express.js app to handle GET and POST requests.

        Configure an Express.js app to serve static files.

        Identify how client-side requests relate to server-side responses.

        Parse optional and required parameters when creating server-side routes.

        Implement client-side POST requests to submit form data to a server.

        Implement separation of concerns for routing.

        Deploy a server-side application to the Heroku platform.

    Lesson Objectives:

        1. Set up and run a Node.js web server using Express.js

        2. Handle two t ypes of GET requests using parameters

        3. Make the application production-ready and deploy it on Heroku

            Upon completing this, we will have created our first applicatio0n that has both a front end and back end. 

                This is what distinguishes a "full stack developer" from a "front end developer"
We will be creating a Web Server!

        Here's the scenario: the local zoo has received funding to build a new online catalog, and they've asked you to create a web server for a front-end application they’re developing, called Zoo Keepr. This site’s data will be stored on the server you create. This will allow animal enthusiasts to access the data from different locations and browsers without needing to download it to their device.

        Node.js has built-in capabilities to create APIs, but Express.js makes it much easier to do so. It is also currently the industry standard, which makes it a very marketable technology to know. Let's use our well-honed research skills to learn how to use it by referring to its documentation.

    Remember learning about server-side APIs? Now we are going to create one of our own from scratch!



The zoo already gave us a front end to use.
    We will build the back end then connect it to the given front end. 
        This will allow the front end to make AJAX requests to our server, much like we've done in the past with server side API's

            The best gameplan would be to 
                Which of the following gameplans do you think is the best way to tackle this lesson?

                    1. Set up the project in GitHub. We’ll create the project’s repository in GitHub and establish the feature branches using issues.
                    2. Create an Express.js server. We’ll use a library called Express.js to create a Node-based web server.
                    3. Handle requests for animals. We’ll use Express.js to create an HTTP route that sends the requestor all of the animal data as JSON.
                    4. Deploy to Heroku. We’ll get introduced to Heroku early on for this project so that we can continuously deploy the server as we go.
                    5. Handle requests for a specific animal. We’ll create one more API route that allows us to search for one specific animal in the array.


        Before we get started though, what is Express.js? Think back to your time spent working with server-side APIs. Whenever you needed to retrieve data from an API, you would make a request to an endpoint. After a short period of time, the server would return the data to the client in the form of a response. Express.js follows a similar pattern.

        You've already created Node.js applications, but they haven't been servers. To be considered a server, a machine or program needs to provide some functionality to a client. In our case, we want that functionality to be accepting a request and sending back a response. Node.js has built-in libraries that support this functionality, but writing Node.js servers requires significantly more code than using Express.js to do the job.


                Steps: 
                    1. Create the Repo
                    2. Create GH issues
                    3. Create Branches
                    4. Create the Project Files  
                    5. Create an Express.js Server
                    6. ensure that when setting up the server, it's listening for incoming requests
                        We do this by installing Express.js with specific commands 
                        
                        ' # You can use the `-y` flag to skip the package questionnaire and leave default answers
                        npm init -y                                                             
                        
                        // the y command stands for 'yes' and it means to initialize a local npm repo with an implicit "yes" for all of the prompts, i.e., accepting all of the default settings and bypassing the interactive user prompts altogether.

                        # You can use `npm i` as a shortcut for `npm install`
                        npm i express'
                    7. Next, we work on server.js
                        Like any other npm package, we will require 'require' at the top of the file.

                    8. Setting up the server takes two steps. 
                        1. instantiate the server
                            ' const app = express();'

                        2. Tell it to listen for requests 
                            'app.listen(3001, () => {
                                console.log(`API server now on port 3001!`);
                                });     '

                                then run 'npm start' in the terminal

                                Wait a minute—what's a port? To understand ports, let's make an analogy. Imagine that a website is like a college campus. A website has an address, referred to as the host. A college campus also has an address. The host tells the client where to go, but it doesn't specify exactly where to go. Likewise, if you have the address for a college campus, you don't know exactly which building or classroom to go to. The port is like a building/classroom; it gives the exact desination on the host.

                                If you're browsing the internet, chances are you're visiting the address on one of two ports: 80 or 443. 80 is typically used for sites that begin with http://, and 443 is used for sites that begin with https://. This raises the question: Why are we using 3001 instead of 80 or 443?

                                The truth is, there's nothing wrong with running your server on 80 or 443. However, ports with numbers 1024 and under are considered special by the operating system, and often require special permissions (like running the process as an administrator). To avoid these permission restrictions, we chose to run on a port that is less restricted. In this instance, we chose 3001, but there are plenty of other ports to choose from. In fact, port numbers can range from 1024 to 49151! We chose a number around 3000 because it is common practice and fairly easy to remember.

                    9. The server is set up on port 3001 by now, lets go to the next step so we can add to it. 

                    10. Create a routine that the 'front-end' can request data from.

                            The first is that the get() method requires two arguments. The first is a string that describes the route the client will have to fetch from. The second is a callback function that will execute every time that route is accessed with a GET request.

                            The second takeaway is that we are using the send() method from the res parameter (short for response) to send the string Hello! to our client. 

                            To kill a port type 'npx kill-port ####' 

                        We then changed send to json // this means we are specifically sending JSON. 