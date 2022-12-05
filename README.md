# cisco-meraki-connector

What can you do with it?
```
1. Add new organizations, admins, networks, devices, VLANs, and more
2. Configure thousands of networks in minutes
3. On-board and off-board new employees’ teleworker setup automatically
4. Build your own dashboard for store managers, field techs, or unique use cases
5. Checkout out the Explore section for open source projects, or browse the Marketplace for partner solutions.
```
What's New in v1
```
The Dashboard API has evolved significantly, providing hundreds of endpoints to manage your Meraki networks!
We want to do so much more. But in order for us to include many of these new features or improvements, we need to break a few things.
The focus of this major version is on Simplicity and Scale, by providing an enjoyable developer experience
The API documentation, Postman collection, and Python library will remain synced and up-to-date with improved navigation and features.
In addition, several improvements and new endpoints have been included with this major release.
```
API Documentation
```
The API Endpoint documentation and complimenting Postman Collection have a new folder structure for navigating the API.
```

Categories
```
The services are grouped into categories, providing a collection of endpoints that behave in a similar way.
CONFIGURE endpoints are for managing cloud configurations
MONITOR endpoints will return status and history informaion
LIVE TOOL endpoints will directly interact with the device
More details https://developer.cisco.com/meraki/api-latest/#!introduction/whats-new-in-v1
```

![Cisco Meraki](images/meraki.png)

```
This Connector API exposes REST API endpoints to perform any operations on Cisco Meraki v1 API in a simple, quick and intuitive fashion.
It describes various API operations, related request and response structures, and error codes.
```
## Build

To build the project binary, run
```
    go build -o main .

```

## Run locally

To run the project, simply provide env variables to supply the API key and authentication bearer token domain name.


```bash
go build -o main .
API_KEY=<API_KEY> DOMAIN_NAME=<DOMAIN_NAME> ./main
```

This will start a worker and expose the API on port `8012` on the host machine

Swagger docs is available at `https://localhost:8012/docs`

## Generating Swagger Documentation

To generate `swagger.json` and `swagger.yaml` files based on the API documentation, simple run -

```bash
go install github.com/swaggo/swag/cmd/swag@latest
swag init -g main.go --parseDependency --parseInternal
```

To generate OpenAPISpec version 3 from Swagger 2.0 specification, run -

```bash
npm i api-spec-converter
npx api-spec-converter --from=swagger_2 --to=openapi_3 --syntax=json ./docs/swagger.json > openapi.json
```
