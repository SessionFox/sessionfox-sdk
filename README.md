
# SessionFox SDK

## Native Android

SessionFox library for Android can be integrated in Android applications. The library is supported from API Level: 16, Android 4.1 (JELLY BEAN)
SessionFox SDK should be triggered at the beginning of application launch.

### Including library in Android project

1. Create a new project in Android Studio or Open an existing application project

2. In the app build.gradle, add following inside allprojects.repositories

```
allprojects{
    repositories {
        google()
        maven {
            url "https://mymavenrepo.com/repo/PENxspKoeuoFCKp9veSD/"
        }  
    }
}
```

3. In the app build.gradle, add following snippet inside dependencies
```java
implementation ('com.sessionfox:sessionfox-sdk:1.0.3-alpha@aar') {
  transitive = true
  }
```
    
4. In your Android Manifest, add the following line
```xml <meta-data android:name="SESSION_FOX_API_KEY" android:value="<your-api-key>" />```

Please replace  with app token obtained from support@sessionfox.com.

5. Extend Application class(if not already extended) and add this line to your onCreate()
```java
SessionFox.init(this);

// Tag screen name visited
SessionFox.setScreen("com.sample.CheckoutScreen");

// Send custom user meta data
SessionFox.setUser(userHashmap);

// Send custom event
SessionFox.sendEvent("purchase",purchaseDetailsHashmap);
```

=======

## React Native

### Getting started

`$ npm install sessionfox-rn --save`

### Mostly automatic installation

`$ react-native link sessionfox-rn`

### Including library in Android project

1. In the build.gradle inside your android folder, add following inside allprojects.repositories
```
allprojects {
    repositories {
        jcenter()
        google()
        maven {
            url "https://mymavenrepo.com/repo/PENxspKoeuoFCKp9veSD/"
        }
    }
}
```
Note: If your gradle version is below 3.0.0, you will have to upgrade gradle inside the above file to 3.0.0 version in your <Project>and sync project in Android Studio.

2. Add the line to your android/app/src/main/AndroidManifest.xml
``` 
<meta-data android:name="SESSION_FOX_API_KEY" android:value="<your-api-key>" />
```
Please replace with api key got from registering on the website.

3. Usage
```javascript
import SessionFoxRN from 'sessionfox-rn';

// Call the init function in your App.js render()
SessionFoxRN.init();

// Tag screen name visited
SessionFoxRN.tagScreenName('com.sample.CheckoutScreen');

// Send custom user meta data
SessionFoxRN.setUser({
  name: 'Mark',
  rollnum: '25',
});

// Send custom event
SessionFoxRN.sendEvent('purchase',{
  amount: '30',
  card: 'hdfc',
});
```
  

