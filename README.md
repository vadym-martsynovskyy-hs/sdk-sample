# sdk-sample-app

> SDK Sample app for external developers to install

## Overview

This Sample App currently only contains a sample plugin. The plugin listens for a ```'sendtoapp'``` event and opens a modal, populated with the data from the message it was activated on.

The Sample App can be hosted locally, or on Heroku or some other hosting service. The backend is a very simple NodeJS/Express app but you can swap out the backend with anything as long as you meet a few requirements. These are listed below in the "Using another solution" section.

## Getting started

### Using Heroku

1. Clone this repository.
2. Install and setup Heroku.
3. Create a Heroku app and link it to this repository.
4. ```git push heroku master``` to push this app to Heroku. Heroku should detect that this app is a Node/Express app and run your index.js file
5. Once Heroku says that it's done use ```heroku open``` and add /modal to the URL it opened in your browser. If it comes up with a blank page that has a "Show JSON Payload" button then the web server is setup correctly.


### Using another solution

Things to keep in mind:

* You need to accept POST requests on your plugin endpoint.
* You need to host the static CSS, Javascript, and icons somehow.
* Your endpoint needs to have HTTPS.

### Configuring your Hootsuite App

1. If you already have a Hootsuite developer account head over to [your Hootsuite app  directory management page](https://hootsuite.com/developers/my-apps) and create an app, and inside that app create a plugin component. For the plugin component Service URL use your endpoint for plugin.html, if you used Heroku and Node this would be "https://<heroku-app-name-here>.herokuapp.com/plugin" . Also, check off the Default Install box.
2. Install your app by going to your [Hootsuite dashboard](https://hootsuite.com/dashboard) and navigating to the app directory (puzzle piece at the bottom of the left sidebar). Your app should be under Developer, install it.
3. Test it by going to your [Hootsuite dashboard](https://hootsuite.com/dashboard), clicking the elipsis on any post and hitting Send to <your-plugin-component-name>. This should pop up a modal with some info about the post you sent to the app.

## Other things you can do with the Plugin SDK

* Use it to send a post to your own servers and manipulate/save it.
* Process the images from a post and use the [attachFileToMessage](https://app-directory.s3.amazonaws.com/docs/sdk/global.html#attachMedia) SDK function to put the processed images into the compose box.
* Compose messages using the [composeMessage](https://app-directory.s3.amazonaws.com/docs/sdk/global.html#composeMessage) SDK function based on the contents of a message that was sent to your plugin.

## Useful Links

* [App Directory SDK Reference](https://app-directory.s3.amazonaws.com/docs/sdk/index.html)