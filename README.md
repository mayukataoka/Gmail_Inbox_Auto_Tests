# How to test Gmail Inbox. 
 
## Challenge 
Using the same test account to repeatedly test the same scenarios.  
For instance, how do you accurately test deleting an email repeatedly? 


## Solution 
Use GMAIL api to reset precondition as described below.  Also, since the focus of the test in Inbox only, all other email actions should be done with the GMAIL APIs.  Appium or Selenium UI test should just verify the Inbox UI only. 

## Side note
I used Gmail APIs when I automated the "Forgot Password" feature that we often see in mobile apps.  I used Gmail APIs in my mobile APPIUM framework. 


### Test case 1) :  Receiving a new email  

- Step 1 -  [Reset State to make testing repeatable ] Using the GMAIL api, delete ALL inbox emails. 
- Step 2 -  Compose an email and send it to the test account using an GMAIL api.  
https://developers.google.com/gmail/api/guides/sending

- Verification 1 - Verify on the UI that the inbox has one email. Verify the header and the body text.  


### Test case 2) :  Receiving a new email with an attachment. 

- Step 1 -  [Reset State to make testing repeatable ] Using the GMAIL api, delete ALL inbox emails. 
- Step 2 -  Compose an email and send it to the test account using an GMAIL api.  
https://developers.google.com/gmail/api/guides/sending

- Verification 1 - Verify  on the UI that the inbox has one email with an attachment.  Verify the attachment. 


### Test case 3) :  Deleting email.

- Step 1 -  [Reset State to make testing repeatable ] Using the GMAIL api, delete ALL inbox emails. 
- Step 2 -  Compose an email and send it to the test account using an GMAIL api.  
https://developers.google.com/gmail/api/guides/sending
- Step 3 - Delete the email from the UI. 

- Verification 1 - Verify the inbox has no email using an GMAIL api https://developers.google.com/gmail/api/v1/reference/users/messages/list?hl=ja
- Verification 3 - Verify on the Inbox UI that the inbox has no email. 

