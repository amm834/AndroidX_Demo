# AndroidX_Demo
This Demo for targeting to the Android-X.

# How to make it?


1. Add 

```
com.android.support:appcompat-v7:27.+
```
libriaries to your project.
This will use from Apache Maven.

1. Open `build.gradle` and change like below

```
compileSdkVersion 27
buildToolsVersion "27.+"
```

1. Add 

```
compile ('android.arch.core:runtime:+') {
       force = true
}   
```

to your dependemcies.

**Note** If you use `AIDE apk` ,

The above is needed as there is an issue with Aide and AppCompatActivity not loading all the required libraries. This will be fixed soon hopefully


1. Go to `res/values`

Change it, from

```
<style name="AppTheme" parent="@android:style/Theme.Holo.Light">
```

to

```
<style name="AppTheme" parent="Theme.AppCompat.Light">
```

Do same as in `res/values-21`.

```javascript
lder. (Important!)

6.Just to be clear, below is what your build.gradle file should look like for a basic out of the box working Aide project using the latest supported support libraries. I hope you find this post useful.

apply plugin: 'com.android.application'

android {
compileSdkVersion 27
buildToolsVersion "27.+"

defaultConfig {
    applicationId "com.your.appname"
    minSdkVersion 14
    targetSdkVersion 28
    versionCode 1
    versionName "1.0"
}
buildTypes {
    release {
        minifyEnabled false
        proguardFiles getDefaultProguardFile('proguard-android.txt'), 'proguard-rules.pro'
    }
}
}

dependencies {

compile ('android.arch.core:runtime:+') {
       force = true
       } 

compile 'com.android.support:appcompat-v7:27.+'
compile fileTree(dir: 'libs', include: ['*.jar'])
}
```
