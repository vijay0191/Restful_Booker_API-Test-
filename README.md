# Restful_Booker_API-Test
Restful Booker API – Postman Collection & Newman Setup

This repository contains a complete Postman collection for testing the Restful-Booker API, including:

Authentication (Create Token)

Get Booking IDs

Get Booking by ID

Create Booking

Update Booking (PUT)

Partial Update Booking (PATCH)

Delete Booking

The collection is structured to support both manual execution in Postman and automated execution using Newman.

🚀 About Restful-Booker API

The Restful-Booker API is a publicly available API used by QA engineers for practice.
Official site: https://restful-booker.herokuapp.com

📁 Included Files
File	Description
RestfulBooker_API_Test.postman_collection.json	Complete Postman collection with all API requests
README.md	Documentation for using the collection
(Optional) Environment File	Can be added on request
(Optional) Test Scripts	Can be added if required
📌 Features Covered
Category	Included Requests
Authentication	Create Token
Booking	GET All IDs, GET by ID
CRUD Operations	Create, Update, Partial Update, Delete
Negative Tests	Expected error responses supported
🧪 How to Use in Postman

Open Postman

Click Import

Select RestfulBooker_API_Test.postman_collection.json

Open the collection and run requests manually

(Optional) Run the entire collection using Collection Runner

📘 Sample HTTP Status Code Reference

A helpful quick table to understand possible API responses:

Status Code	Meaning	When You Get It
200 OK	Request was successful	GET booking, PUT, PATCH
201 Created	Resource successfully created	POST Create Booking
400 Bad Request	Incorrect input or malformed JSON	Wrong body format in POST/PUT/PATCH
401 Unauthorized	Invalid or missing token	Update/Delete without proper auth
403 Forbidden	Token present but no permission	Wrong token value
404 Not Found	Resource does not exist	GET/UPDATE/DELETE with invalid ID
500 Internal Server Error	Server crashed or misbehaved	Invalid server response
🧰 Running Tests with Newman

Newman allows you to run your Postman collection from the command line.

Install Newman
npm install -g newman

Run the collection
newman run RestfulBooker_API_Test.postman_collection.json

Run with environment file
newman run RestfulBooker_API_Test.postman_collection.json -e restful_env.json

📊 Generate HTML Report with Newman

Install reporter:

npm install -g newman-reporter-htmlextra


Run with HTML report:

newman run RestfulBooker_API_Test.postman_collection.json -r htmlextra \
   --reporter-htmlextra-export ./NewmanReports/RestfulBookerReport.html


The report will include:

Full test results

Response bodies

Failures grouped

Execution time

🔧 Folder Structure (Suggested)
RestfulBooker-API-Testing/
│
├── collection/
│   └── RestfulBooker_API_Test.postman_collection.json
│
├── reports/
│   └── RestfulBookerReport.html
│
├── environment/
│   └── restful_env.json (optional)
│
└── README.md

🤝 Contributing

Feel free to suggest additional test scenarios or request:

Environment variables

Pre-request scripts

Automated assertions

More negative test cases
