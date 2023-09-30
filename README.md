# ios-duke-directory

# HW 5

In HW5, we will continue to enhance our SwiftUI app from HW4 with new features and functions.  Please do not add functions that are not listed - you will only receive Extra Points for the items listed in the Rubric.

Instead of doing an automatic "Download and Replace" from the button on the ListView, present options to the user when the button is pressed:
Download and Replace
Download and Update
Cancel
If the user selects either Download option, download the data (with progress indicator) and update your database (including in Sandbox) accordingly.
Put an "Add" button on the ListView.  When pressed this will invoke the AddEditView (see below) and allow the user to create the information for a new user and then Save it. 
Support a .swipeAction to be able to have an "Edit" option from the List view.  The Edit option will take you to the AddEditView, where the fields are pre-filled with the person info and can be edited and saved to your data model. 
Create an AddEditView.  This View will this is where you can be a bit creative.  Maybe put the pic in the center like in the tutorial, put the important info (like name) in a larger font, use some colors, maybe even substitute emojis for the hobbies!  This is one area I want to see a little creativeness.
When in "Edit" mode (not "Add" mode), the AddEditView should allow the user to also save the information to the server (upload / update) but only if they are editing their own info.  The option to upload should not appear if the user is editing other people's info.
Once you have your Project Team name, make sure and edit your info to add your Team name to the Teams field!
Support .onDelete modifer or similar swipeAction to be able to delete people from the List view (and your data model)




# HW4 - List View in SwiftUI
Due: Mon Oct 2, 2023 10:00am

Extras:
1. 

The goal of HW4 is to get you coding in SwiftUI. I am giving you extra time as I want you to spend your time learning SwiftUI and understanding the concepts. Do this by:
    * Doing the ToDoList Tutorial in the repo
    * Doing at least Chapter 1 of the Apple Tutorial, hereLinks to an external site.
    * Review online information sites like the ones hereLinks to an external site. and hereLinks to an external site..

Once you understand SwiftUI, you can start HW4.  HW4 is a list view of all the students in the class plus Professor and TAs.

Here are the list of functions, in the order I suggest doing them:

- [x] Start a new project, this time use the SwiftUI template instead of Storyboard.
- [x] Move your existing Data Model into the new app. Make sure you have good organization of your files and folders for readability. Learn from the tutorial on a good way to organize the files in your project. 
- [ ] Move your upload/download code as well.  For this homework, you will just use download/replace, but in the future we will use the rest.  fyi, for this homework I ended moving my upload/download code into my data model as there is no "ViewController" anymore and it doesn't make sense to be in the View code.
- [x] Don't forget to move over your AppIcon and to name the Target your first name.
- [x] In the last homework, some folks seemed confused as to how to "bootstrap" the data base.  So let me be specific - your own DukePerson information should always be in the data model, so when you first come up, if there is nothing in the sandbox then do a save which will save your DukePerson to the sandbox. Thus, when we first bring up your app, we will see just one cell - you.
- [ ] Have a button on your first screen to issue a Download / Replace call to the server.  You will download all the entries in the server into your data model and then save to disk (sandbox).  If for any reason the download fails (server is down, network issues, etc), you just keep showing your own record.
- [ ] You must have some type of ProgressView in case the download takes more than a few seconds. 
- [ ] Present a List View of everyone.   Each entry ("cell") in the list should show the person's:
    * Picture
    * Name
    * email
    * DUID
    * Netid
    * Program
    * Plan
- [ ] Format the cell however you want - you don't have to copy mine.  But don't just show Description field - we will do that on the other View.
- [ ] The list should be broken up into 3 sections, entitled "Professor", "TA" and "Student".  See attachment for an example.
- [ ] If the user clicks on a person in the list, show a simple View of the person's picture and description, like you did in HW2.  The description should contain all relevant information from DukePerson (you don't need to show "plan" and "program" for Professors).
- [ ] Add a Search Bar to the List view.  The search should go against the description property.  You can code it so the search is dynamic as the user types, or wait until they hit enter.  Either way, the View will change to only show cells that contains the search text.

