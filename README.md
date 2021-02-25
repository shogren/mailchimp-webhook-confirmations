# Mailchimp Subscribe/Unsubscribe 

This file will accept a Mailchimp webhook, log the event to a text file, and send a follow up email using Mandrill.

### Set Up

If you don't have one already, sign up for a Mandrill account and get set up to send: [Quick Start Guide](https://mailchimp.com/developer/transactional/guides/quick-start/)

Then install the [Mandrill PHP client library](https://github.com/mailchimp/mailchimp-transactional-php) in your project:

`composer require mailchimp/transactional
`

### Edits to the mc_webhook file

Make sure to update the path to point to the autoload file:

`require_once('/path/to/mailchimp-transactional-php/vendor/autoload.php');
`

Add your API key here:

`        $mailchimp->setApiKey('YOUR_API_KEY');
`

Update the 'From Email' and 'From Name' in both the $subscribe and $unsubscribe variables:

`"from_email" => "YOUR_FROM_EMAIL",
`

`"from_name" => "YOUR_FROM_NAME",
`


### In your Mailchimp Account

Visit the Audience Dashboard, choose a list, then choose 'Settings' and 'Webhooks'.

Click 'Create Webhook' and add your URL.

To test, add a subscriber to the list and wait for a confirmation email to arrive to that address.

Check your Mandrill API logs to see if the API call is making successfully making it to your Mandrill account.
