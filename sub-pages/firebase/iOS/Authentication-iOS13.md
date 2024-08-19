# Swift - Firebase 


## FireBase Documentation
https://firebase.google.com/docs/ios/installation-methods?hl=en&authuser=0&_gl=1*vfzj8d*_ga*MjEyODAwODg3LjE3MjM1Mzk2ODk.*_ga_CW55HF8NVT*MTcyMzUzOTY4OC4xLjEuMTcyMzU0MDM2MS42MC4wLjA.#analytics-not-enabled



## Setup
1. Open you project in Firebase
2. Click **Authentication** and then **Get Started**
3. Pick your Auth method...e.g.: **e-mail**
4. In **Sign-in providers** enable **Email/Password**
5. In iOS App -> in **AppDelagate.swift** 
```
import Firebase
```
and in

```
func application(... didFinish...WithOptions){
    ...
    // add (Firebase plist must be implemented already)
    FirebaseApp.configure()
    
    return true

}
```


## Implement Code for new User

In appropriate controller.swift we need to import Firebase

```
import UIKit
import Firebase

if let email = emailTextField.text, let password = passwordTextField.text {

    Auth.auth().createUser(withEmail: email, password: password) { authResult, error in
        if let err = error {
            print(e.localizedDescription)
        } else {
            // Navigate to chat controller using segue
            self.performSegue(withIdentifier: "RegisterToChat", sender: self)
        }
    }
}

```

## Authorize user ( Login )

In appropriate controller.swift we need to import Firebase

```
if let email = emailTextField.text, let password = passwordTextField.text {
    Auth.auth().signIn(withEmail: email, password: password) {authResult, error in
        if let e = error {
            print(e)
        } else {
            self.performSegue(withIdentifier: "LoginToChat", sender: self)
        }
  // ...
}


}


```


## Deauthorize user (LogOut)

```
let firebaseAuth = Auth.auth()
do {
  try firebaseAuth.signOut()
  navigationController?.popToRootViewController(animated:true)
} catch let signOutError as NSError {
  print("Error signing out: %@", signOutError)
}

```







## Reference
- [firebase - create_a_password-based_account](https://firebase.google.com/docs/auth/ios/password-auth#create_a_password-based_account)
- [firebase - password-aut](https://firebase.google.com/docs/auth/ios/password-auth#swift_5)