# Dsc-Sign-Up-Page
activity_main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    android:background="@color/background"
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="80sp"
        android:text="Sign Up"
        android:textSize="30dp"
        android:layout_gravity="center"/>
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginStart="100dp"
        android:layout_marginLeft="100dp"
        android:layout_marginTop="20dp"
        android:hint="FullName"/>

    <EditText
        android:id="@+id/u"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:ems="10" />
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Email"
        android:layout_marginLeft="100dp"/>

    <EditText
        android:id="@+id/e"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:ems="10" />
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Password"
        android:layout_marginLeft="100dp"/>

    <EditText
        android:id="@+id/p1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:ems="10"
        android:inputType="textPassword" />
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Confirm Password"
        android:layout_marginLeft="100dp"/>

    <EditText
        android:id="@+id/p2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:ems="10"
        android:inputType="textPassword" />

    <Button
        android:id="@+id/signup"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="100dp"
        android:onClick="Signin"
        android:text="Sign Up" />
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="40dp"
        android:text="Already Registered? Sign In here"
        android:layout_gravity="center"
        android:textSize="20dp"
        android:layout_marginLeft="30dp"
        android:textColor="#3F51B5"
        android:onClick="test"/>
</LinearLayout>







#ActivityMain.java




package com.example.dscassignment;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.text.TextUtils;
import android.util.Patterns;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

   EditText userName;
   EditText email;
   EditText pass;
   EditText pass1;
   Button signin;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        userName= findViewById(R.id.u);
        email = findViewById(R.id.e);
        pass = findViewById(R.id.p1);
        pass1 = findViewById(R.id.p2);
        signin = findViewById(R.id.signup);
        signin.setOnClickListener(new View.OnClickListener(){
            @Override
            public void onClick(View view){
                checkDataEntered();
            }
        });
    }
boolean isEmail(EditText text){
    CharSequence email = text.getText().toString();
    return(!TextUtils.isEmpty(email)&& Patterns.EMAIL_ADDRESS.matcher(email).matches());
    }
    boolean isEmpty(EditText text){
        CharSequence str = text.getText().toString();
        return TextUtils.isEmpty(str);
    }
    void checkDataEntered(){
        if(isEmpty(userName)){
            Toast t =Toast.makeText(this, "You must enter username to register",Toast.LENGTH_SHORT);
            t.show();
        }





    }
}








