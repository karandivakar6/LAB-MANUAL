MAD LAB
Program 1
1. Creating "Hello World" Application.

   
activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <Button
 android:id="@+id/button"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Click_me"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>


MainActivity.java


package com.example.anushamad03;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 Button b;
 b = findViewById(R.id.button);
 b.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 Toast.makeText(MainActivity.this,
 "Hey! We are using Android Application",
 Toast.LENGTH_SHORT).show();
 }
 });
 }
}



Program 2
2. Creating an application that displays message based on screen orientation.


activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <Button
 android:id="@+id/por"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Portrait"
 android:layout_centerInParent="true"/>
 <Button
 android:id="@+id/lan"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Landscape"
 android:layout_below="@+id/por"
 android:layout_centerInParent="true" />
</RelativeLayout>


MainActivity.java


package com.example.anushamad03;
import android.content.pm.ActivityInfo;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 Button l, p;
 l = findViewById(R.id.lan);
 p = findViewById(R.id.por);
 l.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_LANDSCAPE);
 Toast.makeText(MainActivity.this,
 "Hey! We are in Landscape orientation",
 Toast.LENGTH_SHORT).show();
 }
 });
 p.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 setRequestedOrientation(ActivityInfo.SCREEN_ORIENTATION_PORTRAIT);
 Toast.makeText(MainActivity.this,
 "Hey! We are in Portrait orientation",
 Toast.LENGTH_SHORT).show();
 }
 });
 }
}

Program 3
3. Create an application to develop Login window using UI controls.


activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:id="@+id/main"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity"
 android:orientation="vertical">
 <TextView
 android:id="@+id/textView6"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="Login"
 android:gravity="center"/>
 <EditText
 android:id="@+id/editTextText8"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:ems="10"
 android:inputType="text"
 android:text="Name" />
 <EditText
 android:id="@+id/editTextText9"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:ems="10"
 android:inputType="text"
 android:text="password" />
 <Button
 android:id="@+id/button3"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="login" />
</LinearLayout>


MainActivity.java


package com.example.jithin33lab;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;
import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
 private EditText a, b;
 private Button c;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 EdgeToEdge.enable(this);
 setContentView(R.layout.activity_main);
 a = findViewById(R.id.editTextText8);
 b = findViewById(R.id.editTextText9);
 c = findViewById(R.id.button3);
 c.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 String username = a.getText().toString().trim();
 String password = b.getText().toString().trim();
 if (username.equals("admin") && password.equals("pass")) {
 Toast.makeText(MainActivity.this,
 "Login successful", Toast.LENGTH_SHORT).show();
 } else {
 Toast.makeText(MainActivity.this,
 "Invalid username or password",
 Toast.LENGTH_SHORT).show();
 }
 }
 });
 }
}


Program 4
4. Create an application to implement new activity using explicit intent, implicit intent and content provider.
Steps:
1. Click New Project, the New Project Dialog box appears.
2. Choose Empty Views Activity then click Next.
3. Specify the Name of your project, Select the Language as Java, and Select the Minimum SDK as API
16 ("Jelly Bean", Android 4.1).
4. Click Finish Button.

   
activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity"
 android:orientation="vertical"
 android:padding="30dp">
 <Button
 android:id="@+id/btnExplicitContent"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="Explicit Content"
 android:textSize="30sp"
 android:layout_marginTop="30dp">
 </Button>
</LinearLayout>


MainActivity.java


package com.example.joshimad31;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
public class MainActivity extends AppCompatActivity {
 Button btnExplicitContent;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 btnExplicitContent = findViewById(R.id.btnExplicitContent);
 btnExplicitContent.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 Intent intent = new Intent(MainActivity.this, NewActivity.class);
 startActivity(intent);
 }
 });
 }
}
Next step: To create another activity for Explicit Intent, go to File --> Click On New --> window opens,
select Activity ---> Empty Views Activity. In the dialog window give file name as NextActivity and Layout
name as activity_new, click ok.
activity_new.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:id="@+id/main"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".NewActivity"
 android:orientation="vertical"
 android:padding="30dp">
 <Button
 android:id="@+id/btnImplicitContent"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="Implicit Content"
 android:textSize="30sp"
 android:layout_marginTop="30dp">
 </Button>
