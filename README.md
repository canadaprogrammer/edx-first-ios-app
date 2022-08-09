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

- ```swift
  swift
  print("Hello World")
  :exit
  ```

#### On Playground

1. Open Xcode
2. File / New /Playground
3. iOS / Blank / Next
4. FirstPlayground / Create
5. Remove all code except `import UIKit`
6. Enter `print("Hello World")`
7. Click play botton below the line
8. Result will appear in the bottom of screen

### Constants and Variables

- Variable: store a value in memory
  - `var <variable_name> = <variable_value>`
- Constant: store a value that won't change, in memory
  - `let <constant_name> = <constant_value>`

### Data Types

- Defining a variable's data type to be stored in a variable happens when carting it
  - `var <variable_name>: <data_type> = <variable_value>`
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

- ```swift
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

- ```swift
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
    - `case 0..<2: // equal to 0...1`

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

  - ```swift
    if let age = myDictionary["Age"]{
      print(age)
    }
    ```

  - This ensures that the key exists before attempting to do anything with a value

- Changing a Dictionary

  - ```swift
    myDictionary["Age"] = 22 // replace the value if the key exists
    myDictionary.updateValue(39, forKey: "Age") // update
    myDictionary.removeValue(forKey: "Age") // remove
    ```

### for-in

- Allows us to repeat something that is in a sequence or range or collection

  - ```swift
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

  - ```swift
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
8. Type action code

   - ```swift
     theMessage.text = "I'm an app developer"
     print("You pressed the button!")
     ```

9. When you click the button, you can see the text appear at the bottom of your screen, in the debug area

## Developer Documentation

- Hover over the UIlabel
- While you've got the Option key down, a question mark appears
- Click the question mark
- The developer documentation has ginve you a brief summary
- Click "Open in Developer Documentation"

## Debugging

- Compiler Errors
  - When the run button is clicked, Xcode takes the code you wrote, combines it with the code in things such as UILabel & creates an executeable file
  - This is called comiling your code
  - The executable file is what runs on the device
  - When the code can't compile, a compiler error occurs
  - These usually occur when the written code has an error in it
- Run time Errors
  - These are what are really referred to as Bugs
  - The code compiles without errors and starts executing
  - While running the code stops or crashes
  - This is where the code did something it wasn't meant to and can't continue on
  - Most of use have experienced these when using software, and they avr frustrating for both users and developers
  
## Exercise

### Change Label

- ```swift
  //
  //  ViewController.swift
  //  TextChanger
  //
  //  Created by Jungjin Park on 2022-07-30.
  //

  import UIKit

  class ViewController: UIViewController {

    @IBOutlet weak var theMessage: UILabel!
    @IBOutlet weak var counterDisplay: UILabel!

    var iAmADeveloper : Bool = false
    var counter: Int = 0

    override func viewDidLoad() {
      super.viewDidLoad()
      // Do any additional setup after loading the view.
    }

    @IBAction func textChange(_ sender: UIButton) {
      counter = counter + 1
      if !iAmADeveloper{
        theMessage.text = "I'm an app developer"
      } else {
        theMessage.text = "I'm going to be an App Developer!"
      }
      iAmADeveloper = !iAmADeveloper

      print("You coded the button press!")
      counterDisplay.text = "Counter: \(counter)"
    }
  }
  ```

### Change background color depending on user input

- ```swift
  //  ViewController.swift
  //  TextChanger
  //
  //  Created by Jungjin Park on 2022-07-30.
  //

  import UIKit

  class ViewController: UIViewController {

    @IBOutlet weak var theMessage: UILabel!
    @IBOutlet weak var enteredColour: UITextField!

    var userInput : String = ""

    override func viewDidLoad() {
      super.viewDidLoad()
      // Do any additional setup after loading the view.
    }

    @IBAction func textChange(_ sender: UIButton) {
      enteredColour.resignFirstResponder()
      userInput = enteredColour.text!
      switch userInput{
      case "blue":
        view.backgroundColor = UIColor.blue
      case "green":
        view.backgroundColor = UIColor.green
      case "yellow":
        view.backgroundColor = UIColor.yellow
      case "orange":
        view.backgroundColor = UIColor.orange
      default:
        theMessage.text = "It's an unknown colour entered."
      }
    }
  }
  ```

