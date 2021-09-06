# react-firebaseui-localized

React wrapper over firebaseui package with simpler localization


## usage

```js
import FirebaseUIAuth from "react-firebaseui-localized";

import firebase from "firebase/app";
import "firebase/auth";

const firebaseApp = firebase.initializeApp(/* your firebase keys */);

const config = {
  signInFlow: "popup",
  signInSuccessUrl: "/home",
  signInOptions: [
    firebase.auth.GoogleAuthProvider.PROVIDER_ID,
    firebase.auth.FacebookAuthProvider.PROVIDER_ID,
  ],
  tosUrl: "/terms-of-service",
  privacyPolicyUrl: "/privacy-policy",
};

function Login() {
  return (
    <FirebaseUIAuth
      lang="pt_br"
      rtl // if language is rtl
      version="4.7.3"
      config={config}
      auth={firebaseApp.auth()}
      firebase={firebase} // only if there isn't a firebase instance on the window object already
    />
  );
}
```
