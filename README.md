# edX First iOS App

## Starting App Development

### Create your first app

1. Open Xcode
2. Create a new Xcode project
3. Choose a template
    - platform: iOs
    - Application: App
    - Next
4. Choose options
    - Project Name: FirstApp
    - Organization Identifier: jin
    - Interface: Storyboard
    - Language: Swift
    - Uncheck all
    - Next
5. Choose folder
    1. Choose or create folder
    2. Uncheck Create Git repository on my Mac
    3. Create
6. Change the preview device
    1. Click Main.storyboard on the navigator
    2. option + cmd + return
    3. Click '+' on the botton
    4. Choose iPhoneSE 3rd
    5. option + cmd + return
7. Add a button to Main.storyboard
    1. Click Main.storyboard
    2. Click '+' (Library) button on the top
    3. Drag Button into Storyboard
    4. Modify the button
8. Show ViewController.swift on the right editor
    1. Click Add Editor button on Right on the top of editor
    2. Click ViewController.swift
    3. Close Main.storyboard on the Right Editor
9. Add controller for the button
    1. ctrl + drag the button to line 16 on ViewController.swift
    2. On the popup
        - Connection: Action
        - Object: View Controller
        - Name: jinButton
        - Type: UIButton
        - Connect
    3. Type code on ViewController.swift
        - ```swift
          import UIKit

          class ViewController: UIViewController {
              var colourIsYellow = false
              override func viewDidLoad() {
                  super.viewDidLoad()
                  // Do any additional setup after loading the view.
                  view.backgroundColor = UIColor.purpleß
              }

              @IBAction func jinButton(_ sender: UIButton) {
                  if colourIsYellow {
                      view.backgroundColor = UIColor.purple
                      colourIsYellow = false
                  } else {
                      view.backgroundColor = UIColor.yellow
                      colourIsYellow = true
                  }
              }
          }
          ```
10. Play the app on Simulator
    1. Choose iOS, iPhone 8
    2. Click Start the active scheme

### Create your first app with SwiftUI

1. Open Xcode
2. Create a new Xcode project
3. Choose a template
    - platform: iOs
    - Application: App
    - Next
4. Choose options
    - Project Name: FirstAppSwiftUI
    - Organization Identifier: jin
    - Interface: SwiftUI
    - Language: Swift
    - Uncheck all
    - Next
5. Choose folder
    1. Choose or create folder
    2. Uncheck Create Git repository on my Mac
    3. Create
6. Preview
    1. Click `Resume`
    2. Choose a device on the toolbar
    3. Change code to 'hello, Jin' on `ContentView.swift`
7. Add a button and the action
    1. Remove `Text().padding()` from `ContentView.swift`
    2. Click '+' (Library)
    3. Drag Button to the location of `Text`
    4. Change the text to `Button("Our MOOC") {`
    5. Click '+' (Library)
    6. Type `vertical stack` and drag it to above the Button
    7. Move the Button into `VStack {}`
    8. Create a varibale and add action
    9. Add an image
        1. Download an image
        2. Click `Assets.xcassets`
        3. Drag the image to it
        4. Click `ContentView.swift`
        5. Click '+' (Library)
        6. Drag `vertical stack` into condition
        7. Click '+' (Library)
        8. Drag `image` into the `VStack`
        9. Copy the image name and paste into `Image("filename")`
        
- ```swift
  import SwiftUI

  struct ContentView: View {
      @State private var theMOOC = false
      var body: some View {
          VStack {
              Button("Our MOOC") {
                  self.theMOOC.toggle()
              }
              if theMOOC {
                  VStack {
                      Image("floral-welcome-sign")
                          .resizable()
                          .scaledToFit()
                      Text("Welcome to the MOOC!")
                          .font(.largeTitle)
                  }
              }

          }


      }
  }

  struct ContentView_Previews: PreviewProvider {
      static var previews: some View {
          ContentView()
      }
  }
  ```

### Hello World

#### On Terminal

1. Open terminal

- ```
  swift
  print("Hello World")
  :exit
  ```

#### On Playground

1. Open Xcode
2. File / New /Playground
3. iOS / Blank / Next
4. FirstPlayground / Create
5. Remove all code except `inport UIKit`
5. Enter `print("Hello World")`
6. Click play botton below the line
7. Result will appear in the bottom of screen

### Constants and Variables

- Variable: store a value in memory
    - var <variable_name> = <variable_value>
- Constant: store a value that won't change, in memory
    - let <constant_name> = <constant_value>

### Data Types

