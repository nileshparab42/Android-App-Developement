Create java and layout file for flash screen
**SplashScreen.java** 
use `MainActivity.java` code

**splash_screen.xml**
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <ImageView
        android:id="@+id/imageView"
        android:layout_width="195dp"
        android:layout_height="223dp"
        android:layout_marginTop="184dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.55"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:srcCompat="@drawable/ss_logo" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/imageView"
        android:fontFamily="@font/poppins_bold"
        android:textSize="30sp"
        android:textColor="@color/app_font"
        android:text="@string/app_name"/>
</androidx.constraintlayout.widget.ConstraintLayout>
```

Change manifest file add following code
```
<activity
    android:name=".MainActivity">
</activity>
<activity android:name=".SplashScreen"
    android:exported="true">
    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>
</activity>
```

Create intent in `SplashScreen.java`
```
new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                Intent iHome = new Intent(SplashScreen.this,MainActivity.class);
                startActivity(iHome);
            }
        },3000);
```


