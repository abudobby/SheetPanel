# SheetPanel
Bottom Sheet Panel Reusable Component


## Getting Started

Download the project and drag the SheetPanel framework into your workspace

## Usage

```swift
import SheetPanel

let sheetVC = SheetPanelViewController()

....
override func viewDidLoad() {
        super.viewDidLoad()   
        sheetVC.titleLabel.text = "Title"
        sheetVC.subtitleLabel.text = "Subtitile"
        sheetVC.addPanel(toParent: self)
        sheetVC.set(contentViewController: ContentViewController())
        
         }
```


## Features

```swift
import SheetPanel

let sheetVC = SheetPanelViewController()

....
override func viewDidLoad() {
        super.viewDidLoad()   
        sheetVC.titleLabel.text = "Title"
        sheetVC.subtitleLabel.text = "Subtitile"
        sheetVC.addPanel(toParent: self)
        sheetVC.set(contentViewController: ContentViewController())
        
         }
```

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
