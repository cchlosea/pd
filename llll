linear layout: 

( activity main xml )
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <androidx.appcompat.widget.Toolbar
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:title="Practice 1 - 00 Juliana"
        app:titleTextColor="@color/black"
        android:gravity="center"
        android:background="@color/light_purple"/>
    <!-- Instruction TextView -->

    <TextView
        android:id="@+id/textInstruction"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Provide details below"
        android:paddingTop="10dp"
        android:textSize="20sp"
        android:layout_marginBottom="8dp" />
    <EditText
        android:id="@+id/editName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter your name"
        android:textSize="20sp"
        android:layout_marginBottom="16dp" />
    <!-- EditText for Age Input -->
    <EditText
        android:id="@+id/editAge"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:inputType="number"
        android:hint="Enter your age"
        android:textSize="20sp"
        android:layout_marginBottom="16dp" />

    <TextView
        android:id="@+id/textCondition"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Preferred Session"
        android:paddingTop="10dp"
        android:textSize="20sp"
        android:layout_marginBottom="8dp" />

    <!-- RadioGroup for Symptoms -->
    <RadioGroup
        android:id="@+id/radioGroup1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:layout_marginBottom="16dp">
        <RadioButton
            android:id="@+id/S1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="S1" />
        <RadioButton
            android:id="@+id/S2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="S2" />
    </RadioGroup>
    <!-- Button to Run Diagnostic -->
    <Button
        android:id="@+id/button1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Booking"
        android:layout_marginBottom="20dp"
        android:background="@color/purple"/>
    <!-- Result TextView -->
    <TextView
        android:id="@+id/textResult1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=""
        android:textSize="25sp"
        android:textColor="@color/red" />

</LinearLayout>



( main activity kt )
package com.example.practice1

import android.os.Bundle
import android.util.Log
import android.widget.Button
import android.widget.EditText
import android.widget.RadioButton
import android.widget.RadioGroup
import android.widget.TextView
import androidx.activity.enableEdgeToEdge
import androidx.appcompat.app.AppCompatActivity
import androidx.core.view.ViewCompat
import androidx.core.view.WindowInsetsCompat

class MainActivity : AppCompatActivity() {
    lateinit var nameInput : EditText
    lateinit var ageInput: EditText
    lateinit var radioGroup: RadioGroup
    lateinit var button: Button
    lateinit var resultResult1: TextView


    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContentView(R.layout.activity_main)
        nameInput = findViewById(R.id.editName)
        ageInput = findViewById(R.id.editAge)
        radioGroup = findViewById(R.id.radioGroup1)
        button = findViewById(R.id.button1)
        resultResult1 = findViewById(R.id.textResult1)

        button.setOnClickListener {
            //val age = ageInput.text.toString().toInt()
            val selectedButton: Int = radioGroup.checkedRadioButtonId
            val session: RadioButton = findViewById(selectedButton)
            val age = ageInput.text.toString().toInt()

            val consultant = when {
                age <= 12 && session.getText() == "S1" -> "Dr William"
                age <= 12 && session.getText() == "S2" -> "Dr Francis"
                age > 12 && session.getText() == "S1" -> "Dr Silva"
                age > 12 && session.getText() == "S2" -> "Dr Kate"
                else -> "No doctor assigned"  // Default case if no conditions are met
            }
            //display output
            resultResult1.text = "Name : " + nameInput.text.toString() +'\n'+ "Age : " + age.toString()  + '\n' + "Consultant Name : " + consultant

        }

        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main)) { v, insets ->
            val systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars())
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom)
            insets
        }
    }
}


( colors xml )

<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
    <color name="purple">#673AB7</color>
    <color name="red">#FE0028</color>
    <color name="light_purple">#A37DE6</color>
</resources>


( strings xml )

<resources>
    <string name="app_name">Practice1</string>
</resources>


( manifest )

<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">

    <application
        android:allowBackup="true"
        android:dataExtractionRules="@xml/data_extraction_rules"
        android:fullBackupContent="@xml/backup_rules"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Practice1"
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

</manifest>
