# developer-test-project
A server test project for Ares.

## Getting Started
1. Clone this repo and run npm install on your local machine.
2. You'll need to setup an instance of [MongoDB](https://www.mongodb.com/) and run it.
3. If you set up the database on anything but the local host, then you'll need to create a file in the server folder called '.env' and insert `DATABASE_URL:YOUR_DATABASE_PATH` inside.
5. Run `npm run start` to run the project, server will run and begin accepting queries.

## Node Version
This application was built with node 8.9.1. Earlier versions may work, but to guarantee functionality please download [node v8.9.1](https://nodejs.org/en/) or later.


## Data
You will need to place marker data into your own database or query the API with JSON data. Marker data needs to be in the format of
```
{
  name : STRING,
  position : {
    latitude : NUMBER,
    longitude : NUMBER,
  },
  callsign : STRING,
  mmsid : STRING,
  speed : NUMBER,
  course : NUMBER,
  heading : NUMBER
}
```

## API
The main endpoint of the API is `/api/tracks`. Use a get method to retrieve all markers in the database or a post method with JSON data to create a new marker. The endpoint expects an array of objects if you're posting data.

The other endpoint is `/api/tracks/:tracksId` which expects the database id of the marker as a parameter. Sending with a get method will return a single marker from the database if an id match is found. A delete method will delete the marker from the database and a put method will update the marker information except for the marker's mmsid.
