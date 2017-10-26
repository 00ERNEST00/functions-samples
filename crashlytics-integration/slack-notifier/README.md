# Crashlytics Slack Notifier

Identify important conversion workflows in your app, so that when a new issue is reported in that workflow via Crashlytics, a slack notification will be sent to a specific channel on Slack. This will allow you to react quicker to crashes that impact important conversion workflows of your app.

Crashlytics will become the future crash reporter for Firebase. Learn more about Crashlytics [here](https://fabric.io/kits/android/crashlytics/summary?ref=fb).

## Setting up the sample

 Create and setup the Firebase project:
  1. Create a Firebase project using the [Firebase Developer Console](https://console.firebase.google.com).
  1. Enable Billing on your Firebase the project by switching to the **Blaze** plan, this is currently needed to be able to perform HTTP requests to external services from a Cloud Function.

 Create and setup Crashlytics in your app:
  1. Create an account on [Fabric](https://fabric.io/kits?show_signup=true).
  1. Setup Crashlytics for your app as described in the [Crashlytics setup instructions](https://fabric.io/kits/android/crashlytics)

 Configuring the sample
  1. Clone or download this repo and open the `crashlytics-integration/slack-notifier` directory.
  1. You must have the Firebase CLI installed. If you don't have it install it with `npm install -g firebase-tools` and then configure it with `firebase login`.
  1. Configure the CLI locally by using `firebase use --add` and select your project in the list.
  1. Install `npm` dependencies in the functions directory locally, by running: `cd functions; npm install;`
  1. Configure the Firebase CLI to set your Fabric Project ID `firebase functions:config:set fabric.project_id="<YOUR_FABRIC_PROJECT_ID>"`
      1. How do I find my Fabric Project ID? Go into App Settings in your Fabric Dashboard and select the app you would like to use. The URL will contain your Fabric Project Id: `https://fabric.io/settings/apps/<YOUR_FABRIC_PROJECT_ID>`
  
 Setting up an Incoming Slack Webhook
  1. Set up an [incoming webhook integration](https://my.slack.com/services/new/incoming-webhook/) in your Slack team. Take note of the **Webhook URL**.
  1. Config and set the environment variable for the webhook URL: `firebase functions:config:set slack.webhook_url="https://hooks.slack.com/services/...` 
   
## Deploy and test

 1. Deploy your project using `firebase deploy`
 1. Simulate a test crash. [Android Instructions](https://docs.fabric.io/android/crashlytics/test-crash.html) | [iOS Instructions](https://docs.fabric.io/apple/crashlytics/test-crash.html)


## Contributing

We'd love that you contribute to the project. Before doing so please read our [Contributor guide](../CONTRIBUTING.md).


## License

© Google, 2017. Licensed under an [Apache-2](../LICENSE) license.
