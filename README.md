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

# High-level Design Architecture
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7OwnZSCm303xd-9_09dzLmxW4R80JH4I0OaIA39UFuchA-wAsvUZUVJsyoTABJA7jT_gFjS_WE6r5V4QPoms6kgilj7eSCafUMY19ozFZpcR4BeCJGSlAGeTHU4O59tLRtC85iCELKfDZL_SKhxRX4PLdCd3U9lVcPqrV_W6)

# ERD
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7Ssv3SCm343HFbCa0rZiKpc0HiW2j4J812HAu06ldwFwnI_URexgCVhjmL9wL0hjzzDzsHD0yKgD_OmZZBHCSH9FPGwu-E0wfS6RpBVNMfqBEa_PCXatWO4ia6U9GUB_ancRuW3IcjPFt4dgjny0)

# API
## API Flowchart
![Use case diagram in PlantUML]()

## API Definition
Endpoint: /users/register
Method: POST
Description: Registers a new user by accepting their personal information such as directory, email, phone number, and photo of their ID card.

Endpoint: /users/login
Method: POST
Description: Logs in an existing user by accepting their credentials such as email and password or using biometric authentication if available on their device.

Endpoint: /debts
Method: GET
Description: Returns the remaining debt and monthly bills of the logged in user.

Endpoint: /loans
Method: POST
Description: Accepts a loan application from a logged in user, including the loan amount and tenure.

Endpoint: /loans/result
Method: GET
Description: Returns the result of a loan application, either accepted or rejected, and sends a notification via email and phone to the user.

Endpoint: /loans/check
Method: GET
Description: Checks if the user has any ongoing loan application or loan that has not been settled, and denies the loan application if necessary.

Endpoint: /loans/{loan_id}
Method: GET
Description: Returns the status of a specific loan, including the loan amount, remaining amount to be paid, and tenure.