## Other
- [ ] We need everyone's server information to be clean, correct and professional.  Make sure all the data is correct.  Have an updated, new picture with you looking at the camera.  Remove any attributed text from all fields.  Make sure all data accurately reflects your real information. No bad data. Points will continue to be deducted from "Follows Directions" for every homework that there are issues with your information.




# HW3 - Communications
Due: Thu Sep 21, 2023 11:00am

Extras:
1. Add a Help button to present the detailed help instructions with a new VC.
2. Overall UI enhancement: aligned font, color palettes with the app theme, better visual appealing.
3. Progress indicator: match the progress bar with a label show the percentage of progress, complement this feature with expressive emoji to give users straightforward feeling of the progress.
4. Handling bad role and gender data: write initialization for role and gender enum, if input is specficied but not valid among the options, it will be defaultly set to "Other". This could be considered as extra points as mentioned in Teams. 

The purpose of this HW is to be able to send your personal information to a server for storage. You will also be able to receive the information about all your classmates.  If everyone is successful, then you will have full information (including updated pictures) of everyone in the class.  

You can continue to use the same project file you used in HW1 and HW2 if you wish.  Just make sure you create an ece564hw3 repo on GitLab and give us Reporter access.

Here is the list of capabilities to add in this homework:

- [x] Information Upload – You will be using HTTP / REST to send your own information to a web server in the ECE 564 JSON Grammar.  You cannot update the information of others.  This is controlled by a password that I will send you.  This password is used in the "Basic" Authentication of the HTTP header field for "Authorization".  The authentication information needs to be in a String of "netid:password" and then into Base64. The server will compare the netid:password to the one stored in the database and if there is a match will allow the update.  Do not share your password with anyone.
- [x] Information Download - you can download the latest information about the entire class.    Since this is a long running task you must present a progress indicator of some type until completed.  Once completed, you should save to the Sandbox.
- [x] Enhanced error checking / data mapping - quite often there will be students (or even a Professor ;-) )that push bad data to the server.  Don't let their mistakes crash your app!  You will lose points for a crash on any obvious places where you should have been able to catch the bad data.  So, add error checking code and data mapping code accordingly.  For example, if you get a Role string that doesn't match your options, just set it to "Other". 
- [x] Picture Support - take/find a picture of yourself (not an avatar, a good picture of you, where you are looking at the camera and we can see your face) and cut it down using Preview or similar tool to 2 inches by 2 inches and either 72 or 100 dpi.  Drag the picture into your Assets folder in your Project.  You will need to use the "named:" initializer to load it into a UIImage.  You may need to also reduce the quality to ensure the b64 string is less than 100k.

## Model
- [x] We are adding a lot more fields to the database. See HW3 Spec (attached below) to make sure your DukePerson contains all the required new fields.
- [x] You do not need at this point to allow add/update of all these fields, but you can for the extra points.  If you don't, however, you must create a COMPLETE RECORD OF YOURSELF that you can send to the Server, including a new picture.

## View
- [x] You are going to now use the main.storyboard View. Make sure once you create the new DownloadVC to control this view (see Controller below), you link main.storyboard to the right View Controller using the "Identity Inspector" as I showed in class.
- [x] On this view, you will ask the user if they want to do an "Initial Upload", "Updated Upload", "Download / Replace", "Download / Update" or "Load from Disk" (5 buttons).   Here are the specific operations of each choice:
    - [x] Initial Upload - Use the POST endpoint to add your info to the server
    - [x] Updated Upload - Use the PUT endpoint to update your info in the server
    - [x] Download / Replace - Downloads all the entries from the ECE564 server and replaces on Disk (Sandbox) your data file
    - [x] Download / Update - Downloads all the entries from the ECE564 server.  If a DUID already exists on Disk (Sandbox), update it.  If it does not exist, add it.
    - [x] Load from Disk - just precede as you did in HW2 - if the file is found on Disk (Sandbox), load it.  If not, load the ece564class.json file.
