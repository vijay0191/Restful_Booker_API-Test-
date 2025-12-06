# Restful Booker API -- Postman Collection & Newman Setup

This repository contains a complete Postman collection for testing the
Restful-Booker API, including:

-   Authentication (Create Token)
-   Get Booking IDs
-   Get Booking by ID
-   Create Booking
-   Update Booking (PUT)
-   Partial Update Booking (PATCH)
-   Delete Booking

The collection is structured to support both manual execution in Postman
and automated execution using Newman.

## About Restful-Booker API

The Restful-Booker API is a publicly available API used by QA engineers
for practice.

## Included Files

  -------------------------------------------------------------------------------------------------
  File                                             Description
  ------------------------------------------------ ------------------------------------------------
  RestfulBooker_API_Test.postman_collection.json   Complete Postman collection with all API
                                                   requests

  README.md                                        Documentation for using the collection

  Environment File (optional)                      Can be added on request

  Test Scripts (optional)                          Can be added if required
  -------------------------------------------------------------------------------------------------

## Features Covered

  Category          Included Requests
  ----------------- ----------------------------------------
  Authentication    Create Token
  Booking           GET All IDs, GET by ID
  CRUD Operations   Create, Update, Partial Update, Delete
  Negative Tests    Expected error responses

## Sample HTTP Status Code Reference

  -----------------------------------------------------------------------
  Status Code             Meaning          When You Get It
  ----------------------- ---------------- ------------------------------
  200 OK                  Request was      GET booking, PUT, PATCH
                          successful       

  201 Created             Resource         POST Create Booking
                          successfully     
                          created          

  400 Bad Request         Incorrect input  Wrong body format in
                          or malformed     POST/PUT/PATCH
                          JSON             

  401 Unauthorized        Invalid or       Update/Delete without proper
                          missing token    auth

  403 Forbidden           Token present    Wrong token value
                          but no           
                          permission       

  404 Not Found           Resource does    GET/UPDATE/DELETE with invalid
                          not exist        ID

  500 Internal Server     Server crashed   Invalid server response
  Error                   or misbehaved    
  -----------------------------------------------------------------------

## Running Tests with Newman

### Install Newman

    npm install -g newman

### Run the collection

    newman run RestfulBooker_API_Test.postman_collection.json

### Run with environment file

    newman run RestfulBooker_API_Test.postman_collection.json -e restful_env.json

## Generate HTML Report with Newman

Install reporter:

    npm install -g newman-reporter-htmlextra

Run:

    newman run RestfulBooker_API_Test.postman_collection.json -r htmlextra --reporter-htmlextra-export ./NewmanReports/RestfulBookerReport.html