### Temperature Converter

- ```swift
  import UIKit

  class ViewController: UIViewController {

    @IBOutlet weak var celsiusInput: UITextField!
    @IBOutlet weak var fahrenheitInput: UITextField!
    @IBOutlet weak var convertedValue: UILabel!

    var degreesValue: Double? = 100
    var fahrenheitValue: Double? = 0.0

    override func viewDidLoad() {
      super.viewDidLoad()
      // Do any additional setup after loading the view.
    }

    @IBAction func celToFah(_ sender: Any) {
      fahrenheitInput.text = ""
      if celsiusInput.text != ""{
        view.backgroundColor = UIColor.green
        degreesValue = Double(celsiusInput.text!)

        fahrenheitValue = (degreesValue! * 9/5) + 32
        convertedValue.text = "\(fahrenheitValue!) Fahrenheit"
        print("\(degreesValue!) = \(fahrenheitValue!) in fahrenheit.")
      } else {
        convertedValue.text = "Enter Celsius Value"
      }
    }
    @IBAction func fahToCel(_ sender: Any) {
      celsiusInput.text = ""
      if fahrenheitInput.text != "" {
        view.backgroundColor = UIColor.yellow
        fahrenheitValue = Double(fahrenheitInput.text!)
        degreesValue = (fahrenheitValue! - 32) * 5/9
        convertedValue.text = "\(degreesValue!) Degrees"
        print("\(fahrenheitValue!) = \(degreesValue!) in degrees.")
      } else {
        convertedValue.text = "Enter Fahrenheit Value"
      }
    }
  }
  ```

## Functions

- Functions are blocks of code that can be run over and over again to do the same things
- They saves us writing out code over and over again, possibly introducing transcription errors
- Functions should do one thing. If we want to do two things, we can write two functions
- A function has two important components
  1. The function definition, where we specify what the function does.
     - A function definition has four components: name, input parameters, output return values and the body
     - The function body is what turns the inputs into the outputs.
     - `func functionName (InputParameters) -> OutputReturnType { // FunctionBody }`
  2. The function call, where we execute the function
     - `functionName()`

### Function Parameters

- They allow us to specify the name, type and quantity of data that will be processed by the function body.
- When we call the function, we can apply the same steps to different data
- There are three board situations to consider:
  - functions with no input parameter
    - definition: `functionName() {}`
    - call: `functionName()`
  - functions with one input parameter
    - definition: `functionName(parameter: type) {}`
    - call: `functionName(parameter: value)`
    - We must specify a name for the parameter that describes its purpose
    - The parameter becomes a variable we can use within the function
    - We also have to specify the data type of the parameter
  - functions with multiple input parameters:
    - definition: `functionName(firstParameter:dataType, secondParameter:dataType) {}`
    - call: `functionName(firstParameter: value, secondParameter: value)`
    - a function should only do one thing; if we have too many (approx. > 6) parameters, it is likely doing to much
- Default Parameter Values
  - When calling the funciton, we don't have to specify all the parameters
  - If we don't we need a default value to use so the function can still run
  - We should have the default parameters at the end of the parameter list
    - This ensures that all calls to the function use the same order for their non-default arguments, and makes it cleear that the same function is being called in each case
  - definitions: `functionName(firstParameter: Int, secondParameter: Int = 10) {}`

### Function Returns

- The value(s) we calculated within the function can be used outside the function
- when calling functions that return, we don't have to have the smae names for the variables storing the returns as within the function
- No reutrns
- One return
  - All that is required is to make the last line of the function start with return, then specify the variable containing the value to return
  - If you return earlier in the function, any lines afterwards will be ignored
  - `return value`
- Multiple returns
  - All we have to do is separate the returns by a comma

- function definition

  - ```swift
    func thisDivides(number: Int) -> (Int, Int) {
      let value1 = number / 2
      let value2 = number / 4
      return (value1, value2)
    }
    ```

- function call

  - ```swift
    var (div_two, div_four) = thisDivides(number: 16)
    print(div_two) // 8
    print(div_four) // 4
    ```

