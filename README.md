# Cookies
After clicking a button Image and text just change


screen-shot-2017-05-03-at-3.01.15-pm.png

Set Data on Views
A Review Of What We Know
So we’ve now seen a few examples of how we can use the setText method to modify a view. Here’s one example we just looked at:

TextView orderSummaryTextView = (TextView) findViewById(R.id.order_summary_text_view);
orderSummaryTextView.setText(message);
You can break this down into two steps:

Step 1 : Get the view object using the view ID
The first line of code is getting the TextView and storing it in a variable named orderSummaryTextView. To actually get the view, we use the findViewById method which is a method in the Activity class. The argument required is the view ID, which we supply by typing R.id.IDOFVIEW. In this case, the ID of the view is order_summary_text_view, as set in the XML. Note that you need to cast the object, which is what the (TextView) is doing. It is saying that the value findViewById is specifically a TextView and not just a generic View.

Step 2 : Call a method ON the view object
Since we are calling a method on an object, we use the dot syntax. orderSummaryTextView.setText(message); is equivalent to saying, take the orderSummaryTextView object which has the capability to setText (as seen in the documentation), and setText to whatever string it is passed (in this case the string variable message is passed).

Your Turn
You’re going to practice these steps—getting the view object, storing it in a variable, and then manipulating that view object.

Step 1 : Create a New Project
To start this exercise, create a new project (use the Empty Activity template on Android Studio 1.4 and newer). The application name should be Cookies.

Create this new project in the same way as you have for previous projects.

Step 2 : Copy over files
Copy over the Java and XML code into the correct files. The code is here.

Add Gradle Dependency

Then you'll want to copy the line below into your app's build.gradle file:

compile 'com.android.support:appcompat-v7:22.1.0'
You can find the app gradle file inside gradle scripts in your project. Careful not to confuse it with the project gradle file!


You should add this line inside dependencies:


Add the dependency including the word compile inside dependencies{...}. Don't worry if the rest of the lines inside the dependency block don't exactly match the screenshot above.

You may need to sync your project after adding this file:


After making modifications to the Gradle file, this notification to Sync the project should appear at the top of Android Studio.

Android studio may suggest a newer version of the appcompat library, and you should use that one.

Image Files

Also place these two image files in the drawable folder. They can be downloaded from the Supporting Materials section at the bottom of the page:


Step 3 : Hook up the button
Hook up the “Eat Cookie" button so that, when it's clicked, the image and the text change as seen below.


You’ll need to modify the XML to handle a button being pressed (you’ve done this in Lesson 2 and the practice set). Then you’ll need to use the skills you just learned to manipulate the image and text with the Java code. Good luck!

Set Data on Views Solution
The first part of solving this problem is using the onClick attribute to designate what method should be called when the button is clicked. You should use eatCookie since the method is provided for you already in the java code:

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:text="Eat cookie"
        android:onClick="eatCookie" />
Next, you’ll need to actually write the Java code for eatCookie:

public void eatCookie(View view) {
   // Find a reference to the ImageView in the layout. Change the image.
   ImageView imageView = (ImageView) findViewById(R.id.android_cookie_image_view);
   imageView.setImageResource(R.drawable.after_cookie);

   // Find a reference to the TextView in the layout. Change the text.
   TextView textView = (TextView) findViewById(R.id.status_text_view);
   textView.setText("I'm so full");
}
Both times you grab the View object (a TextView in one case, an ImageView in the other) using the findViewById method. You pass the id for the view, which you can find in the xml. For the ImageView, you use the setImageResource method and pass the id of the drawable.

For the TextView, you use the setText method we’ve seen before.
