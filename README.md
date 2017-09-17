# Commands
```sh
react-native run-android
react-native run-ios

// Export (APK @ ./android/app/build/outputs/apk/app-release.apk):
cd android & gradlew assembleRelease
```

# ReactNative Install
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

## 2. Keytool & Signing
Generate key at C:\Program Files\Java\jdk1.8.0_141\bin (NO completar con datos en blanco). Place the key.keystore file under the android/app.
```sh
keytool -genkeypair -alias alias_name -keyalg RSA -validity 20000 -keystore H:\project\key.keystore
```
Edit/Create ~/.gradle/gradle.properties (C:/Users/you/.gradle/):
```sh
MYAPP_RELEASE_STORE_FILE=my-release-key.keystore
MYAPP_RELEASE_KEY_ALIAS=my-key-alias
MYAPP_RELEASE_STORE_PASSWORD=*****
MYAPP_RELEASE_KEY_PASSWORD=*****
```
Edit /android/app/build.gradle
```sh
...
android {
    ...
    defaultConfig { ... }
    signingConfigs {
        release {
            if (project.hasProperty('MYAPP_RELEASE_STORE_FILE')) {
                storeFile file(MYAPP_RELEASE_STORE_FILE)
                storePassword MYAPP_RELEASE_STORE_PASSWORD
                keyAlias MYAPP_RELEASE_KEY_ALIAS
                keyPassword MYAPP_RELEASE_KEY_PASSWORD
            }
        }
    }
    buildTypes {
        release {
            ...
            signingConfig signingConfigs.release
        }
    }
}
...
```

## 3. Android Export
APK @ ./android/app/build/outputs/apk/app-release.apk
```sh
cd android & gradlew assembleRelease
```

## 4. AndroidManifest.xml (android/app/src/main)
Add xmlns:tools="http://schemas.android.com/tools" to manifest tag
```sh
<uses-permission android:name="android.permission.READ_PHONE_STATE" tools:node="remove" />
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
It is impossible to use VirtualBox and Microsoft Hyper-V at the same time. Disable Hyper-V (search "Windows Features").
- <a href="https://www.virtualbox.org/">VirtualBox</a>
- <a href="http://romannurik.github.io/AndroidAssetStudio/">Android Icon Generator</a>


# Errors
- npm ERR! tar.unpack untar error
```sh
npm cache clean
```
- gradlew clean
```sh
cd android & gradlew clean & cd ..
```
- Remove Permissions (android.permission.READ_PHONE_STATE)
