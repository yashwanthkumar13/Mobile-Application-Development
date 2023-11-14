# Ex.No:1 To create a HelloWorld Activity using all lifecycles methods to display messages.


## AIM:

To create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
```

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as HelloWorld and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Display message give in MainActivity file.

Step 7: Save and run the application.
```

## PROGRAM:
```
/*
Program to print the text “Hello World”.
Developed by:YASHWANTH KUAMR S
Registeration Number :212221040185
*/
```
## activity_main.xml :
```
<?xml version="1.0" encoding="utf-8"?>

<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    
    xmlns:app="http://schemas.android.com/apk/res-auto"
    
    xmlns:tools="http://schemas.android.com/tools"
    
    android:layout_width="match_parent"
    
    android:layout_height="match_parent"
    
    android:rotationX="8"
    
    tools:context=".MainActivity">

    <TextView
    
        android:id="@+id/textView"
        
        android:layout_width="271dp"
        
        android:layout_height="54dp"
        
        android:layout_marginStart="156dp"
        
        android:layout_marginEnd="176dp"
        
        android:text="HELLO WORLD"
        
        android:textSize="40dp"
        
        app:layout_constraintEnd_toEndOf="parent"
        
        app:layout_constraintHorizontal_bias="0.491"
        
        app:layout_constraintStart_toStartOf="parent"
        
        tools:layout_editor_absoluteY="312dp" />


</androidx.constraintlayout.widget.ConstraintLayout>
```

## MainActivity.java :
```
package com.example.androidlifecycle;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;

import android.os.Bundle;

import android.widget.Toast;

public class MainActivity extends AppCompatActivity

{

    @Override
    
    protected void onCreate(Bundle savedInstanceState)
    
    {
    
        super.onCreate(savedInstanceState);
        
        setContentView(R.layout.activity_main);
        
        Toast.makeText(getApplicationContext(), "On Create Called", Toast.LENGTH_SHORT).show();
    
    }
    
    protected void onStart()
    
    {
    
        super.onStart();
        
        Toast.makeText(getApplicationContext(), "On Start Called ", Toast.LENGTH_SHORT).show();



    }
    
    protected void onRestart()
    
    {
    
        super.onRestart();
        
        Toast.makeText(getApplicationContext(), "On Restart Called", Toast.LENGTH_SHORT).show();
    }
    
    
    protected void onResume()
    
    {
    
        Toast.makeText(getApplicationContext(), "On Resume Called", Toast.LENGTH_SHORT).show();
        super.onResume();
    }
    
    
    protected void onStop()
    {
    
        super.onStop();
        
        Toast.makeText(getApplicationContext(), "On Stop Called", Toast.LENGTH_SHORT).show();
    }
    
    
    protected void onPause()
    
    {
    
        super.onPause();
        
        Toast.makeText(getApplicationContext(), "On Pause Called", Toast.LENGTH_SHORT).show();
    }
    
    
    protected void onDestroy()
    
    {
    
        super.onDestroy();
        
        
        Toast.makeText(getApplicationContext(), "On Destroy Called", Toast.LENGTH_SHORT).show();
    }
    
}
```

## OUTPUT

![image](https://github.com/yashwanthkumar13/Mobile-Application-Development/assets/116741234/bf4f6efa-1c04-439f-98b9-cc7670b9c494)


![image](https://github.com/yashwanthkumar13/Mobile-Application-Development/assets/116741234/ed9c4592-840a-4505-ba00-063b00a01ccc)


![image](https://github.com/yashwanthkumar13/Mobile-Application-Development/assets/116741234/cb654d53-f76a-40ba-9cc6-3149d60d86b9)


![image](https://github.com/yashwanthkumar13/Mobile-Application-Development/assets/116741234/2c3bb003-d6b3-43ae-931a-d7b0eb185800)


![image](https://github.com/yashwanthkumar13/Mobile-Application-Development/assets/116741234/e5273d03-4167-48b7-9568-80716882835d)


![image](https://github.com/yashwanthkumar13/Mobile-Application-Development/assets/116741234/0ad0d064-0e1c-4d96-95d2-ab0b62db48fc)


## RESULT
Thus a Simple Android Application create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio is developed and executed successfully.
