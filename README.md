# carbot
proyecto final 
ActivityMain

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context="com.codinginflow.multipleonclicklistenerexample.MainActivity">

    <Button

        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="avanzar"/>

    <Button

        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="retroceder"/>

    <Button

        android:id="@+id/button3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="DERECHA"/>
    <Button

        android:id="@+id/button4"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="IZQUIERDA"/>
    <Button

        android:id="@+id/button5"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="STOP"/>

</LinearLayout>









MainActivity

package com.example.carboot;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import com.google.firebase.database.DatabaseReference;
import com.google.firebase.database.FirebaseDatabase;

public class MainActivity extends AppCompatActivity  {


    private Button avanzar,retroceder,izquierda,derecha,stop;

    private DatabaseReference basedato;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        avanzar =(Button) findViewById(R.id.button1);
        retroceder =(Button) findViewById(R.id.button2);
        derecha =(Button) findViewById(R.id.button3);
        izquierda =(Button) findViewById(R.id.button4);
        stop =(Button) findViewById(R.id.button5);


        basedato = FirebaseDatabase.getInstance().getReference();


        avanzar.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
if (avanzar==avanzar) {
           basedato.child("avanzar").setValue("true");
           basedato.child("retroceder").setValue("0");
           basedato.child("izquierda").setValue("0");
           basedato.child("derecha").setValue("0");
           basedato.child("stop").setValue("0");

}
            }
        });


        retroceder.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

if (retroceder==retroceder){
    basedato.child("avanzar").setValue("0");
    basedato.child("retroceder").setValue("true");
    basedato.child("izquierda").setValue("0");
    basedato.child("derecha").setValue("0");
    basedato.child("stop").setValue("0");

}

            }
        });

        derecha.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                if (derecha==derecha){

                    basedato.child("avanzar").setValue("0");
                    basedato.child("retroceder").setValue("0");
                    basedato.child("izquierda").setValue("0");
                    basedato.child("derecha").setValue("true");
                    basedato.child("stop").setValue("0");

                }

            }
        });


        izquierda.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {


                if (izquierda==izquierda){

                    basedato.child("avanzar").setValue("0");
                    basedato.child("retroceder").setValue("0");
                    basedato.child("izquierda").setValue("true");
                    basedato.child("derecha").setValue("0");
                    basedato.child("stop").setValue("0");
                }

            }
        });



        stop.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

             if (stop==stop){

                 basedato.child("avanzar").setValue("0");
                 basedato.child("retroceder").setValue("0");
                 basedato.child("izquierda").setValue("0");
                 basedato.child("derecha").setValue("0");
                 basedato.child("stop").setValue("0");
             }



            }
        });







    }




}
