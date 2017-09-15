# ReactNative
```sh
npm install -g create-react-native-app
npm install -g react-native-cli
```

## 1. Project Start
```sh
react-native init app & cd app

react-native run-android
react-native run-ios
```

## 2. Java Keytool
Generate key at C:\Program Files\Java\jdk1.8.0_141\bin (NO completar con datos en blanco)
```sh
keytool -genkeypair -alias alias_name -keyalg RSA -validity 20000 -keystore H:\project\key.keystore
```

## 3. Android Export
APK @ ./android/app/build/outputs/apk/app-release.apk
```sh
cd android & gradlew assembleRelease
```

# Expo
Install <a href="https://expo.io/">Expo</a> on your phone
```sh
create-react-native-app app
cd app
npm start
```
Fix with local ip address:
```sh
set REACT_NATIVE_PACKAGER_HOSTNAME=192.168.1.105
npm start
```

# Components
- React Navigation: <a href="https://reactnavigation.org">https://reactnavigation.org</a>
```sh
npm install --save react-navigation
```

- React-Native Video: <a href="https://github.com/react-native-community/react-native-video">https://github.com/react-native-community/react-native-video</a>
```sh
npm install --save react-native-video
react-native link
react-native link react-native-video
```

- Uninstall Component
```sh
react-native unlink component
npm uninstall --save component
```

# Tools
- <a href="https://www.virtualbox.org/">VirtualBox</a>
```sh
java -version
```


# Errors
- npm ERR! tar.unpack untar error
```sh
npm cache clean
```
- gradlew clean
```sh
cd android & gradlew clean & cd ..
```
