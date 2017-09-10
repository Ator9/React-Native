# ReactNative
```sh
npm install -g create-react-native-app
```
## 1. Project Start
```sh
create-react-native-app app
cd app
npm start
```

## 2. Install <a href="https://expo.io/">Expo</a> on your phone
Fix with local ip address:
```sh
set REACT_NATIVE_PACKAGER_HOSTNAME=192.168.1.105
npm start
```

## 3. Java Keytool & Final Build
Generate key at C:\Program Files\Java\jdk1.8.0_141\bin (NO completar con datos en blanco)
```sh
keytool -genkeypair -alias alias_name -keyalg RSA -validity 20000 -keystore H:\project\key.keystore
```

## Components
- Uninstall Component
```sh
react-native unlink component
npm uninstall --save component
```

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

## Tools
- <a href="https://www.virtualbox.org/">VirtualBox</a>


## Errors
'react-native' is not recognized as an internal or external command, operable program or batch file.
```sh
npm install -g react-native-cli
```
