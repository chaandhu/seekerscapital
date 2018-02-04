# seekerscapital
seekers capital technical test

These applications were developed by integrating a number of technologies such as spring boot, Rabbit MQ, Redis, Mongo DB, html, css, jquery and canvas.js among others. 

priceapi.rar - Source code for the data consumer service that provides the API for adding new prices and to get the average of the last N prices. Listens to RabbitMQ queues for service requests and reverts back with the response on the reply queues with apprpriate routing keys thru the exchange. Stores the data in the stockprice Mongo DB repository at ds117148.mlab.com:17148/pricedb 

priceapp.rar - Source code for the web application that adds pricesand retrieves the average of the last N entries. Communicates asynchronously with the priceapi by sending the requests to the relevant RabbitMQ queues through the exchange with appropriate routing key and responses fr avergae price from the service are stored in a Redis cache and retrieved by the UI. 
Home page url is http://localhost:8098/priceapp/ , though the host, port and context can be configured as required in the application.yml of this project.

pricedataproducer.rar - Retrieves random number of prices (upto 100)  from the mongo db and shows them in a time series every second. Url is http://localhost:8198/pricedata/ , though the host, port and context can be configured as required in the application.yml of this project.


