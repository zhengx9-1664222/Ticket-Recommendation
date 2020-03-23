# Ticket-Recommendation
This project aims to use personalization to improve ticket search and recommendation. The user need to login with their registered username and password. After they enter the page, they will be able to search nearby hot events on the website. Other than that, user can mark certain event as “favorite”, thus they can easily find those event under the favorite record page the next time they login. The interesting part in this project is that it will give user event recommendation based on their search history and favorite records.
                                                              _______________
                                                             | TicketMaster  |
                                                             | ______________|
                       __________________________________________ | | ________________
                      |                 HTTP Server(Tomcat)       | |                 |
                      |   _______________________________________ | | ______________  |
Client             ---|--|--->_____________             _________ | | __________    | |
(html,css,js)      <--|--|----| RPC        |----------> | TicketMaster Client  |    | |
                      |  |    | Handlers   |<---------- |______________________|    | |
                      |  |    | (Servlets) |----------> _______________             | |          ________________
                      |  |    |____________|<---------- | MySQL Client |------------|-|--------> | MySQL Database |
                      |  |                              |______________|<-----------|-|--------- |________________|
                      |  |__________________________________________________________| |
                      |______________________________________________________________ |                      

I built the web client using HTML, CSS and JavaScript. And for the backend, I Created Java servlets with RESTful APIs to handle HTTP requests and responses. There are mainly three servlet. The first one is a SearchItems api that provides the functionality to search around. The second servlet allows a user to set or unset their favorite records. And the last one will recommends similar events to the user. I deploy these servlets on tomcat. User can interact with web page and once they make some request, this request will be sent to Tomcat. Then Tomcat will find the correct service to handle this request and send the response back to the client. I use SQL to built relational databases to capture event data (for example, the name, description, location, parking info and etc)  from TicketMaster API.