- Defining a variable's data type to be stored in a variable happens when carting it
    - var <varibale_name>: <data_type> = <varible_value>
    - |Type Name|Symbol|Purpose|Example|
      |---|---|---|---|
      |Interger|Int|For whole numbers, integers|4|
      |Double|Double|Numbers with decimal points|4.6|
      |Boolean|Bool|True or False|true|
      |String|String|Text|"Here"|

### Operators

- Are symbols, singular or combined, that allow you to check, change or combine values
    - |Operator Name|Symbol|Purpose|Example|
      |---|---|---|---|
      |Assignment| = |Assign a value to a variable|Greeting = "Hello"|
      |Addition| + |Add the values together|25 + 25 = 50|
      |Subtraction| - |Subtract the values|22 - 11 = 11|
      |Multiplication| * |Multiply the values together|4 * 7 = 28|
      |Division| / |Divide the values|12 / 4 = 3|
      |Remainder|%|Returns the remainder of dividing the numbers|12 % 5 = 2|
      
## Control Flow and Advanced Variables

### if-else

- ```
  if <condition> {
    <code to execute when condition is true>
  } else {
    <code to execute when condition is false>
  }
  ```

### Logical Operators

- |Operator|Description|
  |---|---|
  | == |The items must be equal to each other|
  | != |The values must not be equal to each other|
  | > |The value on the left is greather than the value on the right|
  | >= |The value in the left is greather than or equal to the value on the right|
  | < |The value on the left is smaller than the value on the right|
  | <= |The value on the left is smaller than or equal to the value on the right|
  | && |AND - the condition on the left must be true AND the condition on the right must be true|
  | &#124;&#124; |OR - the condition on the left must be true OR the condition on the right must be true|
  | ! |NOT - the opposite of the conditional statement immediately following the operator is returned|
  
### Switch

- ```
  var numberOfSiblings: Int = 2
  switch numberOfSiblings {
  case 0:
    print("only child")
  case 1:
    print("A single sibling")
  case 2:
    print("Two siblings")
  default:
    print("Wow...")
    
  // result: "Two siblings"
  ```

- Comparison Range

  - `...` or `..<`
  
    - case 0..<2: // equal to 0...1
    
### Collecgions

#### Array

- An ordered list of data of the same type

  - `var myIntegerList: [Int] = [1,2,3,4]`
  
- Data in an array is accessed by its index number

  - `print(myIntegerList[0] // returns 1`
  
- Operations that can be performed upon an array

  - |Operation name|Description|
    |---|---|
    |<array_name>.contains(x)|If x is in the array, returns true else false|
    |<array_name>.isEmpty|Returns true if array is empty, otherwise returns false|
    |<array_name>.append(x)|Appends x to the end of the array|
    |<array_name>.insert(x, at:y)|Inserts x into the array at position y|
    |<array_name>.remove(at:y)|Removes the item at position y in the array|
    |<array_name>.removeLast()|Removes the last item in the array|
    |<array_name>.removeAll()|Removes everything from the array|
    
#### Dictionary

