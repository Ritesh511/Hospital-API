# Hospital API

## Overview

This project is a Hospital API designed for the doctors of a hospital assigned by the government for the testing, quarantine, and well-being of COVID-19 patients. It allows doctors to register patients, create reports based on the patients' COVID-19 status, and access patient reports.

## **Installation**

To run this application on your local machine, follow these steps:

```

**Install the dependencies:**

Navigate to the project directory and install the required packages:


``` 
cd Hospital-API
npm install

 ```

**Start the application:**

Use the following command to start the server:


```
npm run start
```

The server will start running on http://localhost:8000.

**Test the API using Postman:**

Open Postman or another API testing tool and start making requests to http://localhost:8000.


There are two types of users in this API:

* Doctors
* Patients

**Doctor Actions**

**Login/Register:**

   Doctors can log in to the system by providing a username and password. They can also register if not already in the system.

**Manage Patients:**

   When a patient visits, doctors can register the patient using their phone number. If the patient already exists, the API returns the patient's information.
   After conducting a checkup, doctors can create a report for the patient that records the patient's COVID-19 status and other details.


Patient Report Fields

**Created by Doctor:**
 The ID of the doctor creating the report.

## **Status:** 
   
   **The current COVID-19 status of the patient, which can be one of the following:**

 *  Negative
 *  Travelled-Quarantine
 *  Symptoms-Quarantine 
 *  Positive-Admit
 *  Recovered-All-Good

*Date:* The date when the report was created.

# API Routes

**Doctor Routes**

* **POST `/doctors/register`**: Register a new doctor with username and password.
* **POST  `/doctors/login`**:
Log in a doctor and return a JWT token for authentication.

**Patient Routes**

* **POST `/patients/register`**: Register a new patient using their phone number. If the patient already exists, return their information.
* **POST `/patients/:id/create_report`**: Create a new report for a specific patient, with the doctor providing the patient's COVID-19 status.
* **GET `/patients/:id/all_reports`**: Retrieve all reports for a specific patient, sorted from oldest to latest.

**Report Routes**

* **GET `/reports/:status`***: Retrieve a list of all patients' reports, filtered by a specific COVID-19 status.

# Technologies Used

Node.js: Backend framework
Express: Web framework for Node.js
MongoDB: Database for storing patients, doctors, and reports
Mongoose: ODM for MongoDB
Passport.js: For authentication using JWT (JSON Web Tokens)
JWT: For secure, stateless authentication

<h3 align="left">Languages and Tools:</h3>

<p>
<img align="left" src="https://user-images.githubusercontent.com/18380165/224741719-3887a83f-9041-49b5-b1d3-a4b636147582.png" width="120" height="100">
<img align="left" src="https://user-images.githubusercontent.com/18380165/224742317-8448ec1f-c35e-4fa3-99bf-5075da765c1a.png" width="100" height="100">
<img align="left" src="https://user-images.githubusercontent.com/18380165/224742804-66cd82b1-fedd-40a1-ad43-6cd2a7b91e46.png" width="100" height="100">
<br>
<img  src="https://user-images.githubusercontent.com/18380165/224329339-a5174b23-1a5c-4ae4-95c8-ead20a29d77e.png" width="100" height="100">
</p>


**Running Tests**

You can test the API using Postman by sending requests to the following endpoints:

* Register a doctor: **POST `/doctors/register`**
* Login a doctor and get JWT token: **POST `/doctors/login`**
* Register a patient: **POST `/patients/register`**
* Create a patient report:**POST `/patients/:id/create_report`**
* List all reports for a patient: **GET `/patients/:id/all_reports`**
* Filter reports by status: **GET `/reports/:status`**



