# 從零開始 Cordova FCM & Badge (2019-12)

實際操作後，真心覺得 Cordova FCM 一堆坑

## 環境需求 & 涉及領域

* Java Development Kit (JDK)
* Gradle
* Android Studio (Android SDK)
* Node.js (NPM)
* Cordova
* Firebase

## 建置環境

[Requirements and Support](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#requirements-and-support)

|cordova-android Version|Supported Android API-Levels|Equivalent Android Version|
|-----------------------|----------------------------|--------------------------|
|8.X.X                  |19 - 28                     |4.4 - 9.0.0               |
|7.X.X                  |19 - 27                     |4.4 - 8.1                 |
|6.X.X                  |16 - 26                     |4.1 - 8.0.0               |
|5.X.X                  |14 - 23                     |4.0 - 6.0.1               |
|4.1.X                  |14 - 22                     |4.0 - 5.1                 |
|4.0.X                  |10 - 22                     |2.3.3 - 5.1               |
|3.7.X                  |10 - 21                     |2.3.3 - 5.0.2             |

[Installing the Requirements](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#installing-the-requirements)

### 安裝[Java Development Kit (JDK)](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

我沒用到Java但是Android要用所以...

為了在 Build APK 時不踩坑，這裡要注意別裝最新的JDK，因為cordova-android最高版本只有支援到 Java SE 8。

### 安裝[Gradle](https://gradle.org/install/)

Open a second File Explorer window and go to the directory where the Gradle distribution was downloaded. Double-click the ZIP archive to expose the content. Drag the content folder `gradle-6.0.1` to your newly created `C:\Gradle` folder.

意思整個壓縮包裡的`gradle-6.0.1`資料夾就是解壓縮到`C:\Gradle`下就好。

### 安裝[Android Studio (Android SDK)](https://developer.android.com/studio/index.html)

#### Adding SDK Packages

After installing the Android SDK, you must also install the packages for whatever API level you wish to target. It is recommended that you install the highest SDK version that your version of cordova-android supports (see Requirements and Support).

Open the Android SDK Manager (`Tools > SDK Manager` in Android Studio, or `sdkmanager` on the command line), and make sure the following are installed:

1. Android Platform SDK for your targeted version of Android
2. Android SDK build-tools version 19.1.0 or higher
3. Android Support Repository (found under the "SDK Tools" tab)

### [環境變數](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html#setting-environment-variables)

1. `JAVA_HOME`->`C:\Program Files\Java\jdk1.8.0_231`
2. `PATH`->`%JAVA_HOME%\bin`
3. `Path`->`C:\Gradle\gradle-6.0.1\bin`
4. `ANDROID_HOME`->`C:\Users\<使用者>\AppData\Local\Android\Sdk`
5. `PATH`->`%ANDROID_HOME%\tools`
6. `PATH`->`%ANDROID_HOME%\tools/bin`
7. `PATH`->`%ANDROID_HOME%\platform-tools`

```bash
$ java -version
java version "1.8.0_231"
Java(TM) SE Runtime Environment (build 1.8.0_231-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.231-b11, mixed mode)

$ gradle -v
------------------------------------------------------------
Gradle 6.0.1
------------------------------------------------------------
```

## 安裝[Node.js](https://nodejs.org/zh-tw/)

直接裝

## 安裝[Cordova](https://cordova.apache.org/)

```bash
npm install -g cordova
```

### 第一個Android App

```bash
cordova create hello com.example.hello HelloWorld
cd hello
cordova platform add android  #新增Android平台
```

#### 檢查平台環境需求

```bash
$ cordova requirements
Requirements check results for android:
Java JDK: installed .
Android SDK: installed
Android target: installed android-19,android-21,android-22,android-23,Google Inc.:Google APIs:19,Google Inc.:Google APIs (x86 System Image):19,Google Inc.:Google APIs:23
Gradle: installed
```

#### 安裝FCM外掛

使用外掛 [cordova-plugin-fcm-with-dependecy-updated](https://www.npmjs.com/package/cordova-plugin-fcm-with-dependecy-updated) (不是舊版cordova-plugin-fcm)

先在 `專案根目錄` 放置 Firebase Android 應用程式 `google-services.json` 再執行以下指令

```bash
cordova plugin add cordova-plugin-fcm-with-dependecy-updated
```

外掛將會自動將所有環境設置完畢，只需直接在Javascript使用就可以。

#### 執行

```bash
cordova run android
cordova emulate android
```

由裝置直接執行

```bash
cordova run android --device
```

#### 封裝

```bash
cordova build
cordova build android
```