- An unordered collection, and there is a key and a value

  - `var myDictionary = ["Name": "Jin", "Age": 20]
  
- Accessing a Key's value is done using if-let

  - ```
    if let age = myDictionary["Age"]{
      print(age)
    }
    ```
    
  - This ensures that the key exists before attempting to do anything with a value

- Changing a Dictionary

  - ```
    myDictionary["Age"] = 22 // replace the value if the key exists
    myDictionary.updateValue(39, forKey: "Age") // update
    myDictionary.removeValue(forKey: "Age") // remove
    ```    

### for-in

- Allows us to repeat something that is in a sequence or range or collection

  - ```
    for num in 10...15{
      print("Number is: \(num)")
    }
    /* return
     * Number is: 10
     * Number is: 11
     * Number is: 12
     * Number is: 13
     * Number is: 14
     * Number is: 15
     */
     
    var lectures = ["David", "Paul", "Andrew"]
    for lecture in lectures{
      print("Lecturer is: \(lecturer)")
    }
    /* return
     * Lecturer is David
     * Lecturer is Paul
     * Lecturer is Andrew
     */
     
    var ages = ["David": 20, "Paul": 30, "Andrew": 40]
    for person in ages{
      print(person)
      print(person.key)
    }
    /* return
     * (key: "Andrew", value: 40)
     * Andrew
     * (key: "Paul", value: 30)
     * Paul
     * (key: "David", value: 20)
     * David
     */
    ```

### while

- Keeps looping until a condition is met

  - ```
    var points = 5
    var numberOfServes = 1
    while points < 50 && numberOfServes < 3{
      print("Playon, points = \(points)")
      points = points * 2
      numberOfServes = numberOfServes + 1
    }
    /* return
     * Playon, points = 5
     * Playon, points = 10
    */
		```

## Xcode

- Create a new project

	1. Choose a template
		- iOS / App / Next
	2. Choose options
		- Product Name: TextChanger
		- Interface: Storyboard
		- Language: Swift
		- Next
	3. Choose a folder / Create
	4. Check the created project
		- Build Settings
			- Swift Language Version
			
- Navigation area (the left-hand side)

	- You can check files and the project structure
	
- Editor area (the middle)

	- We will see our code and do a while lot of things
	- On the top, there are 'Enable Code Review', 'Adjust Editor Options', and 'Add Editor on Right'
	- When you hold option key, the button will change to Add Editor Below
	
- Utility area (the right hand side)

	- options depending on what is selected
	- On the top, there are 'Show the File Inspector', 'Show the History Inspector', and 'Show Quick Help Inspector'

- Toolbar (the top)

	- On the right side, there are 'Library', 'Show or Hide Code Review', and 'Hide or Show the Inspector'
	- On the left side, there are 'Hide or Show the Navigator' and 'Start the active scheme'
	- On the middle, there are Project Name and Device
		- You can choose a device for 'Start the active Scheme'
		- You can connect iOS device via cable or wirelessly, and the connected device will show
		
- `Main.storyboard`

	- We can preview our device on the Editor area
	- On the toolbar, change the device and click the 'Start the active scheme' button
		- Simulator of the changed device will be created
		- On the menu bar, you can handle the simulator on the device tab

- `Assets.xcassets`

	- This is used to store things in it
	
- `Info.plist`

	- It contains the properties and setting of the app

## Pair iOS device with Xcode

1. Choose Window > Devices and Simulators, then in the window that appears, click Devices.
2. Connect the iOS device to your Mac with a lightning cable.
3. Note: The first time you connect an iOS device to your Mac, you may need to click Trust on the device to continue.
4. In the left column, select the device.
5. In the detail area, select Connect via network.
6. Xcode pairs with the iOS device.
7. Disconnect the lightning cable.
- In the left column, a device that is connected (using a lightning cable or over the network) appears under Connected. If a network icon appears next to the device, the device is paired and it is safe to disconnect the lightning cable.

- Error: Xcode "Device Locked" when iPhone is unlocked
	1. Unplug device
	2. Quit Xcode
	3. Open Xcode
	4. plug in device

- Error: Signing for "..." requires a development team.
	1. Add you Apple ID in Xcode 
		- On menu bar, Xcode > Preferences > Accounts > Add Apple ID
	2. Choose your project > Choose a target > Click Signing & Capabilities tab
		- Check Automatically manage signing
		- Choose Team

- Untrusted Developer on iPhone
	- Settings > General > VPN & Device Management > Select Developer App > Trust
 
## Interface Builder

- .storyboard files:

	- contain parts of the interface
	- define the layout of one or many screens
	- the moving from one screen to another

### Elements position center on different devices and the rotation

- `Main.storyboard`

	1. Click '+' (Library), and add Button and Label
	2. Select Button on the preview
		1. Click "Show the Attribute Inspector" on the right hand side
		2. Change the Title to 'TextChange'
		3. Click "Align" on the bottom of the preview
		4. Check "Horizontally in Contianer" and "Vertically in Container"
		5. Click "Add 2 Constraints"
		6. Change the device on the bottom of the preview and test it
		7. Click the "orientation" on the bottom of the preview and test it 
	3. Select Label on the preview
		1. Click "Add New Constraints" button on the bottom of the preview
		2. Click the red line below the black box in the middle to select the Spacing to nearest neighbor, and uncheck "Constrain to margins"
		3. Click "Add 1 Constraint" button
		4. Click "Align" on the bottom of the preview
		5. Check "Horizontally in Container"
		6. Click Add 1 "Constraints"
	4. You can check added Constraints on View Controller Scene > View Controller > View > Constraints
	5. You can check what is the scene by click "Show the Identity Inspector" on the right hand side

### Add the button action

1. Control + click the button on the storyboard and drag the bottom to line 16 (between the last two brackets) on `ViewController.swift`
2. Change the type to "UIButton"
3. Name: textChange
4. Click Connect
5. Control + click the label on the storyboard and drag the bottom to line 11 (under the UIViewController line) on `ViewController.swift`
6. Name: theMessage
7. Click Connect
8. Type `print("You pressed the button!")`
9. When you click the button, you can see the text appear at the bottom of your screen, in the debug area
