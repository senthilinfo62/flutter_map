# flutter_map_example

## Plugins

The plugins used in this project are:

* [google_maps_flutter](https://pub.dev/packages/google_maps_flutter)
* [geolocator](https://pub.dev/packages/geolocator)
* [flutter_polyline_points](https://pub.dev/packages/flutter_polyline_points)

## Features

* Detect the current location of the user
* Use Geocoding for converting addresses to coordinates and vice versa
* Add Markers to the Map View
* Draw the route between two places using Polylines and Directions API
* Calculate the actual distance of the route

## Usage

* Clone the repository.
  
  ```bash
  git clone https://github.com/SenthilNexware/flutter_map_example.git
  ```

* Open the project using your favorite IDE. For opening with VS Code:
  
  ```bash
  code flutter_maps
  ```

* For the **Android** part, go to `android/app/src/main/AndroidManifest.xml` file and add your **API key** here.
  
  ```xml
  <!-- Add your Google Maps API Key here -->
  <meta-data android:name="com.google.android.geo.API_KEY"
                 android:value="YOUR KEY HERE"/>
  ```

* For the **iOS** part, go to `ios/Runner/AppDelegate.swift` file and add your **API key** here.
  
  ```swift
  GMSServices.provideAPIKey("YOUR KEY HERE")
  ```
* Go to the `lib/secrets.dart` file and add your **API key** here.

<!-- > For more info regarding generating the **API key**, you can check out my article here. -->

## Full configuration (already done in this project)

You do not require to complete these configurations if you are cloning this project, as they are already done in it. But these may be helpful if you are setting up a new Flutter project for using Google Maps and location services.

### Android setup

* Navigate to the file `android/app/src/main/AndroidManifest.xml` and add the following code snippet inside the `application` tag:

   ```xml
   <!-- Add your Google Maps API Key here -->
   <meta-data android:name="com.google.android.geo.API_KEY"
                  android:value="YOUR KEY HERE"/>
   ```

* Also, you will need location access in the app. So, add the following permission in the same file inside the `manifest` tag:
  
  ```xml
  <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
  ```

### iOS setup

* Navigate to the file `ios/Runner/AppDelegate.swift` and replace the whole code with the following:

   ```swift
   import UIKit
   import Flutter
   import GoogleMaps
   
   @UIApplicationMain
   @objc class AppDelegate: FlutterAppDelegate {
     override func application(
       _ application: UIApplication,
       didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
     ) -> Bool {
       //Add your Google Maps API Key here
       GMSServices.provideAPIKey("YOUR KEY HERE")
       GeneratedPluginRegistrant.register(with: self)
       return super.application(application, didFinishLaunchingWithOptions: launchOptions)
     }
   }
   ```

* Also, add the following to `ios/Runner/Info.plist` file:
  
  ```
  <key>io.flutter.embedded_views_preview</key>
  <string>YES</string>
  ```

* For getting location permission, add the following to the same file:
  
  ```
  <key>NSLocationWhenInUseUsageDescription</key>
  <string>This app needs access to location when open.</string>
  ```

This completes the setup for both the platforms in Flutter.
