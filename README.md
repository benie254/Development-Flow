# Development Flow

## Step 1. API Development

### A. Database


#### i. Creation

- First, we create a database using a database service like SQL.

#### ii. Structure

- We define models with fields that will store data.

```
model example: Asset

model field name example: asset_name

model field type example: string/character
```

### B. Data

#### i. Validation

- We define serializers, which are data validation tools.

#### i. Collection

- We define API views for data collection.

### C. Operations

#### i. Methods

- We define methods, which determine the type of action to perform on the database.
```
example methods: update, delete, view, add
```

### D. Security

#### i. Authentication

- We set up authentication for the API to protect API views & data.

### E. Exposure

#### i. Endpoints

- We define endpoints, which will enable the communication between the server and the client.
- Each endpoint is connected to an API View, which sends or retrieves data to/from the database.

### F. Testing

#### i. Endpoints

- We test each endpoint to ensure they perform the expected operations.

## Step 2. Deployment

- After all checks have passed, we deploy to a test environment or other environment.

***

# Client - Server Communication

## Part 1. HTTP Request (Client to Server)

### A. API Consumption

#### i. API Endpoint

- The client application sends a request to the server through an API endpoint (a user attempts to view, edit, add, or delete data).

#### ii. Endpoint Validation

- The server confirms if the endpoint is valid/exists.

##### ENDPOINT INVALID

- If the endpoint is not valid, the request is rejected.
- The server sends an error response to the client.

##### ENDPOINT VALID

- If the endpoint is valid, the request proceeds.

### B. Security

#### i. Credentials Validation

- The server confirms that the authentication credentials sent by the client are valid.

##### CREDENTIALS INVALID

- If the credentials are invalid, the request is rejected.
- The server sends an error response to the client.

##### CREDENTIALS VALID

- If the credentials are valid, the request proceeds.

### C. Operations

#### i. Method Validation

- The server confirms that the method used by the client in the request is valid.
- Methods perform different operations, like `update`, `delete`, `view`, and `add` data.

##### METHOD INVALID

- If the method is invalid for the given endpoint, the request is rejected.
- The server sends an error response to the client.

##### METHOD VALID

- If the method is valid for the given endpoint, the request proceeds.

### D. Requirements

#### i. Method Parameters

- Each method has a parameter, which tells the server how to handle the requested operation.

#### ii. Parameter Validation

- The server confirms that the data sent in the endpoint is valid for the endpoint's method parameters.

##### PARAMETER INVALID

- If a parameter is invalid for the method associated with the endpoint, the request is rejected.
- The server sends an error response to the client.

##### PARAMETER VALID

- If all parameters are valid for the method associated with the endpoint, the request proceeds.

### E. Data

#### i. Data Collection

- Data received from the client is collected for processing.

#### ii. Data Validation

- The data collected is passed into a serializer, which validates it.

##### DATA INVALID

- If the data received is improperly formatted as per the specifications in the database, the request is rejected.
- The server sends an error response to the client.

##### DATA VALID

- If the data received is correctly formatted as per the specifications in the database, the request proceeds.

### F. Database

#### i. Data Fetch / Manipulation

- The client can now add/fetch data to/from the database, or manipulate it (edit, delete).

##### REQUEST FAILED

- If there is any problem with the request to add, fetch, or manipulate data, the request fails.
- The server sends an error response to the client.

##### REQUEST SUCCESSFUL

- If there is no problem with the request, the server sends a successful response to the client.

## Part 2. Response (Server to Client)

- The response from the server to the client may include data and/or a status code.

