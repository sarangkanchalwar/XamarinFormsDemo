# XamarinFormsDemo
Sample addition program test demo. 

## Project Details
This repository has four projects in one solution `XamarinFormsDemo.sln`
* XamarinFormsDemo (Portable)
* XamarinFormsDemo.Android
* XamarinFormsDemo.iOS
* XamarinFormsUITest

### Addition Logic Implementation
The UI for task which takes two numbers and adds them without using +, -, * or / operator is in [MainPage.xaml](https://github.com/ksarang2009/XamarinFormsDemo/blob/master/XamarinFormsDemo/XamarinFormsDemo/XamarinFormsDemo/MainPage.xaml) and code behind it is in [MainPage.xaml.cs](https://github.com/ksarang2009/XamarinFormsDemo/blob/master/XamarinFormsDemo/XamarinFormsDemo/XamarinFormsDemo/MainPage.xaml.cs) file.

### Building apk file
For preparing an apk for the android project following task for building the application for release, which mainly entails setting some application attributes.
  * Specify the Application Icon
  * Version the Application
  * Shrink the APK
  * Compile
  * Archive for Publishing
  
To achieve all the above for this project, here is a step by step guide
* In `Solution Explorer` right click on `XamarinFormsDemo.Android` project > click `Properties` > `Application Manifest`.
* Add `Application name` as XamarinFormsDemo
* Add XamarinFormsDemo.Android in `Package name`
* From the dropdown control select `Application icon`
* Add 1 as `Version number` & 1.0 as `Version name`
* To Shrink the APK size a combination of the Xamarin.Android linker, which removes unnecessary managed code, and the ProGuard tool from the Android SDK, which removes unused Java bytecode are used. The build process first uses the Xamarin.Android linker to optimize the app at the managed code (C#) level, and then it later uses ProGuard (if enabled) to optimize the APK at the Java bytecode level.
  * Click `Android Options` tab
  * Select `SDK Assemblies Only` from the `Linking` dropdown – This will only link the assemblies that are required by Xamarin.Android. Other assemblies will not be linked.
  * Check the `ProGuard` option. Proguard is an Android SDK tool that links and obfuscates Java code. ProGuard is normally used to create smaller applications by reducing the footprint of large included libraries (such as Google Play Services) in your APK. ProGuard removes unused Java bytecode, which makes the resulting app smaller.
* Check `Generate One Package (.APK) per Selected ABI` by this one APK will be created for each of the supported ABI's (one apk for this case)
* To protect the application & disable debugging select `Release` mode
* After all of the above steps are completed, the app is ready for compilation. Select `Build` > `Rebuild Solution` to verify that it builds successfully in Release mode.
* To begin the publishing process, right-click the project in `Solution Explorer` and select the `Archive` context menu item.

`Archive` launches the `Archive Manager` and begins the process of archiving the App bundle & generates apk file in `bin` > `Realease` folder.