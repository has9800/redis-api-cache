# Redis API caching

This is a simple demo for caching data from an API using Redis and an Express server.

Client side data fetching can become a huge performance bottleneck. Especially for users with high latency and low bandwith connections. Furthermore, most APIs limit the number of requests they can serve an application within a specific time frame, a process known as rate limiting.

In this project, I'm using Redis to cache data from an API on the first request, and then fetching data from the cache on every subsequent request instead of fetching directly from the API again. The project is running on an Express server.

To run this project, **Make sure you have Redis and Nodejs installed on your computer**

Once you install Redis, you can check if it's working correctly by opening your terminal and running...
```bash
redis-cli --version
# or
redis-cli ping
```

If Redis is correctly installed, you should get the version back if you ran the first command, and you should see a print out in the terminal that says `> PONG` if you ran the second command.

First bring the repository down into your local machine and run...
```bash
mkdir redis-api-cache && cd redis-api-cache

git init && git clone "<COPY-REPO-URL>" # https://github.com/has9800/redis-api-cache.git

cd redis-api-cache
```

Then, cd over to the repository and install the necessary dependencies...
```bash
npm install
# or
yarn add
```

Finally, in your terminal, run...
```bash
node app.js
```

You should see a print out in the terminal that says `App listening on port 3000`. Then, go to your browser and navigate to `localhost:3000/fish/<FISH-NAME>`. To try an example, paste `localhost:3000/fish/atlantic-cod` in the url bar. You should get back some data.

On the first line, you should see `fromCache:false` on the first request. But if you reload the page, you'll see it changes to `true` ie `fromCache:true` since the data is cached on the first request and fetched from the cache on the second request.

If you check the terminal, you won't see the print out `Request sent to the API` anymore after the first time. The data is being fetched from the cache.
