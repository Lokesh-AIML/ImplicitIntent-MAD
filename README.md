# Ex.No:2a Develop program to create a text field and a button “Navigate”. When you enter “www.gmail.com” and press navigate button it should open google page using Implicit Intents.


## AIM:

To create a navigate button using Implicit Intent to display the gmail page using Android Studio.

## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:

1. **Start the project:** Create a new Android project in Android Studio.

2. **Design the UI:** In `activity_main.xml`, add an `EditText` (to accept the URL input) and a `Button` (to trigger the navigation).

3. **Initialize components:** In `MainActivity.java`, map the `EditText` and `Button` variables to their respective XML IDs using `findViewById()`.

4. **Set click listener:** Attach an `OnClickListener` to the button to listen for user click events.

5. **Get input:** Inside the `onClick` method, extract the text entered in the `EditText` and convert it to a string.

6. **Create implicit intent:** Instantiate an `Intent` with the action `Intent.ACTION_VIEW` and pass the parsed URL string using `Uri.parse()`.

7. **Start activity:** Call `startActivity(intent)` to trigger the OS to open the webpage in an available web browser.

8. **Stop:** Run and test the application.


## PROGRAM:
```
/*
Program to print the text “Implicitintent”.
Developed by: Lokeshwaran S
Registeration Number : 212224240080
*/
```
MainActivity.java
```
package com.example.implicity;

import android.os.Bundle;
import android.content.Intent;
import android.net.Uri;
import android.view.View;
import android.widget.EditText;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText editText;
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        editText = findViewById(R.id.editText);
        button = findViewById(R.id.btn);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                String url = editText.getText().toString().trim();

                if (url.isEmpty()) {
                    Toast.makeText(MainActivity.this,
                            "Enter a website URL",
                            Toast.LENGTH_SHORT).show();
                    return;
                }

                if (!url.startsWith("http://")
                        && !url.startsWith("https://")) {
                    url = "https://" + url;
                }

                Intent intent = new Intent(
                        Intent.ACTION_VIEW,
                        Uri.parse(url)
                );

                startActivity(intent);
            }
        });
    }
}
```

activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editText"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:hint="Enter website URL"
        android:inputType="textUri"
        android:padding="12dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.4"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.122" />

    <Button
        android:id="@+id/btn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="368dp"
        android:onClick="search"
        android:text="Open Website"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

## OUTPUT
<img width="1366" height="720" alt="image" src="https://github.com/user-attachments/assets/f577c880-abb7-488f-b6a9-48106fdcdeab" />
<img width="1366" height="720" alt="image" src="https://github.com/user-attachments/assets/a107d94e-6e55-4615-bbf6-ee1ac4ec2752" />
<img width="1366" height="720" alt="image" src="https://github.com/user-attachments/assets/a3c599b8-cd70-4c22-964c-6d487e1c2651" />
<img width="1366" height="720" alt="image" src="https://github.com/user-attachments/assets/a16cca7f-2552-43ee-8c50-d0d6d0cdc84d" />
<img width="1366" height="720" alt="image" src="https://github.com/user-attachments/assets/c6efd6a7-9428-4248-8953-3dcd251bf3ca" />




## RESULT
Thus a Simple Android Application create a navigate button using Implicit Intent to display the gmail page using Android Studio is developed and executed successfully.


