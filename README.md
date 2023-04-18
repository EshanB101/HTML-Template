# HTML-Template
How to test &amp; trigger HTML template from googlesheets

1. Open spreadsheet
2. Go to extension >> Apps Script
3. Replace current function with this:
<pre>
function sendEmail() {
  var sheet = SpreadsheetApp.getActiveSheet();
  var startRow = 1;  // First row of data to process
  var numRows = 1;   // Number of rows to process
  var dataRange = sheet.getRange(startRow, 1, numRows, 2);
  var data = dataRange.getValues();
  for (var i = 0; i < data.length; ++i) {
    var row = data[i];
    var emailAddress = 'myemail@email.com'; // Replace with your test email
    var message = 'dummy data';      
    var subject = 'This is the subject'; // Replace with your subject line
    var htmlBody = `<p>Replace this with your HTML template</p>`;
    MailApp.sendEmail(emailAddress, subject, message, {htmlBody:htmlBody});
  }
}
</pre>
4. Name the file & hit save
5. Hit run & give access
6. Check email
