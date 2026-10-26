# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.youtube.com” and press navigate button it should open google page using Implicit Intents.

## NAME : SIVAHARIBALAN K
## REG : 212224220103

## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Create a new project in Android Studio.
Design the XML layout with a text field and an Implicit Intent button.
Implement an implicit Intent in MainActivity using an appropriate action and youtube website URL.
Set the Intent to open https://www.youtube.com in a web browser when the button is clicked.
Run the application and verify that clicking the button opens the youtube website.


## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: SIVAHARIBALAN K
Registeration Number : 212224220103
*/
```
## Activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="20dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Implicit Intent"
        android:textSize="28sp"
        android:textStyle="bold"
        android:layout_marginBottom="30dp"/>

    <EditText
        android:id="@+id/editUrl"
        android:layout_width="300dp"
        android:layout_height="wrap_content"
        android:hint="Enter Website URL"
        android:inputType="textUri"/>

    <Button
        android:id="@+id/btnImplicit"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Search"
        android:layout_marginTop="20dp"/>

</LinearLayout>
```
## MainActivity.java

```
package com.example.test;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    EditText editUrl;
    Button btnImplicit;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editUrl = findViewById(R.id.editUrl);
        btnImplicit = findViewById(R.id.btnImplicit);

        btnImplicit.setOnClickListener(v -> {

            String url = editUrl.getText().toString().trim();

            if (url.isEmpty()) {
                Toast.makeText(this, "Please enter a URL", Toast.LENGTH_SHORT).show();
                return;
            }

            // Add https:// if the user didn't type it
            if (!url.startsWith("http://") && !url.startsWith("https://")) {
                url = "https://" + url;
            }

            Intent intent = new Intent(Intent.ACTION_VIEW, Uri.parse(url));
            startActivity(intent);
        });
    }
}
```


## OUTPUT


<img width="1917" height="1136" alt="Screenshot 2026-10-26 091417" src="https://github.com/user-attachments/assets/5ae823e2-6444-47d9-9b60-71346f4adc6e" />

<img width="1917" height="1137" alt="Screenshot 2026-10-26 091441" src="https://github.com/user-attachments/assets/9d4d7c1b-9e5a-4be3-bc3d-7fc34fa409f0" />

<img width="1895" height="950" alt="Screenshot 2026-10-26 091500" src="https://github.com/user-attachments/assets/4b4046e8-9bf4-4ce7-b8f1-552c5b4ad571" />







## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


