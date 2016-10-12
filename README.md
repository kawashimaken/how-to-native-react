# how-to-native-react
react native development memo

## Tool

Atom

## upgrade react-native
react-native upgrade

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
