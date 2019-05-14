# email_parser
Email Parser and spam classification

I require an machine learning/regex expert to build and train a model and expose it through an API for us.
The API needs to extract email signatures from emails, including email replies. It should function in EXACTLY the same way as this API here:

https://sigparser.com/developers/

**It must:**
- Split reply chains (emails)
- Find email addresses in the email body and reply chains (contacts)
- Find contact details (name, phone, job title, address) in the email signatures and reply chains (contacts)
- Find inline phone numbers where someone says “My phone number is…”
- Categorize the type of email or sender. Real sender detection (isSpammyLookingSender, isSpammyLookingEmailMessage, isSpam) - see this here: https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet/customers/sig-parser

**We don't need this:**
Provide a cleaned email body without signatures or reply chains (cleanedemailbody_plain)

We will require all source code for both training and the API. We expect you will use your own and other email inboxes as training data via GMAIL/Office 365 API
We expect you will write code to deploy it to Heroku for us (we will provide details)
<br>
**Sample Request**
{
  "subject": "string",
  "from_address": "string",
  "from_name": "string",
  "htmlbody": "string",
  "plainbody": "string",
  "date": "string",
  "options": {
    "outputCleanedEmailHtmlDepth": 1
  }
}
<br>
**Sample response**
{
    "error": "string",
    "contacts": [
      {
        "firstName": "string",
        "lastName": "string",
        "emailAddress": "string",
        "emailAddressDomain": "string",
        "emailAddressDomainWithoutTLD": "string",
        "phoneNumber": "string",
        "mobilePhone": "string",
        "voipPhone": "string",
        "officePhone": "string",
        "fax": "string",
        "address": "string",
        "title": "string",
        "twitterUrl": "string",
        "twitterHandle": "string",
        "linkedInUrl": "string",
        "linkedInHandle": "string",
        "companyName": "string",
        "website": "string"
      }
    ],
    "isSpammyLookingEmailMessage": true,
    "isSpammyLookingSender": true,
    "isSpam": true,
    "from_LastName": "string",
    "from_FirstName": "string",
    "from_Fax": "string",
    "from_Phone": "string",
    "from_Address": "string",
    "from_Title": "string",
    "from_MobilePhone": "string",
    "from_OfficePhone": "string",
    "from_LinkedInUrl": "string",
    "from_TwitterUrl": "string",
    "from_TwitterHandle": "string",
    "from_EmailAddress": "string",
    "emails": [
      {
        "from_EmailAddress": "string",
        "from_Name": "string",
        "textBody": "string",
        "htmlLines": [
          "string"
        ],
        "date": "2019-05-05T22:27:56.124Z",
        "didParseCorrectly": true,
        "to": [
          {
            "name": "string",
            "emailAddress": "string"
          }
        ],
        "cc": [
          {
            "name": "string",
            "emailAddress": "string"
          }
        ],
        "htmlBody": "string",
        "spammyLookingEmail": true,
        "subject": "string",
        "cleanedBodyHtml": "string",
        "cleanedBodyPlain": "string"
      }
    ],
    "from_LinkedInHandle": "string",
    "duration": 0,
    "cleanedemailbody": "string",
    "cleanedemailbody_ishtml": true,
    "cleanedemailbody_plain": "string",
    "from_CompanyName": "string",
    "from_Website": "string",
    "from_EmailAddressDomain": "string",
    "from_EmailAddressDomainWithoutTLD": "string"
  }
