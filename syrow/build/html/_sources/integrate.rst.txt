Android (React)
******************************************************






To integrate your android app with project follow the below guidelines.

 * Open android studio > File > New project (android) > 

.. figure::  images/crtandroidproject.png
	   :align:   center
  
In the above tab you have to fill:

  * Application name in **Application name** textfield, for e.g here is `TestChatApp` .

  * Here **Company domain** for e.g. `syrow.com` 

  * Here set the **Project location** means the location of project in your system then
  
  * Click on **Next** button then 

.. figure::  images/targetandroiddevice.png
	   :align:   center

Here you set the **Targeted Android Device** (for which you are  developing this).
  
   * Here set the *Device* and their *API* version.
   
   * Click on **Next** button to proceed.

.. figure::  images/targetandroiddevice.png
	   :align:   center

Above tab will be open here

  * Add an **Activity** to Mobile .
 
  * Click on **Next** 

.. figure::  images/addactivity.png
	   :align:   center

Here 

  * Click on **Empty Activity** to select that activity for your project.

  * Then click on **Next** button.

.. figure::  images/configureactivity.png
	   :align:   center

In the above tab enable these two checkboxs **Generate Layout File** and **Backwards Compatibility (AppCompact)** and set 

   * **Activity name** to *MainActivity* and 

   * **Layout Name** to *activity_main* then

   * Click on **Finish** button to finish the configuration process.

Then you will see below tab

.. figure::  images/mainactivityjava.png
	   :align:   center

Here now you have to import module from library.


.. figure::  images/newmodule.png
	   :align:   center 

Then click on **File** > **New** > **New Module...** as in above tab.

.. figure::  images/newmodule1.png
	   :align:   center 


.. figure::  images/importmodulefromlibrary1.png
	   :align:   center

Here browse file from your system means

   * Set the **File name:** as in above tab.

.. figure::  images/importmodulefromlibrary.png
	   :align:   center

Here 
 
    * Select **app-debug.aar** for *File name:*

.. figure::  images/subprojectname.png
	   :align:   center 

As you can see above 
  
   * Click on **Subproject name** textfield and rename it form *TestChatApp* to *app-syrow* .

   * Then click on **Finish** button.


 # Now copy the below code into your main activity



Here is Java code ::



 public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button btnSend = findViewById(R.id.btn_send);

        btnSend.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                Intent intent = new Intent(android.content.Intent.ACTION_VIEW);

                intent.putExtra("APIKey", “<— REQUEST CLIENT RELATIONSHIP LEAD —>”);
                intent.putExtra("customerName", "Raj Singh");
                intent.putExtra("customerEmail", "raj@syrow.com");
                intent.putExtra("phoneNumber", "9876543210");
                intent.setComponent(new ComponentName("packagename//com.syrow.chat",
                        "classname//com.syrow.chat.ChatRoomActivity"));
                startActivity(intent);

            }
        });

    }

 }

.. NOTE::

  * Now you can run the build process to test

  * And **customerName, customerEmail and phoneNumber** are optional in above code.

After importing the Library in your project. You will find your library module name in ``setting.gradle(Project Settings)``.

.. figure::  images/1.png
	   :align:   center 

Add your library dependency to dependecies in ``build.gradle(Module:app)`` . i.e implementation project **(“module name”)** .
Also add the dependencies that are **added/used** in the library **project/module** to your project.

.. figure::  images/2.png
	   :align:   center 

In **Color.xml** add these *color attribute* to change the color of chatApp theme. ::
 
   <color name="chatColor">#000000</color>
 <color name="chatColorPrimaryDark">#000000</color>

.. figure::  images/3.png
	   :align:   center

And you are done. Here is your AAR file 

 
:download:`this is AAr file <app-debug.aar>`.


Here is gradle-build-gradle Code ::

  dependencies {
          classpath 'com.android.tools.build:gradle:3.3.1'
          
          // NOTE: Do not place your application dependencies here; they belong
          // in the individual module build.gradle files
          classpath 'com.google.gms:google-services:1.5.0-beta2'
      }
  
  
  allprojects {
      repositories {
          google()
          jcenter()
          maven { url 'https://jitpack.io' }
          flatDir {
              dirs 'libs'
          }
          
      }
  }



 
Here is app-build-gradle Code ::

    compileOptions {
          sourceCompatibility JavaVersion.VERSION_1_8
          targetCompatibility JavaVersion.VERSION_1_8
      }  
  
  
  
    dependencies
  {
  
      implementation 'com.android.support:design:27.1.1'
      implementation 'com.android.support.constraint:constraint-layout:1.1.2'
      implementation 'com.android.support:support-v4:27.1.1'
      testImplementation 'junit:junit:4.12'
      androidTestImplementation 'com.android.support.test:runner:1.0.2'
      androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.2'
      implementation 'com.loopj.android:android-async-http:1.4.9'
      implementation 'de.hdodenhof:circleimageview:2.2.0'
      implementation 'io.crossbar.autobahn:autobahn-android:18.5.1'
      implementation 'org.jetbrains:annotations-java5:15.0'
      implementation 'com.android.support:cardview-v7:27.1.1'
      implementation 'com.android.volley:volley:1.1.1'
      implementation 'com.github.bumptech.glide:glide:4.3.1'
      implementation 'com.github.Cloudist:ImageViewer:1.1.5'
      implementation 'me.relex:photodraweeview:1.1.3'
      implementation 'com.facebook.fresco:fresco:0.14.1'
      implementation 'com.4ert:audioview:0.4'
      implementation 'com.squareup.picasso:picasso:2.71828'
  }
   
  
  android {
      defaultConfig {
          multiDexEnabled true
      }
  }


Here is java Code ::

  b=(Button)findViewById(R.id.btn_send) ;
        b.setOnClickListener(v -> {

            Intent intent=new Intent(MainAct.this,ChatRoomActivity.class);

            intent.putExtra("APIKey", "<— REQUEST CLIENT RELATIONSHIP LEAD —>");
            intent.putExtra("customerName", "Raj Singh");
            intent.putExtra("companyId", "2");
            intent.putExtra("customerId", "2");
            intent.putExtra("customerEmail", "raj@syrow.com");
            intent.putExtra("phoneNumber", "9876543210");
            startActivity(intent);
           

        });



.. raw:: html

    <div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; height: auto;">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/h3udGVw8eBw" frameborder="0" allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe>
    </div>




 




