- Exercise: Multiple Returns
  - Define a function called 'calcSumDiff' that for two input parameters 'firstNum' and 'secondNum' will output the sum and the difference of the two numbers.
  - Call your function and store the results in appropriately named variables.
- Then, print the values of these to confirm the function works as intended

  - ```swift
    func calcSumDiff(firstNum: Int, secondNum: Int) -> (Int, Int) {
      let sum = firstNum + secondNum
      let diff = abs(firstNum - secondNum)
      return (sum, diff)
    }

    let result = calcSumDiff(firstNum: 10, secondNum: 12)
    print(result) \\ return (22, 2)
    ```

## Structures

- A Structure contains one or more variables (called properties)

  - ```swift
    struct Person { var anme: string }
    var aPreson = Person(name: "Tim")
    print(aPerson.name)
    // return Tim
    ```

- We can also add methods (functions) to it as well

  - ```swift
    struct Person {
      var name: String
      var age: Int
      var location: String

      func whoAmI() {
        print("Hi, I'm \(name)! I'm \(age) and live in \(location)")
      }
    }
    
    let aPerson = Person(name: "Jin", age: 20, location: "Victoria")
    
    print(aPerson.name) // Jin
    aPerson.whoAmI()   // Hi, I'm Jin! I'm 20 and live in Victoria
    ```

- An `initializer` creates an instance of a structure
  - This involves creating an instance of each property
  - We can specify default values for the properties

  - ```swift
    struct WaterMeter {
      var litersUsed: Int = 0
      var customer: Person = Person(name: "Anonymous", age: 20, location: "Canada")
    }

    let theMeter = WaterMeter()

    print(theMeter.litersUsed)  // 0
    print(theMeter.customer.age) // 20
    ```

- When we specify the values when we create an instance, this is called using the `memberwise initializer`
  - `var aWaterMeter = WaterMeter(literUsed: 10)`
- `Custom Initializer`: In more complicated situations, we may wish to write our own initializer functions

  - ```swift
    struct CarSpeed {
      var kph: Double   // only kph is stored
      init(kph: Double) { // Basic initializer for kph
        self.kph = kph
      }
      init(mph: Double) { // Advaced logic in initializer for mph
        self.kph = mph * 1.6
      }
    }
    var firstSpeed = CarSpeed(kph: 100)
    var sameSpeed = CarSpeed(mph: 60)
    ```

- `Computed Properties`

  - ```swift
    struct CarSpeed {
      var kph: Double
      var nph: Double {
        return kph / 1.6
      }
    }
    ```

- `Mutating Methods`: Added methods to a structure that change the values of the properties
 
  - ```swift
    struct CarSpeed {
      var kph: Int = 0
      mutating func reset() {
        kph = 0
      }
    }
    var myCarSpeed = CarSpeed(kph: 100) // kph is 100
    myCarSpeed.reset()         // kph is 0
    ```

- Type Properties and Methods stay the same for all instances of a structure
  - Add `static` before a property or method

  - ```swift
    struct CarSpeed {
      static var legalLimit = 100
    }
    ```

- `self` simply refers to the current instance of a structure (or other object)
- This allows us to interact with the current instance, for example to set or access its properties

- Exercise: Detailed Person
  - Modify the Person structure such that we also store their favourite food and their height. Choose appropriate data types for these properties.
  - Add a second function to the Person structure named 'foodAndHeight' to output these new properties in a human-readable manner.

- Initialise the Structure you've created, and call your new function to confirm the changes work as intended

  - ```swift
    struct Person {
      var name: String;
      var age: Int;
      var location: String;
      var favouriteFood: String;
      var height: Int;

      func whoAmI() {
        print("Hi, I'm \(name)! I'm \(age) and live in \(location).");
      }

      func foodAndHeight() {
        print("My favourite Food is \(favouriteFood), and I'm \(height)cm tall.")
      }
    }
    let bPerson = Person(name: "Jin", age: 20, location: "Canada", favouriteFood: "Galbi", height: 180);
    bPerson.foodAndHeight() // returns My favourite Food is Galbi, and I'm 180cm tall.
    ```

