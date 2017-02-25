<img src="https://pp.vk.me/c604720/v604720888/37813/os4AzOREBAY.jpg" width="600px"></img>

 

AwesomeSpotlightView is a nice and simple libriary for iOS written on Swift 3. It's highly customizable and easy-to-use tool. Works perfectly for tutorial or coach in your app. 

![icon](https://psv4.vk.me/c812529/u11225888/docs/fc40c590a745/giphy.gif?extra=caA0mh9X42MfFm8ChqUAF2_2Tttvce1V1FY00NtuAdvO-bBHmegvRQTnUGrDekzAzFktvyzZCsFvC9CNhItk5vrw4IlMw6lPsxdv-xBTqySVUVETixB_)

![icon](https://cs7064.vk.me/c812520/u11225888/docs/0f11997e9c90/giphy_1.gif?extra=VHTih3h_AUbAufM_bGEi4ci5r1P0lJYRsE4skxT8xXwjJL1EVkgdUT5CuHzoHqZIypvGOEBXq0SI-_HI4QNhg4JfpOCJxenmZHRryF_tI7k1rRh7YB3h)

## Example

To run the example project, clone the repo, and run `pod install` from the Example directory first.

## Installation
## CocoaPods
AwesomeSpotlightView is available through [CocoaPods](http://cocoapods.org). To install
it, simply add the following line to your Podfile:

```ruby
pod "AwesomeSpotlightView"
```


## Manually

* Just drop AwesomeSpotlightView folder in your project.
* You're ready to use AwesomeSpotlightView!

## Usage

```swift
override func viewDidLoad() {
    super.viewDidLoad()
    let spotlight1 = AwesomeSpotlight(withRect: CGRect(x: 75, y: 75, width: 100, height: 100), shape: .Circle, text: "spotlight1")
    let spotlight2 = AwesomeSpotlight(withRect: CGRect(x: 20, y: 200, width: 130, height: 25), shape: .Rectangle, text: "spotlight2")
    let spotlight3 = AwesomeSpotlight(withRect: CGRect(x: 170, y: 50, width: 30, height: 100) shape: .RoundRectangle, text: "spotlight3")
    
    let spotlightView = AwesomeSpotlightView(frame: view.frame, spotlight: [spotlight1, spotlight2, spotlight3])
    spotlightView.cutoutRadius = 8
    spotlightView.delegate = self
    view.addSubview(spotlightView)
    spotlightView.start()
}
```

You can configure AwesomeSpotlightView before you present it using the `start` method. For example:

```objective-c
spotlightView.enableContinueLabel = true
spotlightView.enableSkipButton = true
spotlightView.showAllSpotlightsAtOnce = false
spotlightView.start()
```

## Configuration AwesomeSpotlight

var rect = CGRect()
  var shape : AwesomeSpotlightShape = .RoundRectangle
  private var text : String = ""
  private var attributedText : AttributedString? = nil

### `rect` (CGRect)

The rect of spotlight.

### `shape` (AwesomeSpotlightShape)

Shape of spotlight: .Rectangle, .RoundRectangle, .Circle.

### `text` (String)

The text of the caption.

### `attributedText` (AttributedString)

The attributed text of the caption.

## Configuration AwesomeSpotlightView

### `spotlightsArray` ([AwesomeSpotlight])

Modify the spotlights.

### `spotlightMaskColor` (UIColor)

The color of the mask (default: 0,0,0 alpha 0.6).

### `animationDuration` (Double)

Transition animation duration to the next coach mark (default: 0.3).

### `cutoutRadius` (CGFloat)

The cutout rectangle radius (default: 4.0).

### `maxLabelWidth` (Double)

The captions label is set to have a max width of 280px. Number of lines is figured out automatically based on caption contents.

### `labelSpacing` (CGFloat)

Define how far the captions label appears above or below the cutout (default: 35px).

### `enableContinueLabel` (Bool)

'Tap to continue' label pops up by default to guide the user at the first spotlight (default: false).

### `enableSkipButton` (Bool)

'Skip' label pops up by default to guide the user at the first spotlight (default: false).

### `enableArrowDown` (Bool)

Icon with Arrow showed between caption text and caption (default: false).

### `textLabelFont` (UIFont)

Fond of caption text label (default: UIFont.systemFont(ofSize: 20.0)).

### `continueLabelFont` (UIFont)

Fond of continue label (default: UIFont.systemFont(ofSize: 13.0)).

### `skipButtonFont` (UIFont)

Fond of skip button (default: UIFont.boldSystemFont(ofSize: 13.0)).

### `showAllSpotlightsAtOnce` (Bool)

Showed all spotlight at once (at the same time) (default: false).

## AwesomeSpotlightViewDelegate

### 1. Conform your view controller to the AwesomeSpotlightViewDelegate protocol:

`class ViewController: UIViewController, AwesomeSpotlightViewDelegate`

### 2. Assign the delegate to your AwesomeSpotlightView view instance:

`spotlightView.delegate = self`

### 3. Implement the delegate protocol methods:

*Note: All of the methods are optional. Implement only those that are needed.*

- `func spotlightView(spotlightView : AwesomeSpotlightView, willNavigateToIndex index: Int)`
- `func spotlightView(spotlightView : AwesomeSpotlightView, didNavigateToIndex index: Int)`
- `func spotlightViewWillCleanup(spotlightView : AwesomeSpotlightView)`
- `func spotlightViewDidCleanup(spotlightView : AwesomeSpotlightView)`

## Inspired by
* [WSCoachMarksView](https://github.com/workshirt/WSCoachMarksView)

## Author
* [Aleksandr Shoshiashvili](https://github.com/aleksandrshoshiashvili)
