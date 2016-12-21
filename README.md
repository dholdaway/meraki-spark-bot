# Sample: Meraki Spark Bot

A sample Cisco Spark Bot using Spark, Meraki Dashboard, and Tropo API's.

The Spark Bot is tied to an AWS Lambda function that performs the fetching of information triggered by Spark messages.
The Bot posts responses back to the originating Spark room.

A Spark Webhook must be registered (see Postman collection for examples).

When triggered, the Webhook will send an HTTP POST to a configured targetUrl (example used: an AWS API Gateway endpoint).

The Lambda function extracts the Spark message id from the Webhook triggered POST. The Lambda function then does an API call back to Spark to get the text of the message (it only receives the message id initially). The text of the message is matched to "commands" mapped to different functions. The functions execute one or more API calls to gather information from the Meraki Dashboard.

Each function gathers the requested information, assembles a response into a table, and sends an API call to Spark to post the response in the originating room.

# API References

developer.ciscospark.com

developers.meraki.com

www.tropo.com