</LinearLayout>
NewActivity.java
package com.example.joshimad31;
import androidx.appcompat.app.AppCompatActivity;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
public class NewActivity extends AppCompatActivity {
 Button btnImplicitContent;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_new);
 btnImplicitContent = findViewById(R.id.btnImplicitContent);
 btnImplicitContent.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View view) {
 Uri webpage = Uri.parse("http://www.openglprojects.in");
 Intent intent = new Intent(Intent.ACTION_VIEW, webpage);
 startActivity(intent);
 }
 });
 }
}


Program 5
5. Create an application that displays custom designed Opening Screen.
Steps:
1. Click New Project, the New Project Dialog box appears.
2. Choose Empty Views Activity then click Next.
3. Specify the Name of your project, Select the Language as Java, and Select the Minimum SDK as API
16 ("Jelly Bean", Android 4.1). Click Finish Button.

   
activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:id="@+id/main"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <TextView
 android:id="@+id/idTVHeading"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:layout_centerInParent="true"
 android:layout_margin="20dp"
 android:gravity="center"
 android:padding="10dp"
 android:text="Background Drawable in Android"
 android:textAlignment="center"
 android:textColor="@color/black"
 android:textSize="20sp"
 android:textStyle="bold" />
</RelativeLayout>


MainActivity.java


package com.example.joshimad51;
import android.os.Bundle;
import android.widget.RelativeLayout;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
 private RelativeLayout containerRL;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 containerRL = findViewById(R.id.main);
 // Setting background for our relative layout
 containerRL.setBackground(getResources().getDrawable(R.drawable.back_drawable));
 }
}
Next Step: app --> res --> drawable --> right click on drawable --> Select New --> Click Drawable
Resource File. Give filename as "back_drawable.xml" and root element as shape, set source as main,
then click OK.
back_drawable.xml
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
 android:shape="rectangle">
 <gradient
 android:angle="270"
 android:endColor="@color/white"
 android:startColor="#2C3A87" />
</shape>


Program 6 (Mad 6)


activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:id="@+id/main"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity"
 android:orientation="vertical">
 <TextView
 android:id="@+id/textView7"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="klestudents_good"
 android:gravity="center"/>
 <Button
 android:id="@+id/button4"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="Button" />
</LinearLayout>


MainActivity.java


package com.example.joshi_mad6;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
 private TextView a;
 private Button b;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 // Initialize views
 a = findViewById(R.id.textView7);
 b = findViewById(R.id.button4);
 // Set click listener for the button
 b.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 a.setText("All the best");
 }
 });
 }
}


Program 7 (Mad 7)
Create a UI with ALL Views


activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 android:orientation="vertical"
 android:padding="16dp">
 <!-- Name EditText -->
 <EditText
 android:id="@+id/editTextName"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:hint="Enter Name"
 android:inputType="text"/>
 <!-- Date of Birth EditText -->
 <EditText
 android:id="@+id/editTextDOB"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:hint="Date of Birth"
 android:inputType="date"/>
 <!-- Gender RadioGroup -->
 <RadioGroup
 android:id="@+id/radioGroupGender"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:orientation="horizontal">
 <RadioButton
 android:id="@+id/radioButtonMale"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Male"/>
 <RadioButton
 android:id="@+id/radioButtonFemale"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Female"/>
 </RadioGroup>
 <!-- Checkbox for terms and conditions -->
 <CheckBox
 android:id="@+id/checkBoxTerms"
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="I agree to the Terms and Conditions"/>
 <!-- Submit Button -->
 <Button
 android:id="@+id/buttonSubmit"
 android:layout_width="match_parent"
 android:layout_height="wrap_content"
 android:text="Register"/>
</LinearLayout>


MainActivity.java


