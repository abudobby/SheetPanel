# SheetPanel
Reusable Bottom Sheet Panel Component


## Getting Started

Download the project and drag the SheetPanel framework into your workspace. Try out the sample app to play around with some of the configurations. 


## Usage

```swift
import SheetPanel

let sheetVC = SheetPanelViewController()

....
override func viewDidLoad() {
        super.viewDidLoad()   
        sheetVC.titleLabel.text = "Title"
        sheetVC.subtitleLabel.text = "Subtitile"
        sheetVC.layout = Layout(withPositions: [.dismissed, .collapsed, .expanded])
        sheetVC.addPanel(toParent: self)
        sheetVC.set(contentViewController: ContentViewController())
         }
         
  override func viewDidAppear(_ animated: Bool) {
        super.viewDidAppear(animated)
        
        sheetVC.openSheet()

    }
```
## Configure

SheetPanelViewController is a drop in Bottom Sheet view that is configurable. Instantiate the controller and a few lines of code later, you are up and running :) 

### Title and Subtitle ###
```swift
public var titleLabel: UILabel
public var subtitleLabel: UILabel

```
Configure the title and subtitle once you instantiate the controller. 

### Layout ###
```swift
public var layout: Layout

sheetVC.layout = Layout(withPositions: [.dismissed, .collapsed, .expanded])
```
Every sheet requries a layout to configure the states. A default layout is created if none is provided. Use this to configure the various scroll positions of SheetPanelViewController. 


### Sheet Position States ###
```swift
public enum SheetPosition : Double
```
* ```.dismissed ```
 Sheet not active on screen
 
 * ```.collapsed ```
 Sheet is at a third of the screen from the bottom
 
 * ```.expanded ```
 Sheet is expanded to 90% of the screen from the bottom
 
 You can have all of these states in any order you desire. 
     
  






## API Methods

### Set content ###
```swift
 public func set(contentViewController: UIViewController)
```
Sets the view controller responsible for the content portion of a sheet. Attach any viewcontroller to this to show your content in the sheet.

### Add Panel ###
```swift
public func addPanel(toParent parent: UIViewController) 
```
Adds the view managed by the sheet controller as a child of the specified view controller.

### Open Sheet ###
```swift
public func openSheet()
```
Opens SheetPanelViewController to the inital set position

### Move ###
```swift
public func move(to position: SheetPosition, animated: Bool = true)
```
Moves SheetPanelViewController to a specific position in parentViewController with animation.

## Delegates

```swift
public protocol SheetPanelDelegate: AnyObject {
  
    func SheetViewPanel(didOpen atPosition: SheetPosition)
  
    func SheetViewPanel(didChangeTo position: SheetPosition)
}

```
### Did Open Sheet to initial position ###
```swift
  func SheetViewPanel(didOpen atPosition: SheetPosition)
```
Called everytime the sheet is opened for the first time. 

### Sheet did change position ###
```swift
  func SheetViewPanel(didChangeTo position: SheetPosition)
```
Called everytime the sheet changes position return the current position

## Testing
I built this component with simplicity in mind. By having the sheet be configured via a layout model, it allows for better testing. To expand on this idea, many of the methods inside the main controller can be refactored into a model to make testing easier. Given more time, I'd probably also use Apples new Combine Framework to keep track of the states to make the component more asynchronous in nature. 

## Future Enhancements
So far the beauty of this component is the simplicity of having the standard positions states. A future enhnacement to further configure this would be to allow the developer to choose custom positions for the sheet not provided by current API. Another big step would be to confiure the sheet to act like any viewcontroller--ALlow for pushes to another controller for more information while still maintating current position. Moreover, tapping into UIPresentationController API to create a smooth modal transitions between views while keeping Sheet design intact (Doordash's ordering view). 

## Cross-Platform Usability
This component primarly should be used on mobile. The main reason behind the deisgn in my oppinion is to allow for my content without forcing the user to switch between many different views. If there is more screen real estate such as on tablets and computers, a side panel next to main content would probably be a compareable design to mimic the same interacton.   

