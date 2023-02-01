# sensor-api

## Description

This project creates a JSON REST API for storing and querying sensor metadata. Each sensor is made up of three fields: name, tags, and location. The API exposes endpoints for the following:

          * Storing name, location, and tags for each sensor
          * Retrieving metadata for each sensor by name
          * Updating a sensor's metadata
          * Querying to find the sensor nearest to a given location
          
[This project was created in Go and made use of the Gin Web Framework.](https://github.com/gin-gonic/gin)

## Install, Build, and Run Locally

[To download Go.](https://go.dev/doc/install)

To check if go is installed:
`go version`

To install `gin`:
`go get -u github.com/gin-gonic/gin`

To run:
`go run main.go`

## HTTP Methods

To GET all sensors:
`curl http://localhost:8080/sensors`

To GET a specific sensor by name:
`curl http://localhost:8080/sensors/name/NAME`

To POST a sensor:
`curl -X POST -H "Content-Type: application/json" -d '{"name": "NAME", "tag": ["TAG1"], "location": LOCATION}' http://localhost:8080/sensors`

To PATCH a sensor:
`curl -X PATCH -H "Content-Type: application/json" -d '{"name": "NAME", "tag": ["TAG1", "TAG2"], "location": LOCATION}' http://localhost:8080/sensors/NAME`

To GET a sensor by closest location:
`curl -X GET -d '{"x": X, "y": Y}' http://localhost:8080/sensors/location`

To DELETE a sensor by name:
`curl -X DELETE http://localhost:8080/sensors/NAME`

## Further Development

The API is in working condition with all implemented endpoints functioning properly. The next steps are to include additional tests and input validation. In addition, some of the code can be rewritten for efficiency. Specifically, more complex data structures can be implemented to decrease the time complexity of some functions. Finally, the API can be connected to a frontend and database for complete functional use.