- [x] Add a ProgressView control to the main storyboard page as well.  Use the delegate method approach for your URL Session so you can get messages as it downloads.  Update the ProgressView during the download.
- [x] Add a "Continue" or "Done" button.  The user presses this after their selection is complete.  The text field should let the user know when operations are complete and if they are successful or not.
- [x] When the "Continue" or "Done" button is pressed, present the original ViewController from HW1.
- [x] If anything is not successful, do the best to show an error of what happened in a TextView on main and do not go to the original ViewController.
- [x] See attached file for an example of what the main.storyboard View could look like.  Obviously, don't match mine exactly - add your own twist - and if you want do additional color, font, background, controls, etc for extra points.

## Controller
- [x] You need to create a new UIViewController instance to managed the main.storyboard View.  Call it "DownloadVC". 
- [x] You will need to add logic support for the 6 buttons. 
- [x] For download, you will need to support the URLSessionDataDelegate protocol and implement urlSession delegate messages.  This is where you will send updates to your ProgressView.
- [x] Use the TextView for any error or other types of output messages.  If you add a Help button (this would be extra), for example, you could print help instructions in this window.

## Other
- [x] When you send your data to the server, you need to send all the DukePerson info in HW3 Spec and nothing else. 
- [x] You do not need to be able to input your own data using the app - you can "pre-build" your DukePerson record (with picture) but  then add it to the data model.  The upload() method should retrieve it from the data model, not from the "pre-built" DukePerson.
- [x] Make sure your base64 picture is small (less than 100KB).  If not, it will take too long to upload and for others to download.
- [x] After you upload your own data, check your data using the server homepage - if it all looks good there, there is a good chance it will work for everyone.

# HW2 - Persistent Storage
Due: Thu Sep 14, 2023 11:00am

Extras:
1. I wrote a extra `deleteJSON()` function for testing and other purposes. 
2. I made the UI enhancements in the DukePersonVC: background color, gradients and font, etc. 
3. I added an additional `Copy Email` Button and functions, where I utilized **alerts** and **clipboard** for copy the person's email.
4. I made a `Save to Local` button that can save the current data into sandbox (which is not required but functionally useful), the data can be reused and maintained.
5. I modified the algorithms when match the parameters to DukePerson: now the parameter is totally case unsensitive, `LN=` is ok to use for using rather than only `ln=`. I made this changes because the keyboard always start with the capital case. 
6. I made detailed error messages when handing json loading and saving. 

In this Homework we will be able to persist our DukePerson information so that it is saved on disk and available next time the app is launched.  In addition, you will be able to load a JSON file to "bootstrap" the database as well as expand our definition of the DukePerson object.  Specifics are below.

Since this builds off the code from HW1, you do not need a new project (although you are welcome to create one).  You DO need a new GitLab repository called ece564hw2 and once again give us Reporter access.  Note:  the Xcode Project name does not need to change - it can still be ece564hw1.

## Model

The Data Model should be brought over from HW1 and expanded.  You will need to support a few more fields.  This info is also in the attached "HW2 Spec"

- [x] You need to support the following additional fields:
    - [x] program:String
    - [x] plan:String
    - [x] picture:String

* Note: no need to update the three fields.*

- [x] You will need to update the .description field to add (for Students only) - "(Firstname) is in the \(person.program) program working towards a \(person.plan) degree. You can reach..."
- [x] You will need to add "save()  -> Bool" and "load(URL) -> Bool" methods to your data model.  These will be used to load a JSON file from the Sandbox and to write a JSON file to the Sandbox.  They return true if the operation worked or false if it didn't.
- [x] You will also need to be able to parse the ece564class.json file attached below, so download and copy into your project file. 
- [x] Follow the following logic in your code to ensure we can test correctly:
    - [x] You will check to see if the JSON file is already in your Sandbox.
    - [x] If the file exists, you call the load() method with the URL to the file.
    - [x] If the file does not exist, you call the load() with the URL for ece564cohort.json (attached below).  Do an immediate save() after loading to ensure you now have a file in the Sandbox.


## View / Controller
You will be adding a very simple View.  We will call it the "DukePersonView".  It will be managed by the file "DukePersonVC", which you will create.  For this you will need to create the "DukePersonVC" View Controller and an .xib for the View.  Do NOT use a Storyboard, straight code, or SwiftUI - this View must be in an .xib. 

