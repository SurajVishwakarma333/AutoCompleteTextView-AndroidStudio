# AutoCompleteTextView-AndroidStudio
• In Android, AutoCompleteTextView is a view i.e similar to EditText, except that it displays a list of completion suggestions automatically while the user is typing.

• A list of suggestions is displayed in drop down menu from which user can choose an item which actually replace the content of Editbox with that.

• It is a subclass of EditText class so we can inherit all the properties of EditText in a AutoCompleteTextView.

# syntax :
       
     <AutoCompleteTextView
        android:id="@+id/simpleAutoCompleteTextView"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:text="This is an AutoCompleteTextView" />

![Screenshot_2022_0611_122012](https://user-images.githubusercontent.com/101108540/173177025-f8a67f9e-a28e-46b9-8f29-f982304824c7.jpg)


# In order to display AutoCompleteTextView text in drop down list we have to use Array Adapter To Display Text Values In AutoCompleteTextView :
• To display the Array content in an autocompletetextview we need to implement Adapter. 
• In AutoCompleteTextView we mainly display text values so we use Array Adapter for that.



      import android.support.v7.app.AppCompatActivity;
      import android.os.Bundle;
      import android.view.Menu;
      import android.view.MenuItem;
      import android.widget.ArrayAdapter;
      import android.widget.AutoCompleteTextView;
      public class MainActivity extends AppCompatActivity {
      
      AutoCompleteTextView autoCompleteTextView;
      
      <!--Putting dowp-down list items in array -->
      String[] countryNameList = {"India", "China", "Australia", "New Zealand", "England","Pakistan"};
      
      @Override
      protected void onCreate(Bundle savedInstanceState) {
      super.onCreate(savedInstanceState);
      setContentView(R.layout.activity_main);
      
      //initiate an auto complete text view
      autoCompleteTextView = findViewById(R.id.autoCompleteTextView);
      
      ArrayAdapter adapter = new ArrayAdapter(this, android.R.layout.simple_list_item_1,countryNameList);
      autoCompleteTextView.setAdapter(adapter);
      autoCompleteTextView.setThreshold(1);     //start searching from 1 character
      autoCompleteTextView.setAdapter(adapter); //set the adapter for displaying
      country name list
      }
      }
