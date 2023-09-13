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

![image](https://github.com/Dhanush12022004/Mobile-Application-Development/assets/128135558/90a9e756-f4a7-498c-8bf6-9e2e105d39cd)


![image](https://github.com/Dhanush12022004/Mobile-Application-Development/assets/128135558/1707bc7d-8e69-4d23-b2ed-8597276ab7c7)


![image](https://github.com/Dhanush12022004/Mobile-Application-Development/assets/128135558/0c906420-00df-468a-a465-c968a793c2d4)


![image](https://github.com/Dhanush12022004/Mobile-Application-Development/assets/128135558/9073d75a-fd81-45bd-bf14-0e153b22df42)


![image](https://github.com/Dhanush12022004/Mobile-Application-Development/assets/128135558/ba4a09e5-0fbd-446d-ac68-c7931d586eba)


![image](https://github.com/Dhanush12022004/Mobile-Application-Development/assets/128135558/8ce0ba83-0229-4fbe-9778-ea578def23f4)


![image](https://github.com/Dhanush12022004/Mobile-Application-Development/assets/128135558/fa74956f-6d96-4957-bf5b-40cd46293d96)


## RESULT
Thus a Simple Android Application create a HelloWorld Activity using all lifecycles methods to display messages using Android Studio is developed and executed successfully.