## Classes

- Classes differ from structures as classes can hoave hierarchical relationship
- Classes can have parents (named superclasses) or children (named subclasses)

- Base Classes don't have a parent

  - ```swift
    class Animal {
      var animalName: String
      var numberOfLimbs: Int
      func makeNoise() {
        //
      }
    }
    ```

- Subclassing allows us to extend an existing class by basing it on an existing class (and its methods and properties)

  - ```swift
    class Dog:Animal {
      var breed: String
      override function makeNoise() {
        print("Woof!")
      }
    }
    ```

- If we add more properties to our subclass, we need to override the initializer as it will only initialize the superclasses' properties

  - ```swift
    class Dog:Animal {
      var breed: String
      init(animalName: String, numberOfLimbs: Int, Breed: String) {
        self.breed = breed
        super.init(animalName: animalName, numberOfLimbs: numberOfLimbs)
      }
    }
    ```

- ```swift
  class Animal {
    var name: String
    var numberOfLimbs: Int

    func makeNoise() {
      // Do nothing!
    }
    init(name: String, numberOfLimbs: Int) {
      self.name = name
      self.numberOfLimbs = numberOfLimbs
    }
  }

  class Cat: Animal {
    var breed: String = ""

    override func makeNoise() {
      print("Meow!")
    }

    init(name: String, numberOfLimbs: Int, breed: String) {
      self.breed = breed
      super.init(name: name, numberOfLimbs: numberOfLimbs)
    }
  }

  let myCat = Cat(name: "Whiskers", numberOfLimbs: 4, breed: "Ragdoll")
  print(myCat.name)
  myCat.makeNoise()

  let myAnimal = Animal(name: "Miscellaneous", numberOfLimbs: 0)
  print(myAnimal.name)
  myAnimal.makeNoise()

  print(myCat.breed)
  ```

- Exercise: Another Animal
  - Create a new Subclass of Animal for a Snake. It should store a true or false value regarding whether it is poisonous, a value of its length as well as ensuring its makeNoise function outputs a 'Hiss'.
  - Ensure that you have define the initialiser for the Snake.

- As snakes can be (for this purpose) considered to have zero limbs, pass the value directly into the superclass initialiser

  - ```swift
    class Snake:Animal {
      var poisonous: Bool = false;
      var snakeLength: Double

      override func makeNoise() {
        print("Hiss")
      }
      init(animalName: String, numberOfLimbs: Int = 0, poisonous: Bool, snakeLength: Double) {
        self.poisonous = poisonous
        self.snakeLength = snakeLength
        super.init(animalName: animalName, numberOfLimbs: numberOfLimbs)
      }
    }
    let aSnake = Snake(animalName: "Bell Snake", poisonous: true, snakeLength: 100)
    let bSnake = Snake(animalName: "Bella Snake", numberOfLimbs: 4, poisonous: true, snakeLength: 100.3)

    aSnake.makeNoise()     // Hiss
    print(aSnake.numberOfLimbs) // 0
    print(aSnake.snakeLength)  // 100.0

    bSnake.makeNoise()     // Hiss
    print(bSnake.numberOfLimbs) // 4
    print(bSnake.snakeLength)  // 100.3
    ```

## Introduction to User Interface Development

### Basic Views

- User Interface Components: Apple's UIKit provides us with the components we can use to make our own
- Views: A view is a visual element that makes up our app
  - We can create text, graphics, lines and more with them
  - Most apps contain screens which are made up of many niews, which create what is termed a view hierarchy
  - Views need a Frame (size and position) first
- UIView: The UIView class is UIKit's foundational class
  - This is subclassed to make many components we can use to build our app's interface
- UILabel: A UILabel allows us to display a piece of short text (in our app) to the user
- UIImageView: It allows us to display an image to the user
- UITextView: It allows a user to interact with multiple lines of test within the app
- UIScrollView: It allows users to scroll
  - The benefit of this is to add and explore content larget than the viewport (screen/window)
  - Scrollbars (or indicators as they termed) only appear when the user scrolls
- UIToolbar: It displays a group of buttons at the bottom of the screen (usually)
  - Buttons (or tools) allow users to perform an action
