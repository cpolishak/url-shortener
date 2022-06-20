# URL SHORTENER
A URL shortener tool built with NodeJS

## First Phase
This first stage is to have a nodeJS app that will connect with MongoDB to a local DB to save long urls as shortened versions like that of bitly. 

The url is currently shortened via npm package "generate-unique-id" which will set a unique id to the end of the base url when the server is running to make a "shortUrl". This is done with a POST request to <baseURL>/api/url/shorten with body in json format {"longUrl":"<long url here>"} and headers set to content-type: application json. Once that request is sent, if successful, the db will get a document with the following values (_id, urlCode, longUrl, shortUrl, date). The shortUrl can then be copied and pasted in the browser (while the app is running) and this will automatically redirect to the full (longUrl) url. 

## Next Steps
- Add front-end for users to go to, enter long urls, and get a response with the short url they can use. 
    - To be built with React
- Set up the app with cloud database
    - Planning to use a Mongo Atlas cluster
- Deploy the app for live usage
    - Could be hosted on github-pages
    - Link with portfolio site
- Potentially add features for tracking/analytics (similar to bitly)

# To set up and run locally

- Clone this repo
- npm install
- Install MongoDB and connect to host (mongodb://localhost:27017/)
- Run npm run start (or run "node index.js" if nodemon is not set up on your pc)
- Get long url from site of your choosing
- Make POST with instructions above from "First Phase section" of readMe (need to have postman installed first or use cURL request)
- Refresh DB to see "urlshortener" DB created and "urls" collection with document containing data
- Copy shortUrl from DB and paste in browser