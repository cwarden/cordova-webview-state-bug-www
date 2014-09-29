CDVWebViewDelegate fails to update the webview state properly in iOS when a
page loads an iframe using javascript and does a redirect to another page using
javascript.

```
$ git clone https://github.com/greatvines/cordova-webview-state-bug-www.git
$ cordova create --copy-from=cordova-webview-state-bug-www iframe-redirect-bug
$ cd iframe-redirect-bug
$ cordova platform add ios
$ cordova run --emulator ios
```

Wait for simulator to start, and screen to say "Done".

```
$ cat platforms/ios/cordova/console.log
```

The last should be `Finished load of: file:///Users/.../www/redirect.html`.

Instead, you get `Failed to load webpage with error: The operation couldn’t be completed. (NSURLErrorDomain error -999.)`
