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
      
