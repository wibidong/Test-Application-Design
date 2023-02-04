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

# API
## API Flowchart
![Use case diagram in PlantUML](http://www.plantuml.com/plantuml/svg/7Sqz2iCm343XlQTe3v1exvH0A7Jhq0ieZd04jcHa2L-_FzCRtl0jtT4yQhdSM5A9WyBAzNHl_GvWEERCViOUdIofE8dFIIiCtlbGoV2cxjFQMk64pYhJHfspG4KMs3H59V7_sHYpOONrzPmUHKSwqNnkFtiXERxz0000)

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