You will need Android Studio, node.js, React Native command line tools, and WatchMan.
We recommend installing node and Watchman via Homebrew. 

                   brew install node
                   brew install watchman
                   
Node comes with npm, which lets you install the React Native command line interface.

                    npm install -g react-native-cli
                    
If you get a permission error, try with sudo: 

                    sudo npm install -g react -native-cli
                    
If you plan to make changes in Java code, we recommend Gradle Daemon which speeds up the build. 

#Test Your React Native Installation
Use the React Native command line tools to generate a new React Native project called "AwesomeProject", then run
react-native run-android inside the newly created folder:

                 react-native init AwesomeProject
                 cd AwesomeProject
                 react-native run-android
                 
If everything is set up correctly, you should see the new app running in your Android emulator shortly. react-native
run-android is just one way to run your app - you can also run it from directly within Android Studio or Nuclide.

#Modifying Your App
Now that you have successfully run the app, let's modify it:

     -Open index.android.js in the text editor of your choice
     -Press the R key choice twice or select Reload from the developer menu to see your change!
