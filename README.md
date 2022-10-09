# CONFIG
### Include `adb` and other android tools on your path
In `Users/hugomatilla.bash_profile` add
`export PATH=$PATH:/Users/hugomatilla/Documents/AndroidSDKs/sdk/platform-tools`
`export PATH=$PATH:/Users/hugomatilla/Documents/AndroidSDKs/sdk/tools`

### My own adb location
```js 
cd /Users/hugomatilla/Documents/AndroidSDKs/sdk/platform-tools
```

# START
```js 
adb shell
```

# SERVER
### Kill server
```js
adb kill-server
```

### Start server
```js
adb sart-server
```

# FILES
### Sends files to device 
```js
adb push <computer.file.path> /sdcard/<device.path>
```

### Retreive files from device 
```js
adb pull /sdcard/<device.path> <computer.file.path> 
```

# PACKAGES
### List all packages
```js
pm list packages
```

### Uninstall
```js
pm uninstall file.name
```

### Install
```js
pm install package.name
```

# DEVICES
### List all connected devices
```js
adb devices
```

### Clear data
```js
pm clear package.name
```

# INTENTS
[am Command](https://developer.android.com/studio/command-line/shell.html#am)
### URI
```js
am start -a android.intent.action.VIEW -d https://github.com
```

### Mime Type and and Extra string
```js
am start -a "android.intent.action.SEND" --es "android.intent.extra.TEXT" "Hello World" -t "text/plain"
```

### Activity 
```js
am start -n "your.application.packagename/path.to.the.Activity"
```

### Activity with extras
```js
am start -n "your.application.packagename/path.to.the.Activity" - e "key" "data"
```

### Service 
```js
am startservice -n "com.example.application/.BackgroundService"
```

### Broadcast with Action
```js
am broadcast -a "android.intent.action.PACKAGE_FIRST_LAUNCH" -d "com.example.application"
```

#### Notification
[stackoverflow](http://stackoverflow.com/questions/27800369/simulating-android-gcm)
```js
am broadcast -a com.google.android.c2dm.intent.RECEIVE -n <YOUR_PACKAGE_NAME>/<YOUR_RECEIVER_NAME (in the manifest)> -e "<EXTRA_KEY_1>"
"<EXTRA_VALUE_1>" -e "<EXTRA_KEY_2>" "<EXTRA_VALUE_2>"
```

# SQLITE
```js
cd data/data/<your-package-name>/databases/
```

```js
sqlite3 <your-db-name>.db
```

## Commands
### TABLES
```js
.tables
```
### SCHEMA
```js
.schema tablename
```
### QUERY
```sql
SELECT * FROM tablename;
```
### HELP  
```js
.help
```

# EMULATOR
## Allow Computer Keyboard
```js
for f in ~/.android/avd/*.avd/config.ini; do echo 'hw.keyboard=yes' >> "$f"; done
```
