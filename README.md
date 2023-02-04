<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Test-Application-Design](#test-application-design)
  - [Authors](#authors)
- [Problem description](#problem-description)
- [Task](#task)
- [User Stories](#user-stories)
- [Use Case](#use-case)
- [High-level Design Architecture](#high-level-design-architecture)
- [Screen Flow Design](#screen-flow-design)
- [Screen Behavior](#screen-behavior)
- [ERD](#erd)
- [API](#api)
  - [API Flowchart](#api-flowchart)
  - [API Definition](#api-definition)
  - [Endpoint: /users/register](#endpoint-usersregister)
    - [Method: POST](#method-post)
    - [Description:](#description)
    - [Request Body:](#request-body)
    - [Security:](#security)
    - [Responses:](#responses)
  - [Endpoint: /users/login](#endpoint-userslogin)
    - [Method: POST](#method-post-1)
      - [Description:](#description-1)
      - [Request Body:](#request-body-1)
      - [Security:](#security-1)
      - [Response:](#response)
  - [Endpoint: /debts](#endpoint-debts)
    - [Method: GET](#method-get)
    - [Description:](#description-2)
      - [Security:](#security-2)
      - [Response:](#response-1)
  - [Endpoint: /loans](#endpoint-loans)
    - [Method: POST](#method-post-2)
    - [Description:](#description-3)
      - [Request Body:](#request-body-2)
      - [Security:](#security-3)
      - [Response:](#response-2)
  - [Endpoint: /loans/result](#endpoint-loansresult)
    - [Method: GET](#method-get-1)
    - [Description:](#description-4)
      - [Request Query:](#request-query)
      - [Security:](#security-4)
      - [Response:](#response-3)
  - [Endpoint: /loans/check](#endpoint-loanscheck)
    - [Method: GET](#method-get-2)
    - [Description:](#description-5)
      - [Request Query:](#request-query-1)
      - [Security:](#security-5)
      - [Response:](#response-4)
  - [Endpoint: /loans/{loan_id}](#endpoint-loansloan_id)
    - [Method: GET](#method-get-3)
      - [Description:](#description-6)
      - [Request Parameters:](#request-parameters)
      - [Security:](#security-6)
      - [Response:](#response-5)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Test-Application-Design
Test Application Design PT. XYZ 

## Authors

* **Hermanus Wibisono**  - [wibidong](https://github.com/wibidong)

# Problem description

PT. XYZ is a fintech company that wants to develop their mobile apps, in an effort to reach a wider user base they want to develop an online loan application.
Potential High Level User Story:

1. User performs registration with data directory, email, phone number, and uploads a photo along with the ID card
2. User can log in with a password or biometric (if available on their mobile device)
3. User can view the remaining debt and monthly bills that must be paid (if any)
4. User can borrow up to Rp. 12,000,000 with a maximum tenure of 1 year.
5. During the loan application process, the result will be accepted or rejected
6. If the loan is accepted, there will be a notification via email and registered phone number
7. User cannot take out a loan if there is an ongoing loan application and has not been settled.

# Task
1. Create a high-level design architecture for this mobile app project.
2. Specify the Screen Flow and ERD designs for the project you want to create.
3. Create detailed API design using design tools such as UML, ERD, flowchart, etc.
4. Create a detailed screen behavior design for the mobile app based on the screen flow above.

# User Stories
1. As a potential user, I want to be able to register for the mobile app so I can start using the online loan services.
2. As a registered user, I want to be able to log in to the app either with a password or biometric for convenience and security.
3. As a logged in user, I want to be able to view my remaining debt and monthly bills so I can keep track of my financial status.
4. As a logged in user, I want to be able to apply for a loan up to Rp. 12,000,000 with a maximum tenure of 1 year.
5. As a loan applicant, I want to be notified via email and phone if my loan application is accepted or rejected.
6. As a loan borrower, I want to be unable to apply for another loan if I still have an ongoing loan that has not been settled.
7. As a loan borrower, I want to be able to see the amount of loan I have borrowed and the amount I still need to pay.

# Use Case
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7OsnZSCm303xd-8pWCK-bGDeX2n0KuHCGA84aOJNZvFgYWFkTdDS7htzFKIfHU5OxVzqd_O4M7YbAdx64SQBXZgh9neTBZca3AtmPlFjDMSJGfUXMsQJgj1H5FAWwAp-CrcmBknmfpP2upI_svsrtFm0)

The User (U) has the ability to perform the following actions:

Register: This allows the user to create an account in the system.
Log In: The user logs in to the system using their email and password.
View Loan Status: The user can view the current status of their loan application.
Apply for Loan: The user can submit a loan application by entering their loan details.
Receive Loan Approval: The user will receive a notification about the result of their loan application, whether it's approved or rejected.

On the other hand, the Loan Application (LA) system has the following functionalities:

Store User Data: The system stores the user's personal information and loan details.
Authenticate User: The system verifies the user's identity before granting access to the system.
Calculate Loan Eligibility: The system assesses the user's eligibility to receive a loan based on the information provided by the user.
Notify User: The system sends a notification to the user about the result of their loan application.

# High-level Design Architecture
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7OwnZSCm303xd-9_09dzLmxW4R80JH4I0OaIA39UFuchA-wAsvUZUVJsyoTABJA7jT_gFjS_WE6r5V4QPoms6kgilj7eSCafUMY19ozFZpcR4BeCJGSlAGeTHU4O59tLRtC85iCELKfDZL_SKhxRX4PLdCd3U9lVcPqrV_W6)

User Interface: This package includes the screens and interfaces that the users interact with, such as the user registration screen, login screen, loan status screen, loan application screen, and loan notification screen.

Business Logic: This package includes the core functionalities of the loan application system. It includes the user authentication, loan processing, loan approval or denial, loan notification management, and loan status management. It communicates with the other packages to provide an integrated system.

Data Storage: This package includes the storage systems for user and loan data.

Security: This package includes the security measures of the system, such as user authentication, data encryption, and secure communication.

Communication: This package includes the communication methods for sending notifications to users, such as push notifications, SMS notifications, and email notifications.

Integration: This package includes the integration of the loan application system with other systems, such as mobile device biometric authentication, banking systems for loan processing, and third-party libraries for encryption and security.

# Screen Flow Design
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7Ox13S8m303_J043jFxpAbBL1M01DxLIIuaTERQoFfJNdNIVMxgZUTHoUx2a4WU5bVlftleJm73CcVsCFJfPKd4IdvDM6BppePBXGzsdLsk54pghJ2jrpW8LMM3L59N4_sLbp8OLtic8P2iwO6F1SjdSheM5vFZn2m00)

# Screen Behavior
1. Start Screen:
User is presented with the start screen of the loan management mobile app.
2. Welcome Screen:
User is welcomed to the app and given the option to either register or login if they are a registered user.
3. Register Screen:
- If the user is not a registered user, they can click on the "Register" button and be redirected to the Register Screen.
- User enters their personal information, email, phone number, and uploads a photo.
- User clicks on the "Register" button to complete the registration process.
4. Verification:
User's information is verified by the system.
5. Verification Successful:
If verification is successful, the user is redirected to the Login Screen.
6. Login Screen:
User enters their email and password or uses biometric authentication.
7. System Login Check:
- System checks if the user credentials are correct.
- If the credentials are incorrect, the system displays an error message and the user cannot proceed to the Home Screen.
- If the credentials are correct, the system logs the user in and redirects them to the Home Screen.
8. Home Screen:
User is now on the Home Screen of the app where they can view their loan information, apply for a loan, and view the status of their loan application.
9. View Loan Information:
User clicks on the "View Loan Information" button to view their current loan details.
10. Loan Information:
User is presented with information about their loan, including the loan amount borrowed, loan amount remaining, and loan tenure.
11. Apply for Loan:
User clicks on the "Apply for Loan" button to apply for a new loan.
12. Loan Application Form:
User enters the loan amount they would like to apply for.
13. Loan Amount Check:
- System checks if the loan amount entered is greater than 12.000.000.
- If the loan amount is greater than 12.000.000, the system displays an error message and the user cannot proceed with the application.
14. Select Tenure:
User selects the loan tenure.
15. Tenure Check:
- System checks if the loan tenure selected is greater than 1 year.
- If the loan tenure is greater than 1 year, the system displays an error message and the user cannot proceed with the application.
16. Review Information:
User reviews the information they have entered in the loan application form.
17. Submit Loan Application:
User submits the loan application.
18. View Loan Status:
User clicks on the "View Loan Status" button to view the status of their loan application.
19. Loan Status Check:
- System checks if the loan status is ongoing.
- If the loan status is ongoing, the system displays an error message and the user cannot apply for another loan.
20. Loan Eligibility Check:
- System checks if the user is eligible for the loan they have applied for.
- If the user is not eligible, the system displays an error message and the loan application is rejected.
21. System Review:
System reviews the loan application.
22. Loan Application Result:
User is presented with the result of their loan application, either approved or rejected.
23. Loan Approval:
If the loan application is approved, the user is notified via email and phone.
24. Loan Disbursement:
If the loan application is approved, the loan amount is disbursed to the borrower's account.
25. Loan Repayment:
The borrower then repays the loan according to the terms agreed upon in the loan application process.
26. End:
The loan management process is complete, and the user can view their loan information at any time through the mobile app.

# ERD
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7Ssv3SCm343HFbCa0rZiKpc0HiW2j4J812HAu06ldwFwnI_URexgCVhjmL9wL0hjzzDzsHD0yKgD_OmZZBHCSH9FPGwu-E0wfS6RpBVNMfqBEa_PCXatWO4ia6U9GUB_ancRuW3IcjPFt4dgjny0)

User Entity
| Column Name      | Data Type | Key Type   | Description                                            |
|------------------|-----------|-----------|--------------------------------------------------------|
| User_ID          | Number    | Generated | Unique identifier for the user                         |
| Name             | Text      | Required  | Name of the user                                       |
| Email            | Text      | Required  | Email address of the user                              |
| Phone            | Text      | Required  | Phone number of the user                               |
| Address          | Text      | Optional  | Address of the user                                    |
| Profile_Picture  | Text      | Optional  | Profile picture of the user                            |
| KTP              | Text      | Optional  | KTP number of the user                                 |
| Password         | Text      | Required  | Password of the user                                   |

Loan Entity
| Column Name                 | Data Type | Key Type   | Description                                            |
|----------------------------|-----------|-----------|--------------------------------------------------------|
| Loan_ID                   | Number    | Generated | Unique identifier for the loan                         |
| User_ID                  | Number    | Foreign Key| User who applied for the loan                           |
| Loan_Amount              | Number    | Optional  | Loan amount applied for                                 |
| Loan_Tenor               | Number    | Optional  | Loan tenor in months                                   |
| Loan_Status              | Text      | Optional  | Status of the loan                                     |
| Loan_Repayment_Schedule  | Text      | Optional  | Repayment schedule for the loan                        |

Payment Entity
| Column Name      | Data Type | Key Type   | Description                                            |
|------------------|-----------|-----------|--------------------------------------------------------|
| Payment_ID       | Number    | Generated | Unique identifier for the payment                      |
| Loan_ID          | Number    | Foreign Key| Loan associated with the payment                       |
| Payment_Amount   | Number    | Optional  | Amount paid for the loan                               |
| Payment_Date     | Date      | Optional  | Date of the payment                                    |
| Payment_Status   | Text      | Optional  | Status of the payment                                  |

Notification Entity
| Column Name                | Data Type | Key Type   | Description                                            |
|----------------------------|-----------|-----------|--------------------------------------------------------|
| Notification_ID           | Number    | Generated | Unique identifier for the notification                 |
| User_ID                  | Number    | Foreign Key| User who received the notification                      |
| Notification_Type        | Text      | Optional  | Type of notification                                   |
| Notification_Message      | Text      | Optional  | Message of the notification                            |
| Notification_DateTime    | DateTime  | Optional  | Date and time of the notification                      |

Relationships:

1. A User can have multiple Loans.
2. A Loan can have multiple Payments.
3. A User can receive multiple Notifications.

# API
## API Flowchart
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7Sqz2iCm343XlQTe3v1exvH0A7Jhq0ieZd04jcHa2L-_FzCRtl0jtT4yQhdSM5A9WyBAzNHl_GvWEERCViOUdIofE8dFIIiCtlbGoV2cxjFQMk64pYhJHfspG4KMs3H59V7_sHYpOONrzPmUHKSwqNnkFtiXERxz0000)

## API Definition
## Endpoint: /users/register
### Method: POST
### Description: 
Registers a new user by accepting their personal information such as directory, email, phone number, and photo of their ID card.

### Request Body:
```json
{
  "name": "string",
  "email": "string",
  "password": "string",
  "phone": "string",
  "address": "string",
  "profile_picture": "string",
  "ktp": "string"
}
```
### Security:
- API requests must include a valid JSON Web Token (JWT) in the header to authenticate the user.
- The password must be hashed using a secure algorithm such as bcrypt before being stored in the database.
### Responses:
- 201: Created - The user was successfully registered.
- 400: Bad Request - The request body was malformed or missing required fields.
- 401: Unauthorized - The provided JWT was invalid or has expired.
- 409: Conflict - The provided email address is already in use by another user.


## Endpoint: /users/login
### Method: POST

#### Description: 
Logs in an existing user by accepting their credentials such as email and password or using biometric authentication if available on their device.

#### Request Body:
```json
{
"email": "user@example.com",
"password": "secret"
}
```

#### Security: 
This endpoint uses JSON Web Token (JWT) for authentication and authorization. The token is included in the response and should be passed in the `Authorization` header for subsequent requests to protected endpoints.

#### Response:
HTTP Status: 200 OK
```json
{
  "message": "Login Successful",
  "user": {
    "User_ID": 1,
    "Name": "John Doe",
    "Email": "johndoe@example.com",
    "Phone": "+123456789",
    "Profile_Picture": "https://example.com/profile_picture.jpeg",
    "KTP": "123456789012345678",
    "Address": "123 Main Street, New York, NY 10001"
  },
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX2lkIjoxLCJpYXQiOjE1MTYyMzkwMjJ9.8iPQQzMUbL-CnJO9Y9Nxig8vDRhKAmIq3bLixFzWtjA"
}
```
HTTP Status: 401 Unauthorized
```json
{
  "message": "Incorrect Email or Password"
}
```

## Endpoint: /debts
### Method: GET
### Description:
Returns the remaining debt and monthly bills of the logged in user.
#### Security:
This endpoint requires authentication. The JSON Web Token (JWT) should be passed in the Authorization header.

#### Response:
HTTP Status: 200 OK
```json
{
"message": "Debts retrieved successfully",
"debts": [
{
"Debt_ID": 1,
"Name": "Credit Card",
"Amount": 5000,
"Due_Date": "2022-12-31",
"Monthly_Payment": 500
},
{
"Debt_ID": 2,
"Name": "Car Loan",
"Amount": 20000,
"Due_Date": "2025-12-31",
"Monthly_Payment": 1000
}
]
}
```
HTTP Status: 401 Unauthorized
```json
{
"message": "Access Denied. Please Login First"
}
```

## Endpoint: /loans
### Method: POST
### Description:
Accepts a loan application from a logged in user, including the loan amount and tenure.

#### Request Body:
```json
{
  "loan_amount": 1000,
  "tenure": 12
}
```

#### Security:
This endpoint requires authentication. The user must provide a valid JSON Web Token (JWT) in the Authorization header to access this endpoint.

#### Response:
HTTP Status: 201 Created
```json
{
"message": "Loan application submitted successfully",
"loan_application": {
"Loan_ID": 1,
"User_ID": 1,
"Amount": 1000,
"Tenure": 12,
"Status": "Pending"
}
}
```

HTTP Status: 400 Bad Request
```json
{
"message": "Invalid request body"
}
```

HTTP Status: 401 Unauthorized
```json
{
"message": "Please provide a valid JSON Web Token in the Authorization header"
}
```

## Endpoint: /loans/result
### Method: GET
### Description:
Returns the result of a loan application, either accepted or rejected, and sends a notification via email and phone to the user.

#### Request Query:
loan_ID: The ID of the loan application to retrieve the result of.
#### Security:
This endpoint uses JSON Web Token (JWT) for authentication and authorization. The token should be passed in the Authorization header.

#### Response:
HTTP Status: 200 OK
```json
{
"message": "Loan Result",
"loan": {
"Loan_ID": 1,
"Amount": 1000,
"Tenure": 12,
"Result": "Accepted"
}
}
HTTP Status: 404 Not Found
{
"message": "Loan Result Not Found"
}
HTTP Status: 401 Unauthorized
{
"message": "Unauthorized Access"
}
```

## Endpoint: /loans/check
### Method: GET
### Description:
Checks if the user has any ongoing loan application or loan that has not been settled, and denies the loan application if necessary.

#### Request Query:
GET /loans/check?user_id=1
Where user_id is the identifier of the user making the request.

#### Security:
This endpoint uses JSON Web Token (JWT) for authentication and authorization. The token should be passed in the Authorization header with a value of Bearer <token>.

#### Response:
HTTP Status: 200 OK
```json
{
"message": "Ongoing Loan Application found",
"details": {
"Loan_ID": 1,
"Amount": 5000,
"Tenure": 12,
"Status": "Pending"
}
}
```
HTTP Status: 200 OK
```json
{
"message": "No ongoing loan application found"
}
```
HTTP Status: 401 Unauthorized
```json
{
"message": "Invalid Token"
}
```

## Endpoint: /loans/{loan_id}
### Method: GET
#### Description:
Returns the status of a specific loan, including the loan amount, remaining amount to be paid, and tenure.

#### Request Parameters:
loan_id (required, integer): The ID of the loan for which the status is requested.
#### Security:
This endpoint uses JSON Web Token (JWT) for authentication and authorization. The token must be passed in the Authorization header with the format Bearer [token] in order to access the protected endpoint.

#### Response:
HTTP Status: 200 OK
```json
{
"Loan_ID": 1,
"User_ID": 1,
"Amount": 100000,
"Remaining_Amount": 50000,
"Tenure": 12,
"Status": "Ongoing"
}
```

HTTP Status: 401 Unauthorized
```json
{
"message": "Access Denied. You must be logged in to access this endpoint."
}
```

HTTP Status: 404 Not Found
```json
{
"message": "Loan with ID 1 not found."
}
```