- [x] Create the ViewController file and the .xib by choosing New->File, Cocoa Touch Class, enter Class name ("DukePersonVC"), subclass of UIViewController and make sure you select "Also create XIB file".
- [x] Add to your new  ViewController  a property for storing a DukePerson.
- [x] The View has only 3 required fields - a UIImageView, a multi-line UILabel and a UIButton.  You can add more if you want, plus color, gradients, font changes - anything you want. 
- [x] The UIImageView will show the picture of the person, the UILabel will contain their description field, the UIButton with return to the previous View.
- [x] For now, we will just have one way to launch the DukePersonVC - when the results of a find() operation returns 1 object.  So a find(DUID) or a find(ln, fn) that has only 1 element in the returned array.  Once you get the DukePerson back from the find(), you will create an instance of DukePersonVC(), update the DukePerson property in the instance, then launch the new VC with the .present method as I did in this weeks lecture. 
- [x] The DukePersonVC will then show the picture and the description field


## Other
- [x] Change the name and bundle of your app to your FIRST NAME.  You can do this by just clicking on the current name under "Targets" and typing over it.  For the Bundle ID, leave the root alone ("edu.duke.netid") but change the name to match the new target name.  This will allow me to load all the apps and know who is who.
- [x] Create a nice AppIcon for your app.  Use any image tool to create a .png that is 1024x1024.  Drag the file into the "AppIcon" area in "Assets.xcassets"








# HW1 - Simple App with Data Model

Due: Thu Sep 7, 2023 11:00am

## Extras
1. **Algorithms - Efficient Data Storage**: By using a dictionary to store `DukePeople`, you've optimized the data structure for quick lookup times. Especially when utilizing `duid` as a key, we can fetch a duke person's data in constant time, making the search process swift and efficient.
2. **Branding and Identity**: To give the app a sense of belonging and identity, I incorporated the app title and the official Duke University logo. This not only aligns with Duke's branding but also reinforces the app's primary purpose to users. 
3. **Encapsulation in Data Structures**: I integrated a compareUpdate function directly within the `DukePerson` object, demonstrating my understanding of encapsulation in Object-Oriented Programming. This function enables a seamless comparison of different `DukePerson` info dictionary, enhancing data integrity and consistency.
4. **User Interface Enhancements**: Recognizing the importance of aesthetics in user engagement, I meticulously refined UI elements such as color, weight, and font to make it visual appeal.
5. **Configuration Functions**: To streamline codebase, we configure UI elements like buttons with designed functions, making the code clean and maintainable.
6. **Validation Functions**: Prioritizing data integrity and security, I implemented validation functions to prevent potential errors and bolstering security against malicious or unintended inputs.
7. **Detailed Messaging**: I incorporated detailed messages throughout the app to keep users informed and guide their actions. 
8. **Extensive Testing**

## Guidance

The goal of HW1 is to get your first exposure of using Swift and Xcode to create an application. In a traditional iOS app, the design pattern is MVC - Model, View, Controller.  These first two homework are going to focus on the Model (the data) with a simple Controller and a simple View.  Here are the steps to perform:

### Model
- [x] You are going to create a data Model to store information about people. For this HW1, we will NOT be saving the information permanently - it is just in memory for now.
* Specifics in the data model are in the attached file - "HW1 Spec"
- [x] The Duke Unique ID (DUID) will be the "key" in the database we will create. That is, once information is associated with this key you can change the information and it will update the record with this key.
- [x] The Model will center around a struct we will call DukePerson. You could also make DukePerson a class, but I recommend struct *(I use class)*. 
- [x] Your DukePerson object must support the CustomStringConvertible protocol as the way to display the output text.  The spec contains what this output text should look like.
- [x] Get into good code hygiene practices from the start by organizing your code in Xcode Groups and Files. For example, have a Model group that has  a DataModel.swift for your data model and a DataStructures.swift for your data objects (struct, class, enum).   You will be reusing these in future homework so if you separate your code properly it is easy to move a file from one Project to the next.
- [x] Another good coding practice I suggest you to follow is to contain all methods that act on the data to be contained in a data object. Think of these as methods inside a structure or class that also contains the Array of your DukePerson entries. The methods of add, update, find, etc. could be contained in your data model object.