- UINavigationBar: It can be thought of as the 'title bar' - but isn't the only way to make one
  - It has buttons to navigate through the view hierarchy (back, forwards etc)
  - It looks like it sometimes has other buttons (although they are not implemented using a UINavigationBar)
- UITabBar: It looks similar to a UIToolbar, but serves a different yet similar purpose
  - Rather than performing actions, a UITabBar allows the user to select between views
  - It's used in conjunction with a TabBarController
  - It is best used for when the app has multiple workflows i.e. doesn't just run from start to finish like a 'wizard'

#### Playgounds Basic Views

- in Cocoa Touch
  - Xcode > File > New > Playground > iOS > Single View

  - ```swfit
    //: A UIKit based Playground for presenting user interface

    import UIKit
    import PlaygroundSupport

    class MyViewController : UIViewController {
      override func loadView() {
        let view = UIScrollView()
        view.backgroundColor = .white
        view.contentSize = CGSize(width: 375, height: 1000)

        let label = UILabel()
        label.frame = CGRect(x: 50, y: 200, width: 200, height: 20)
        label.text = "Hello World!"
        label.textColor = .black

        view.addSubview(label)

        let textView = UITextView()
        textView.frame = CGRect(x:50, y:240, width: 200, height: 100)
        textView.text = "Tap to edit me - I'm a TextView!"
        textView.textColor = .black

        view.addSubview(textView)

        self.view = view
      }
    }
    // Present the view controller in the Live View window
    PlaygroundPage.current.liveView = MyViewController()
    ```

- in SwiftUI
  - Xcode > File > New > Playground > iOS > Blank

  - ```swift
    import SwiftUI
    import PlaygroundSupport

    struct Name {
      var firstName: String = ""
      var lastName: String = ""
    }

    struct NameRow: View {
      var name: Name
      var body: some View {
        HStack {
          Text(name.firstName)
          Text(name.lastName).bold()
        }
      }
    }

    struct NameView: View {
      var body: some View {
        Group {
          NameRow(name: Name(firstName: "Jin", lastName: "Park")).offset(x:1, y:0)
          NameRow(name: Name(firstName: "Jina", lastName: "Park")).offset(x:0, y:0)
        }
      }
    }

    PlaygroundPage.current.setLiveView(NameView().padding(150))
    ```

### Basic Controls

- Controls allow us to setup Actions that respond to events (interactions) with the controls
  - An Action is simply a special type of function
- UIButton: It is a control which the user can 'tap'
- UISegmentedCongrol: Think of a UISegmentedControl as a group of buttons where only one can be selected
  - Code is run when the user selects a different button
- UITextField: It is similar to a UITextView or a UILabel
  - In that it allows the user to enter a single line of text - these are properties of those Views
  - Code can also be bound to after each keystroke (use this carefully)
- UISlider: It allows the user to select a continuous value between a lower and upper range
  - As the user drags the slider toggle, code is run, so dragging can trigger an event many times
- UISwitch: They are to controls what Boolean values are to variables
  - Code can run for when the state changes or when it is set to a specific value
- UIDatePicker: It sllows the user to select a date and time
  - Code is executed when date and/or time is changed
- UIViewController: It is not really a control, but a special case view
  - Each screen in an app is usually a scene in Storyboards
  - UIViewControllers manage each view - they contain the Actions and the Storyboards used to generate each screen or scene
  - These are subclassed and overridden to allow us to make our own scenes

#### Playgrounds: Basic Controls

- in SwiftUI
  - Xcode > File > New > Playgrounds > iOS > blank

  - ```swift
    import SwiftUI
    import PlaygroundSupport

    struct AToggle: View {
      @State var isToggled = false
      var offDescription: String
      var onDescription: String
      var body: some View {
        Toggle(isOn: $isToggled) {
          if(isToggled) {
            Text(onDescription)
          } else {
            Text(offDescription)
          }
        }
      }
    }

    struct MainView: View {
      var body: some View {
        VStack {
          Group {
            AToggle(offDescription: "Off 1", onDescription: "On 1")
            AToggle(offDescription: "Off 2", onDescription: "On 2")
          }
          Button(action: {
            print("Tapped")
          }, label: {
            Text("I am a button!")
          })
        }
      }
    }

    PlaygroundPage.current.setLiveView(MainView().padding(150))
    ```

