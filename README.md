
FacebookFix for iOS
======

These files are fixing the issue with the Facebook SDK sending an expired token to the server!


### Official Bug
[https://developers.facebook.com/support/bugs/194772814474841/!](https://developers.facebook.com/support/bugs/194772814474841/)

### Instructions
1) Download Facebook SDK using CocoaPods (in order to have access to source code). How to [here!](https://developers.facebook.com/docs/ios/getting-started/advanced)
2) Copy these two files over the existing ones in Pod (It will ask you to unblock pod and you need to accept it)
3) Use it like:
```
let loginManager = FBSDKLoginManager()
loginManager.authType = "reauthorize"
loginManager.logIn(withReadPermissions: permissions, from: loginViewController) { (loginResult, error) in ......
```
### Notes
Default auth_type is "rerequest". I change the request to "reauthorize" only if token is expired
