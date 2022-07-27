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
