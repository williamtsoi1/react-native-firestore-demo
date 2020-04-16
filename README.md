# react-native-firestore-demo
This is a demo app to demonstrate how Firestore can be used in React Native apps using the [React Native Firebase](https://rnfirebase.io) SDK.

The demo app is largely inspired by the [Create React Native Firebase CRUD App with Firestore](https://www.positronx.io/create-react-native-firebase-crud-app-with-firestore/) tutorial, with an added twist of some server side processing of inputs.

## What does this app do?
![screenshot][screenshot]

This is a simple guestbook app, where the user can enter his/her name, email address, phone number and a greeting message. This data is saved in Firestore.

![architecture][architecture]

When there is a write operation into Firestore, a Cloud Function is triggered, and a translation of the greeting message is obtained through the Google Translate API. This translation is written back into Cloud Firestore and this is immediately made available to the mobile app in real time.



## To run the project 
* Create a Firebase project and create a Firestore database
* Git clone 
* Create a `database/firebaseDb.js` file based from `database/firebaseDb.js.sample`
* Enter your firebase credentials into `database/firebaseDb.js`
* `npm install`
* `npm start`

## To enable Translate API functionality
* Create an "Translate Text" extension within Firebase console.
* Enter the following for input parameters for the extension:
  * Target languages for translations: `ja`
  * Collection Path: `users`
  * Input field name: `greeting`
  * Translation output field name: `translated`

[screenshot]: ./img/app-screenshot.png
[architecture]: ./img/architecture.png