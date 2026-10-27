
# Ex.No:3 Design an android application Send SMS using Intent.


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
Developed by: JAYANI N
Registeration Number : 212224100025
*/


## activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText
        android:id="@+id/phoneNumber"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter phone number"
        android:inputType="phone" />

    <EditText
        android:id="@+id/message"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter message"
        android:inputType="textMultiLine"
        android:minLines="3"
        android:gravity="top" />

    <Button
        android:id="@+id/sendButton"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Send SMS" />

</LinearLayout>


## MainActivity.java

package com.example.smsintent;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText phoneNumber, message;
    Button sendButton;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        phoneNumber = findViewById(R.id.phoneNumber);
        message = findViewById(R.id.message);
        sendButton = findViewById(R.id.sendButton);

        sendButton.setOnClickListener(v -> {

            String phone = phoneNumber.getText().toString().trim();
            String text = message.getText().toString();

            if (phone.isEmpty() || text.trim().isEmpty()) {
                Toast.makeText(this,
                        "Enter phone number and message",
                        Toast.LENGTH_SHORT).show();
            } else {
                Intent intent = new Intent(Intent.ACTION_SENDTO);
                intent.setData(Uri.parse("smsto:" + Uri.encode(phone)));
                intent.putExtra("sms_body", text);

                startActivity(intent);
            }
        });
    }
}


```

## OUTPUT

<img width="1092" height="843" alt="image" src="https://github.com/user-attachments/assets/61405034-e359-42dc-8599-b1748fdff45b" />
<img width="1380" height="952" alt="image" src="https://github.com/user-attachments/assets/f5af51fc-765d-460e-be16-b203f8e2f6ca" />


<img width="180" height="417" alt="image" src="https://github.com/user-attachments/assets/24112d00-3475-41ef-8479-cbb54c794e7d" />
<img width="183" height="415" alt="image" src="https://github.com/user-attachments/assets/70b1f2ea-e38a-4f59-bf81-85a65b474054" />
<img width="187" height="413" alt="image" src="https://github.com/user-attachments/assets/3c5bf587-279e-4a76-a9e1-66b994c1912b" />



## RESULT
Thus a Simple Android Application create and design an android application Send SMS using Intent using Android Studio is developed and executed successfully.
