# redis-mongodb

This is a simple demo for MongoDB write-through caching using Redis, served from an Express server.

## Basic functionality
The Express server has two routes, a `get` route which fetches articles, and a `post` route which allows users to post articles. Simple. <br />

Then, Redis checks to see if the requested document is in the cache and if it's not, then the document is fetched from the MongoDB database.

To try this, bring the repository down to your local machine and run the following...

Make sure you have **Redis** installed...

``` bash
npm install
# or
yard add
```

Now, run the following command to check if Redis is installed correctly 
```bash 
redis-cli ping
```

You should get a response back that prints 
```bash 
> PONG
```

Then, setup a MongoDB client either via MongoDB Atlas in the cloud, NodeJS drivers, or any other way you choose to connect. <br />
Find your MongoDB connection URI string and paste it in `/config/keys.js`. <br />
```bash
 MONGO_URI: "<YOUR-MONGODB-CONNECTION-URI-HERE>"
 ```
 
 Also, you'll want to paste in your Redis uri as well. The default is `127.0.0.1:6379`. To learn more, run `redis-cli --help` in your terminal.
 ```bash
 REDIS_URI: "<YOUR-REDIS-URI-HERE>"
 ```
 
 Finally, in your terminal, run the following command to start the Express server 
 ```bash
 node app.js
 ```
 You should get a print that says
 ```bash
 > app is listening on port 3000!
 ```
 
 Now, all you have to do is go to your browser and open up `localhost:3000` and check if the server is responding back with a message that it's working fine.
 
 ## Getting & Posting Articles to the database
 
