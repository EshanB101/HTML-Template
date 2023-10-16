# HTML-Template
How to test &amp; trigger HTML template from googlesheets

1. Open spreadsheet
2. Go to extension >> Apps Script
3. Replace current function with this:
<pre>
function sendEmail() {
  var sheet = SpreadsheetApp.getActiveSheet();
  var emailAddress = 'dummyemail@test.com'; // Replace with your test email
    var message = '';      
    var subject = 'This is the subject'; // Replace with your subject line
    var htmlBody = `
        REPLACE CONTENT INSIDE THIS TEMPLATE LITERAL WITH YOUR TEMPLATE
    `;
    MailApp.sendEmail(emailAddress, subject, message, {htmlBody:htmlBody});
}
</pre>
4. Name the file & hit save
5. Hit run & give access
6. Check email
