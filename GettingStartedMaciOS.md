#Dependencies for Mac + iOS
You will need xCode, Node.js, the React Native command line tools, and Watchman.

We recommend installing Node and Watchman via HomeBrew. 

                     brew install node
                     brew install watchman
                     
Node comes with npm, which lets you install the React Native command line interface.       

                     npm install -g react-native-cli
                     
If you get a permission error, try with sudo:                

                     sudo npm install -g react-native-cli
                     
#Testing your React Native Installation
Use the React Native command line tools to generate a new React Native project called "AwesomeProject", then run react-native 
run-ios inside the newly created folder.

                     react-native init AwesomeProject
                     cd AwesomeProject
                     react-native run-ios
                     
You should see your new app running in the iOS simulator shortly. react-native run-ios is just one way to run your app -
you can also run it from directly within Xcode or Nuclide.

#Modifying Your App
Now that you have successfully run the app, let's modify it. 
-Open index.ios.js in the texteditor of choice and edit some lines.
-Hit Command⌘ + R in your iOS simulator to reload the app and see your change
