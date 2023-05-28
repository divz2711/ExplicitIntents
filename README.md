# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
step1:Create the first activity with a layout that includes an EditText for number input and a Button for the Factorial action.

step2:Implement an OnClickListener for the Factorial button that retrieves the number from the EditText, calculates its factorial, and creates an Intent to open the second activity.

step3:Pass the calculated factorial value as an extra data in the Intent.

step4:In the second activity, retrieve the factorial value from the Intent using getIntent().getIntExtra() method.

step5:Update the layout of the second activity to display the factorial value.

step6:Declare the second activity in the AndroidManifest.xml file.

step7:Build and run the application to test the functionality of both screens.

## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by:Divya S
Registeration Number :212221040042
*/
```

## activity_main.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical"
    android:padding="20dp">

    <EditText android:id="@+id/etNumber"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="@string/Enter_the_number"
        android:inputType="number"
        android:layout_marginTop="50dp"
        android:importantForAutofill="no" />

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="factorial"
        android:onClick="displayFactorial" />

</LinearLayout>
```

## activity_main2.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity2"
    android:padding="20dp">

    <TextView android:id="@+id/tv"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:text="@string/factorial_of_number_is"
        style="@style/TextAppearance.AppCompat.Large"/>



</RelativeLayout>
```

## MainActivity.java:
```
package com.example.ieapp;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    EditText etNumber;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        etNumber=findViewById(R.id.etNumber);

    }
    public void displayFactorial(View view){
        Intent i = new Intent(MainActivity.this,MainActivity2.class);
        i.putExtra("number",etNumber.getText().toString());
        startActivity(i);
    }
}
```



## MainActivity2.java:
```
package com.example.ieapp;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.widget.TextView;

public class MainActivity2 extends AppCompatActivity {
    TextView tv;

    @SuppressLint("SetTextI18n")
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
        Bundle b=getIntent().getExtras();
        int no= Integer.parseInt(b.getString("number"));
        long f=1;
        for (int i=no;i>0;i--){
            f=f*i;
        }
        tv=findViewById(R.id.tv);
        tv.setText("Factorial of "+no+" is " +f);

    }
}
```

## OUTPUT

![2023-05-28 (8)](https://github.com/divz2711/ExplicitIntents/assets/121245222/ae1d35e7-fdd1-44d8-9372-f2fa721d5140)
![image](https://github.com/divz2711/ExplicitIntents/assets/121245222/f00d0a3d-be24-4a0d-b442-d0f0bfeab114)
![image](https://github.com/divz2711/ExplicitIntents/assets/121245222/b5a5054f-6c7d-4533-ad94-fffc3f912d6c)



## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.