- in Cocoa Touch

  - ```swift
    import UIKit
    import PlaygroundSupport

    class MyViewController : UIViewController {
      @objc func buttonTapped() {
        print("Tapped the button!")
      }
      @objc func datePickerValueChanged() {
        print("Changed value of the date picker!")
      }
      override func loadView() {
        let view = UIScrollView()
        view.backgroundColor = .white
        view.contentSize = CGSize(width: 375, height: 1000)

        let button = UIButton()
        button.frame = CGRect(x:0, y: 20, width: 100, height: 20)
        button.setTitle("Tap Me", for: .normal)
        button.setTitleColor(.blue, for: .normal)
        button.addTarget(self, action: #selector(buttonTapped), for: .touchDown)

        view.addSubview(button)

        let datePicker = UIDatePicker()
        datePicker.frame = CGRect(x:0, y: 0, width: 375, height: 500)
        datePicker.addTarget(self, action: #selector(datePickerValueChanged), for: .valueChanged)

        view.addSubview(datePicker)
        self.view = view
      }
    }
    // Present the view controller in the Live View window
    PlaygroundPage.current.liveView = MyViewController()
    ```

## Auto Layout

1. Xcode > File > New > Project
2. iOS > App > Next
3. Interface: Storyboard, Language: Swift > Next
4. Create
5. Change device to iPhone8
6. On `Main.storyboard`
   1. Change the preview device to iPhoneSE
   2. Centered button
      1. Click Library on the toolbar (the top)
      2. Add a button on the middle
      3. Align > Check Horizontally in Container and Vertically in Container > Click Add 2 Constraints
      4. Add New Constraints > Set 20 on each side > Click Add 2 Constraints
   3. Warning - Fixed leading and trailing constraints with a center constraint may cause clipping
      1. On Size Inspector > remove Horizontal center constraint
         1. Click Horizontal Center Constraint
         2. Pushing delete button
      - When constraints have issues, solving methods
        - Modifying Constraints form the Size Inspector on the Utility Area
        - Clicking Resolve Auto Layout Issues on the bottom of the preview to change the constraints to fit the object
        - Clicking Update Frames on the bottom of the preview to change the object to fit the constraints
   4. Stack View
      1. Add a label on the top center from library
      2. Warning - Views without any layout constraints may clip their content or overlap other views
         1. Align > Check Horizontally in Container > Add 1 Constraint
      3. Warning - Vertical position is ambiguous for "Label"
         1. Add New Constraints > Choose Safe Area on the top > Add 1 Constraint
      4. Add a label below the label and change the Label to "Second Label"
      5. Add New Constraints > Type 20 on the top > Add 1 Constraint
      6. Warning - Horizontal position is ambiguous for "Second Label"
         1. Align > Check Horizontally in Container > Add 1 Constraint
      7. Add Third Label as same as the Second Label
         1. Change the font to System 40
      8. Select the three labels with Shift key
      9. Editor on the menu bar > Embed In > Stack View
      10. Align > Check Horizontally in Container > Add 1 Constraint
      11. Add New Constraints
          1. Choose Safe Area at the top
          2. Type 100 at the bottom
          3. Add 2 Constraints
      12. On Attribute Inspector of Stack View
          1. Axis
          2. Alignment (Vertically)
          3. Distribution (Horizontally)
          4. Spacing
          5. Click '+' (Add Variation) next to Spacing for iPad
             1. Width: Regular
             2. Height: Regular
             3. Click Add Variation
      13. Click layout at the bottom of the preview
          1. You can test it on Full Screen or Split View
      14. On Attribute Inspector of label
          1. Click '+' (Add Variation) next to Drawing for iPad
             1. Width: Compact
             2. Height: Regular
             3. Click Add Variation
             4. Check Hidden
             5. You can check it on layout at the bottom of the preview

## Scenes

- A scene is simply 'one thing' we can do in our app that is described by 'one screen'
- Complex apps will require multiple scenes to be able to deliver the required functionality

