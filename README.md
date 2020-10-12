# SheetPanel
Bottom Sheet Panel Reusable Component


## Getting Started

Download the project and drag the SheetPanel framework into your workspace

[create an anchor](#Features)



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

SheetPanelViewController is a drop in Bottom Sheet view that is configurable. Instantiate the controller and a few lines of code and your are up and running. 

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
Sets the view controller responsible for the content portion of a sheet.

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

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
