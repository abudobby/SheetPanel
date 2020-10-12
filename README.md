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
```


## API

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
