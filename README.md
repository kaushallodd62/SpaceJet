Name - Kaushal Lodd
Roll - BT19CSE052
Assignment 7 README.md file

--------------------------------------------------------------------------------------------------------------------------------------

    JAVA Setup
    sudo apt-get update
    sudo apt-get install default-jdk

--------------------------------------------------------------------------------------------------------------------------------------

Q1) Design a ‘Space Jet’ game in android studio.

    Game Story: In our game there will be a Space Jet, and the jet has to kill the enemies by hitting them. There will also be some good guys and our Space Jet should not kill them. So basically if our Space jet touches other character that will be destroyed. So we have to only kill the enemies.

    Step 1: Installation of Android Studio in the system.
        https://developer.android.com/studio

    Step 2: Creating a New Project and Downloading required images.
        Name - Space Jet
        Android Version - Lollipop version 5.1 (API 22).
        Copying all downlaoded images into drawable folder in res folder of project.

    Step 3: Designing the Start Screen.
        Full Screen Activity with background image and two fully functional ImagedButtons.
        To make your application full screen, we go to res->values-theme->themes.xml and add the following code.
    
            <!-- Base application theme. -->
            <style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
                <item name="windowNoTitle">true</item>
                <item name="windowActionBar">false</item>
                <item name="android:windowFullscreen">true</item>
                <item name="android:windowContentOverlay">@null</item>
            </style>
        
        In our AndroidManifest.xml file, change the android:theme attribute as follows:
            android:theme="@style/AppTheme"
        
        In the activity_main.xml file, add the following code inside the <RelativeLayout /> tag to create the ImageButtons:
            <ImageButton
                android:id="@+id/buttonPlay"
                android:background="@drawable/playnow"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_above="@+id/buttonScore"
                android:layout_centerHorizontal="true" />

            <ImageButton
                android:id="@+id/buttonScore"
                android:background="@drawable/highscore"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_alignParentBottom="true"
                android:layout_centerHorizontal="true" />
        
        Now, modify MainActivity.java to implement button functionality, i.e. add an OnClickListener, and set the button to it.
    
    Step 4: Creating the game activity

        Create a new activity named GameActivity (right click on the package name -> new -> activity -> empty activity).

    Step 5: Create the GameView class. This is the main interface where we will play the game.

        It needs to contain the following elements:
            1. A volatile boolean type variable that tracks whether the game is running or not.
            2. the gameThread thread, which is the game loop.
            3. the function run(), which keeps running while the running variable is true. Inside this loop, we use the following methods:
                a. update(), which updates the coordinate of the character 
                b. draw(), which draws the characters to the canvas 
                c. control(), which controls the frames per second drawn in the game 
                d. pause() to pause the game, and 
                e. resume() to resume the game.

        Now, Add GameView to GameActivity.

    Step 6: Create the Player class.
        This class should contain:
            1. integer variables for the coordinates of the player
            2. integer variable for the speed of the player
            3. the constructor which initializes these variables.
            4. the drawable resource, or the bitmap.
            5. methods to update the coordinate of the character, getter functions to get x coordinate, y coordinate and speed.
        
        Now, add the Player into our GameView.
        
    
    Step 7: Add controls to the player character, such that when the player taps on the screen the characters boosts up, and when the screen is released, the character boosts down.
        To do this, update the method onTouchEvent() to add the required functionality.
        
        Modify the Player.java file to add this functionality.
        
    Step 8: Create animated background: modify GameView.java file to add background stars, so that the background looks animated.
    
    Step 9: Add enemy characters.
        Create a new class called Enemy containing the required member variables and member functions. Add this class into GameView.
    
    Step 10: Add features and functionalities:
        1. Collision Detection: Modify the Enemy class as well as the Player class to add this functionality.
        2. Blast Effect: create a new java class called Boom, for the blast effect, and add code. Add this functionality into the GameView class as well.
    
    Step 11: Friendly characters
        Create a Friend class and ad the required member variables and member functions. Add this into gameView.
    
    Step 12: Adding scores functionality.
        Declare new variables in GameView for scores. Also add the functinality for calculating scores.
        Create a new activity called HighScore and configure the files HighScore.java and activity_high_score.xml
        Add the high score functionality to the "High Score" button in our MainActivity.java file.
    
    Step 13: Add sounds
        Create MediaPlayer objects in the GameView.java file, and initialize them in the GameView constructor, and start the game music method.
        

The game is now complete. Click the "play" button on the toolbar to run it in the selected virtual device, or run it on your own device using USB debugging feature.

    Step 14: create APK.
        Go to Build -> Build Bundle(s)/APK(s) -> Build APK(s) from the toolbar menu.
        Once the APK build is complete, select "Locate" to access the apk file.

--------------------------------------------------------------------------------------------------------------------------------------