# Salesforce Follow-Up Automation

An automated system in Salesforce for efficiently managing customer follow-ups. This project leverages Email-to-Case, Batch Apex, Scheduled Apex, and Messaging API integration to ensure timely and personalized customer engagement.

## Features
- Automatically converts incoming emails into Case records.
- Periodically processes open cases for follow-up actions.
- Sends personalized follow-up emails based on customer engagement.
- Logs all interactions as Tasks for transparency and accountability.



Here's the Cron's expression to schdule the job

DateTime startTime = System.now().addMinutes(2);
String cronExp = '0 ' + startTime.minute() + ' ' + startTime.hour() + ' ' + startTime.day() + ' ' + startTime.month() + ' ? ' + startTime.year();
System.schedule('MyJob', cronExp, new FollowUpEmailBatch());
