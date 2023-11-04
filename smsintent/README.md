
# Ex.No:6 Design an android application Send SMS using Intent.


## AIM:

To create and design an android application Send SMS using Intent using Android Studio.

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as smsintent and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Send SMS and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to create and design an android application Send SMS using Intent.
Developed by: YASHWANTH KUMAR S
Registeration Number : 212221040185
*/
```
## activity_main.xml:
```
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

<TextView
    android:id="@+id/textView3"
    android:layout_width="205dp"
    android:layout_height="29dp"
    android:layout_marginTop="68dp"
    android:text="Phone Number:"
    android:textSize="25dp"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />

<EditText
    android:id="@+id/phone_number_edittext"
    android:layout_width="296dp"
    android:layout_height="56dp"
    android:layout_marginTop="52dp"
    android:inputType="phone"
    android:textSize="25dp"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.494"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toBottomOf="@+id/textView3" />

<TextView
    android:id="@+id/textView4"
    android:layout_width="233dp"
    android:layout_height="32dp"
    android:layout_marginTop="72dp"
    android:text="Message:"
    android:textSize="25dp"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toBottomOf="@+id/phone_number_edittext" />

<EditText
    android:id="@+id/message_edittext"
    android:layout_width="310dp"
    android:layout_height="67dp"
    android:layout_marginTop="48dp"
    android:inputType="textMultiLine"
    android:lines="4"
    android:textSize="25dp"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toBottomOf="@+id/textView4" />

<Button
    android:id="@+id/send_button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="Send SMS"
    android:textSize="25dp"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toBottomOf="@+id/message_edittext"
    app:layout_constraintVertical_bias="0.373" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
## Main_Actvity.java:
```
package com.example.sms;

import androidx.appcompat.app.AppCompatActivity;

import androidx.core.app.ActivityCompat;

import androidx.core.content.ContextCompat;

import android.Manifest;

import android.content.Intent;

import android.content.pm.PackageManager;

import android.net.Uri;

import android.os.Bundle;

import android.view.View;

import android.widget.Button;

import android.widget.EditText;

import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

private static final int PERMISSION_REQUEST_SEND_SMS = 123;

private EditText phoneNumberEditText, messageEditText;
private Button sendButton;

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    phoneNumberEditText = findViewById(R.id.phone_number_edittext);
    messageEditText = findViewById(R.id.message_edittext);
    sendButton = findViewById(R.id.send_button);

    sendButton.setOnClickListener(new View.OnClickListener(){
        @Override
        public void onClick(View v) {
            String phoneNumber = phoneNumberEditText.getText().toString();
            String message = messageEditText.getText().toString();
            if (ContextCompat.checkSelfPermission(MainActivity.this, Manifest.permission.SEND_SMS)
                    != PackageManager.PERMISSION_GRANTED) {
                ActivityCompat.requestPermissions(MainActivity.this,
                        new String[]{Manifest.permission.SEND_SMS},
                        PERMISSION_REQUEST_SEND_SMS);
            } else {
                sendSMS(phoneNumber, message);
            }
        }
    });
}

private void sendSMS(String phoneNumber, String message) {
    Intent smsIntent = new Intent(Intent.ACTION_SENDTO);
    smsIntent.setData(Uri.parse("smsto:" + phoneNumber));
    smsIntent.putExtra("sms_body", message);

    if (smsIntent.resolveActivity(getPackageManager()) != null) {
        startActivity(smsIntent);
    } else {
        Toast.makeText(this, "No messaging app found.", Toast.LENGTH_SHORT).show();
    }
}
@Override
public void onRequestPermissionsResult(int requestCode, String[] permissions, int[] grantResults) {
    super.onRequestPermissionsResult(requestCode, permissions, grantResults);
    if (requestCode == PERMISSION_REQUEST_SEND_SMS) {
        if (grantResults.length > 0 && grantResults[0] == PackageManager.PERMISSION_GRANTED) {
            String phoneNumber = phoneNumberEditText.getText().toString();
            String message = messageEditText.getText().toString();
            sendSMS(phoneNumber, message);
        } else {
            Toast.makeText(this, "SMS permission denied.", Toast.LENGTH_SHORT).show();
        }
    }
}
}
```
## Android_Manifest.xml:
```
<manifest xmlns:android="http://schemas.android.com/apk/res/android"

xmlns:tools="http://schemas.android.com/tools">

<uses-permission android:name="android.permission.SEND_SMS" />


<application
    android:allowBackup="true"
    android:dataExtractionRules="@xml/data_extraction_rules"
    android:fullBackupContent="@xml/backup_rules"
    android:icon="@mipmap/ic_launcher"
    android:label="@string/app_name"
    android:supportsRtl="true"
    android:theme="@style/Theme.SMS"
    tools:targetApi="31">
    <activity
        android:name=".MainActivity"
        android:exported="true">
        <intent-filter>
            <action android:name="android.intent.action.MAIN" />

            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>
    </activity>
</application>
```

## OUTPUT

![AM](https://github.com/Anbuselvan04/Mobile-Application-Development/assets/119410896/a81a00ed-e342-4ffe-a82f-a60e033aeb43)
![MA](https://github.com/Anbuselvan04/Mobile-Application-Development/assets/119410896/0534b710-34df-489f-9b40-e671b807369b)
![OP1](https://github.com/Anbuselvan04/Mobile-Application-Development/assets/119410896/ffcf9cbf-3c52-43b6-b88b-2721f0e877cc)
![OP2](https://github.com/Anbuselvan04/Mobile-Application-Development/assets/119410896/f8c00f71-0589-4be4-9a41-f81eb49deaf0)

## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