### Controller
- [x] You will use **ViewController.swift** for your controller code.  This is what drives the View.
- [x] The ViewController.swift should be in its own Xcode Group, "Controller"
- [x] Much of the code will go in viewDidLoad(), much like I showed in this weeks lecture repository.
- [x] As a matter of fact, feel free to reuse as much of my sample code as you want - it should make building the View that much easier.
- [x] Add other methods to the ViewController as needed.  If you create utility functions that are general and not specific to controlling a View, you may want to consider putting them in a different file, like "Utilities.swift"
- [x] Every action taken against the database needs to somehow show a result to the user via the View.  For example, if the person is not found, then the message should say "Not Found".  If it is found, then show the .description information in the TextView.  If "find" results in several people, then print all the info in the TextView.  "List" has its own format, so does not use .description output.
- [x] ADDITION:  On an "update", the Controller should first do a "find", then update only those fields the user changed before calling the update API.  The update API in the spec is still correct - it will replace the entire DukePerson.

### View
- [x] I tried to keep the View as simple as possible so that you see how to build a simple User Interface in iOS but don't need to spend much time on it. This View will be replaced later by a SwiftUI version.
- [x] I also tried to make it so you can reuse various subViews from my sample code by simply moving their frame and changing the properties and handler method.
- [x] Try not to make your View look exactly like mine - change up colors, fonts, background, layout, etc.
- [x] The View will drive calls to the data model methods - Add, Delete, Update, Find, List. 
- [x] Remember, DUID is required for Add, Delete and Update, it is optional for Find (depending on which Find you do, and is not needed for List.
- [x] You need to provide an interface to each of the methods described in the spec.  You can offer additional functions to the user for extra points.
- [x] Make sure you have a Help button to show the syntax of the parameters the user has to type, especially if you add features / functions that I don't have.
- [x] Remember you can add function to your version for extra points, but you must support everything as described in the spec.
- [x] Here is how I do it (tokens with a comma between them):
        fn=Ric, ln=Telford, em=ric.telford@duke.edu, fr=Chatham County, ge=Male, ro=Professor


## HW1 Spec

You will also need to create an object (class or struct) for the DukePerson object. The only required elements are DUID and description. You should put default values in for the others if not specified. For example, “firstname” for fName, “unknown” for email or from, etc. Over time we will add more elements to DukePerson. For HW1, it needs to contain at least:
```
let DUID: Int
var fName: String
var lName: String
var email: String
var from: String
var gender: Gender
var role: Role
var description: String
```
### Protocols
You need to support the `CustomStringConvertible` protocol and the output from the description property must match this format (including possessive and pronoun words):
```
Ric Telford is a Professor. He is from Pittsboro, NC. You can reach him at ric.telford@duke.edu.
```

For Gender of “Unknown” or “Other” you can use “They”, “Their” and “Them”

### Methods
Implement the following methods in your Data Model. The methods need to match these signatures exactly, as we will be creating a test suite that matches these interfaces:
```
func add(_ newPerson: DukePerson) -> Bool {}
```
If the "newPerson.DUID" is not already in the database, add newPerson to the
database and return true. Otherwise return false.
```
func update(_ updatedPerson: DukePerson) -> Bool {}
```
Looks for the "updatedPerson.DUID" in the database. If found, replaces that
entry, and returns true. If not found, then adds "updatedPerson" to database and
returns false.
```
func delete(_ DUID: Int) -> Bool {}
```
Looks for "DUID" entry in database. If found, remove the entry from the
database and return true. If not found, return false.
```
func find(_ DUID: Int) -> DukePerson? {}
```
Searches for an entry with "DUID". If found, returns the info as an Optional DukePerson. If not found, returns nil.
```
func find(lastName lName: String, firstName fName: String = "*") -> [DukePerson]? {}
```
Finds all the people in the database that match the given lastName and firstName. The firstName parameter is defaulted, so you can also call the method with just the lastName. If “*” is specified for both lastName and firstName, return everyone in the database. If no matches found, returns nil
```
func list() -> String
```
Returns a formatted list of all entries in the database, for example “1. Ric Telford, Professor, ric.telford@duke.edu – 0664541”