### Segues

- A `segue` defines how a new ViewController appears over the previous ViewController
- We can also use `segues` to dismiss View Controllers to move back to previous ones, and these are termed `modal segues`.

### Triggers

- Segues can be triggered either using the Interface Builder or programmatically using Swift code
  - We generally connect the trigger to a control such as a button, so the segue is triggered when the user taps the button

### Unwinding

- Dismissing a segue is termed `unwinding` it
  - We can't really do this using Interface Builder
  - We do this programmatically by creating an `IBAction` function that takes a `UIStoryboardSegue` parameter
  - We then need to connect the IBAction to a control, which we will do in the exercise

### Navigation Controllers

- Using a Navigation Controller we can push a new ViewController on top of the stack with a push transition

### Navigation Bars and Items

- This can be cusstomised visually in Interface Builder, keeping in mind the Human Interface guidelines
- The Navigation Bar is implemented ad a `UINavigationBar`
- To customize what the bar says, we need to modify the Navigation Item within our View Controller
- We can customize the style by modifying the attributes of the Navigation Bar

### Passing Information

- Generally, we will need to pass information between View Controllers
  - This is despite changing View Controllers to a different `task`, as it is still part of a larger workflow
- We override the prepare function to setup data for transfer during a segue
- The prepare function is how we programmatically define a segue

## Tab Bar Controllers

- Tab Bar Controllers are commonly seen in many apps to separate different workflows within an App
- To add a Tab Bar Controller in Interface Builder, we drag it onto the Canvas from the Object library
- To add a tab, we drag it from the Object library into our TabBarController
- Each of these tabs is termed a Tab Bar Item
- Tab Bar Item has a Label and an Image
  - We can use a bunch of built-in icons or supply our own
- We can customise the look and feel further using Swift code

## ViewController Event Handling

- Life Cycle States
  - A View Controller can be in one of the following states:
    - View not loaded
    - View appearing
    - View appeared
    - View disappearing
    - View disappeared
- View Did Load
  - The most common function is viewDidLoad, which runs when the View Controller is loaded
  - Generally this function is used to programmatically initialise the View Controller
    - Set up values, connect to resources, etc.
- Overriding
  - One think to be aware of is that as we are overloading each of these functions, you must call the superclass initialiser within them when you do so

  - ```swift
    override func viewWillAppear(_animated: Bool) {
      super.viewWillAppear(animated)
      // you write your code here
    }
    ```

- Function with `will` run before the event, whereas functions with 'did' run afterwards

## Navigation Hierarchy

### Hierarchical Navigation

- A user makes one choice per screen/scene until they reach their destination scene
  - If they change destination, they have to start from the beginning, retracing their steps back to the start
  - Used in apps such as Settings
- Generally implemented with Navigation Controllers

### Flat Navigation

- Users can switch between different categories or 'workflows'
- Ganerally implemented with a Tab Bar Controller

### Content-Driven Navigation

- This is a different and more free-flow type of navigation
- Users can move in a non-linear fashion between elements of the App
  - The most common example would be games

### Workflows

- It is best to consider what the User will be doing in the App before building it
  - This is to be able to best design the navigation hierarchy
  - Consider the features and how they will be built as View Controllers, as well as the movement between them

### Design Guidelines

- Apple recommend the following things to consider when designing a Navigation Hierarchy
  - Design a structure to make it fast and easy to get to content
  - Use standard navigation controls, such as a Navigation Bar when implementing a Hierarchical Navigation
  - Use a Tab Bar when implementing multiple categories (modes, workflows) of content or functionality
  - Use the correct style (modal va push) where appropriate

## Errors

### "this class is not key value coding-compliant for the key counter"

- This means there was somthing called 'counter' which it can no longer find.
- It's because I changed the label name after connect it from 'counter' to 'counterDisplay'
- Solution:
  1. Click the label on `Main.storyboard`
  2. Control + drag the label to the 'counterDisplay' on `ViewController.swift`
  3. Click "Show the connection inspector" on the Utility Area (the right hand side)
  4. You can see there are two connections on Referencing Outlets
  5. Remove 'counter' from it
