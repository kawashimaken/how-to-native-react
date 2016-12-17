# how-to-react-native
react native development memo

## Tool

Atom
Sublime + babel

## upgrade react-native
```
react-native upgrade

npm install -g react-native-git-upgrade
cd MyProject
react-native-git-upgrade  //upgrade to the latest
```

see difference, press d

## after overwrite, you need to do the following

update the info.plist in order to make network access work at development mode.

Add the following to 
```
<key>your_great_domain</key>
  <dict>
    <key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
      <true/>
  </dict>
  
```
under NSAppTransportSecurity->NSExceptionDomains

## if you are using map (or any other libraries using native code.)

[https://github.com/airbnb/react-native-maps](https://github.com/airbnb/react-native-maps)

```bash
react-native link
```
（rnpm now is merged into react native core, so dont not use rnpm. see here [https://facebook.github.io/react-native/docs/linking-libraries-ios.html](https://facebook.github.io/react-native/docs/linking-libraries-ios.html)）

## logging
```bash
react-native log-ios
```


## 0.38.0  -> 0.39.0
## upgrade react-native
rename the project

```
react-native init AwesomeProject
cd AwesomeProject
react-native run-ios
```
copy
```
/app
index.ios.js
package.json
```
update the info.plist in order to make network access work at development mode.

Add the following to 
```
<key>NSAppTransportSecurity</key>
    <dict>
      <key>NSExceptionDomains</key>
      <dict>
        <key>localhost</key>
        <dict>
          <key>NSExceptionAllowsInsecureHTTPLoads</key>
          <true/>
        </dict>
        <key>yoursitedomain.com</key>
        <dict>
          <key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
          <true/>
        </dict>
      </dict>
    </dict>
  
```
then
```
npm install -g react-native-git-upgrade
cd MyProject
react-native-git-upgrade  //upgrade to the latest
npm install
react-native link
```
then
```
react-native run-ios
```
you should be fine.
