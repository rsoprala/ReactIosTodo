# ReactIosTodo

Install this app on multiple devices. When any user adds or updates a task, the change will reflect on all devices

## Setup
```
	npm install -g react-native-cli
	brew update && brew upgrade
	brew install watchman
	react-native init ReactIosTodo && cd ReactIosTodo
	open ios/ReactIosTodo.xcodeproj/
	npm install firebase --save
### issues
	// firebase was not working with error Invalid directory /Users/node_modules/firebase not found
	watchman watch-del-all
	rm -rf $TMPDIR/react-packager-*
	//delete node_modules and downgrade npm
	sudo npm install -g npm@2 

```

## Running code
- select simulator in xcode and run. Edit index.ios.js in sublime and reload simulator.

## running code on device
- in ios/ReactIosTodo/AppDelegate.m change localhost to IP address, connect the device, select device in xcode and run. Let xcode codesign the app to be run on your device. Note: On your device you have to go to General->DeviceManagement and trust the developer installing the app on the device. Now the app should run and connect to the dev server on the machine
- you can shake the device to reload or debug in chrome (see this video - https://egghead.io/lessons/react-react-native-debugging-on-an-ios-device)
- if everything is running as expected. You can finally run as standalone (w/o the dev server). Go back to AppDelegate.m and enable option-2
```
//run this is root dir
react-native bundle --entry-file index.ios.js --bundle-output ios/main.jsbundle
```
- run using xcode once, then disconnect the device and run the app.

## Demo
![alt tag] (https://github.com/rsoprala/ReactIosTodo/blob/master/demo.png)

## References
** Special thanks to Simon for this article - https://devdactic.com/react-native-firebase-todo/ **
