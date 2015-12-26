# Android-Simple-Calculator-Activity
This is an android application by which the user can easily calculate the output of the given input by using arithmetic operations.
--------------------------------------------------------------------------------------------------------------------------------------
SimpleCalculatorActivity.java
--------------------------------------------------------------------------------------------------------------------------------------

package com.felight.launch;
import android.app.Activity;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;


public class SimpleCalculatorActivity extends Activity {

    public void doCalculation(View view){

        EditText etFirstNumber = (EditText) findViewById(R.id.etFirstNumber);
        EditText etSecontNumber = (EditText) findViewById(R.id.etSecondNumber);
        TextView tvResult = (TextView) findViewById(R.id.tvResult);

        double num1 = Double.parseDouble(etFirstNumber.getText().toString());
        double num2 = Double.parseDouble(etSecontNumber.getText().toString());

       switch (view.getId()){
           case R.id.btnAdd:
               tvResult.setText(""+(num1+num2));
               break;
           case R.id.btnSub:
               tvResult.setText(""+(num1-num2));
               break;
           case R.id.btnMul:
               tvResult.setText(""+(num1*num2));
               break;
           case R.id.btnDiv:
               tvResult.setText(""+(num1/num2));
               break;

           default:

       }
    }

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.simple_calculator_layout);
    }
}
--------------------------------------------------------------------------------------------------------------------------------------
simple_calculator_layout.xml:-
--------------------------------------------------------------------------------------------------------------------------------------

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical" android:layout_width="match_parent"
    android:layout_height="match_parent">

    <EditText
        android:hint="Enter First Number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:inputType="numberDecimal"
        android:ems="10"
        android:id="@+id/etFirstNumber"
        android:layout_gravity="center_horizontal" />

    <EditText
        android:hint="Enter Second Number"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:inputType="numberDecimal"
        android:ems="10"
        android:id="@+id/etSecondNumber"
        android:layout_gravity="center_horizontal" />

    <LinearLayout
        android:gravity="center"
        android:orientation="horizontal"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal">

        <Button
            android:onClick="doCalculation"
            style="?android:attr/buttonStyleSmall"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="+"
            android:id="@+id/btnAdd" />

        <Button
            android:onClick="doCalculation"

            style="?android:attr/buttonStyleSmall"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="-"
            android:id="@+id/btnSub" />

        <Button
            android:onClick="doCalculation"

            style="?android:attr/buttonStyleSmall"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="*"
            android:id="@+id/btnMul" />

        <Button
            android:onClick="doCalculation"
            style="?android:attr/buttonStyleSmall"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="/"
            android:id="@+id/btnDiv" />
    </LinearLayout>

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="Result will be displayed here"
        android:id="@+id/tvResult"
        android:layout_gravity="center_horizontal" />
</LinearLayout>