package com.example.joshi_mad_7;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.CheckBox;
import android.widget.EditText;
import android.widget.RadioButton;
import android.widget.RadioGroup;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
public class MainActivity extends AppCompatActivity {
 private EditText editTextName, editTextDOB;
 private RadioGroup radioGroupGender;
 private CheckBox checkBoxTerms;
 private Button buttonSubmit;
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 // Initialize views
 editTextName = findViewById(R.id.editTextName);
 editTextDOB = findViewById(R.id.editTextDOB);
 radioGroupGender = findViewById(R.id.radioGroupGender);
 checkBoxTerms = findViewById(R.id.checkBoxTerms);
 buttonSubmit = findViewById(R.id.buttonSubmit);
 // Set click listener for the submit button
 buttonSubmit.setOnClickListener(new View.OnClickListener() {
 @Override
 public void onClick(View v) {
 // Retrieve user input
 String name = editTextName.getText().toString().trim();
 String dob = editTextDOB.getText().toString().trim();
 int selectedGenderId = radioGroupGender.getCheckedRadioButtonId();
 String gender = getGenderFromId(selectedGenderId);
 boolean termsChecked = checkBoxTerms.isChecked();
 // Validate user input
 if (name.isEmpty() || dob.isEmpty() || gender.isEmpty() || !termsChecked) {
 Toast.makeText(MainActivity.this,
 "Please fill in all fields and agree to terms.",
 Toast.LENGTH_SHORT).show();
 } else {
 // Process registration
 Toast.makeText(MainActivity.this,
 "Registration successful!",
 Toast.LENGTH_SHORT).show();
 // Optionally navigate to another activity here
 }
 }
 });
 }
 // Helper method to get gender from radio button ID
 private String getGenderFromId(int selectedId) {
 RadioButton radioButtonMale = findViewById(R.id.radioButtonMale);
 RadioButton radioButtonFemale = findViewById(R.id.radioButtonFemale);
 if (selectedId == radioButtonMale.getId()) {
 return "Male";
 } else if (selectedId == radioButtonFemale.getId()) {
 return "Female";
 } else {
 return "";
 }
 }
}


Program 8
8. Learn to deploy Android applications.
Steps to Deploy an Android Application
1. Prepare App (use Program 1 Hello World for this program). Optimize performance and test thoroughly.
Ensure compatibility with various devices.


activity_main.xml


<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
 xmlns:android="http://schemas.android.com/apk/res/android"
 xmlns:app="http://schemas.android.com/apk/res-auto"
 xmlns:tools="http://schemas.android.com/tools"
 android:layout_width="match_parent"
 android:layout_height="match_parent"
 tools:context=".MainActivity">
 <TextView
 android:layout_width="wrap_content"
 android:layout_height="wrap_content"
 android:text="Hello World!"
 app:layout_constraintBottom_toBottomOf="parent"
 app:layout_constraintEnd_toEndOf="parent"
 app:layout_constraintStart_toStartOf="parent"
 app:layout_constraintTop_toTopOf="parent"
 android:textSize="30sp"/>
</androidx.constraintlayout.widget.ConstraintLayout>


MainActivity.java


package com.example.helloworld;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
public class MainActivity extends AppCompatActivity {
 @Override
 protected void onCreate(Bundle savedInstanceState) {
 super.onCreate(savedInstanceState);
 setContentView(R.layout.activity_main);
 }
}



2. Generate Signed APK (Android Package Kit):
In Android Studio, navigate to Build > Generate Signed Bundle/APK.
Follow the prompts to create a new keystore or use an existing one. A keystore is a binary file that
contains a set of private keys.
Configure the build type (release) and signing configuration.
Generate the signed APK file.
3. Test Your Signed APK:
Before distributing your app, test the signed APK to ensure that the signing process did not introduce any
issues.
Install the APK on various devices and perform thorough testing.
4. Release on Google Play Console:
Sign in to the Google Play Console (https://play.google.com/apps/publish).
Create a new app entry if this is your first release or select an existing app.
Complete all the required information for the app listing, including the title, description, screenshots, and
categorization.
Upload your signed APK file.
Set pricing and distribution options.
Optimize your store listing for search and conversion.
Once everything is set, click the "Publish" button to release your app to the Google Play Store.
5. Other Distribution Channels (Optional):
Besides Google Play, you can distribute your app through other channels such as Amazon Appstore,
Samsung Galaxy Store, or third party app marketplaces.
Each distribution channel may have its own requirements and submission process, so be sure to follow
their guidelines.
6. Monitor and Update:
Keep an eye on user feedback and app performance metrics through the Google Play Console.
Regularly update your app to fix bugs, add new features, and improve user experience based on
feedback.
