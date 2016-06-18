# Swift Cheatsheet

### Helpful resources
###### Swift Cookbook by @vandadnp https://github.com/vandadnp/iOS-8-Swift-Programming-Cookbook
###### Awesome Swift by @matteocrippa https://github.com/matteocrippa/awesome-swift
###### Awesome Swift by @Wolg https://github.com/Wolg/awesome-swift
###### Awesome iOS by @vsouza https://github.com/vsouza/awesome-ios
<br>
## Compilation of some of the most commonly used stuff while I develop apps.

#### Unwind to Previous Screen
```Swift

@IBAction func unwindToPrevious(segue: UIStoryboardSegue) {
        // some code to execute
} // unwindToPrevious

```

#### Produce UIColor from Hex Values

###### This is pretty awesome - https://github.com/yeahdongcn/UIColor-Hex-Swift

```Swift

func UIColorFromHex(rgbValue:UInt32, alpha:Double=1.0)->UIColor {
        let red = CGFloat((rgbValue & 0xFF0000) >> 16)/256.0
        let green = CGFloat((rgbValue & 0xFF00) >> 8)/256.0
        let blue = CGFloat(rgbValue & 0xFF)/256.0
        return UIColor(red:red, green:green, blue:blue, alpha:CGFloat(alpha))
} // UIColorFromHex
```

#### Present View Controller

```Swift
let vc = ViewController() //change this to your class name
self.presentViewController(vc, animated: true, completion: nil)
```

#### Present View Controller with Storyboard ID

```Swift 
let storyboard = UIStoryboard(name: "Main", bundle: nil)
let vc = storyboard.instantiateViewControllerWithIdentifier("nav1") as! CustomNavigationVC
self.presentViewController(vc, animated: true, completion: nil)
```

#### Prepare to Segue

```Swift
override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
        // Get the new view controller using segue.destinationViewController.
        // Pass the selected object to the new view controller.
} // prepareForSegue
```

#### Screen Dimensions

Useful when you want to create UI based on the model of the phone.
Note:- Include this code in your viewDidLoad() as shown below

```Swift
override func viewDidLoad() {
        super.viewDidLoad()
        
        let screenSize: CGRect = UIScreen.mainScreen().bounds
        let screenHeight = screenSize.height
        let screenWidth = screenSize.width
} // viewDidLoad

```

#### Dismiss View Controller

```Swift

self.dismissViewControllerAnimated(false, completion: nil)

```

#### Rotate

```Swift

self.transform = CGAffineTransformMakeRotation((valueToRotate * CGFloat(M_PI)) / 180.0)

```

#### Text Label Multiple Lines

```Swift
textLabel.lineBreakMode = .ByWordWrapping // or NSLineBreakMode.ByWordWrapping
textLabel.numberOfLines = 0 
```

#### Circular Image

```Swift
        self.profileImageView.layer.cornerRadius = self.profileImageView.frame.size.width / 2;
        self.profileImageView.clipsToBounds = true;
```

#### Inside Segment Buttons Tapped

```Swift

switch segmentView.selectedSegmentIndex{
case 0:
    userInformationLabel.text = "text1";
case 1:
    userInformationLabel.text = "text2";
case 2:
    userInformationLabel.text = "text3";
default:
    break; 
}
```

#### Swipe Gesture

###### Thanks to http://www.ioscreator.com/tutorials/detecting-swipe-gesture-tutorial-ios8-swift

####### Add the code below in your viewDidLoad
```Swift 
override func viewDidLoad() {
    super.viewDidLoad()
    
    var leftSwipe = UISwipeGestureRecognizer(target: self, action: Selector("handleSwipes:"))
    var rightSwipe = UISwipeGestureRecognizer(target: self, action: Selector("handleSwipes:"))
    
    leftSwipe.direction = .Left
    rightSwipe.direction = .Right
    
    view.addGestureRecognizer(leftSwipe)
    view.addGestureRecognizer(rightSwipe)
}

```

####### Add this method in your View Controller Class
```Swift

func handleSwipes(sender:UISwipeGestureRecognizer) {
    if (sender.direction == .Left) {
      println("Swipe Left")
    }
    
    if (sender.direction == .Right) {
      println("Swipe Right")
      self.swipeLabel.frame.size.height)
    }
}
```
#### Error Handling - Swift 2.0
```Swift
do{
    try (statements)
}
catch{
    print("errors")
}
```

#### UI AlertView

```Swift 
let alert = UIAlertController(title: "Alert", message: "Message", preferredStyle: UIAlertControllerStyle.Alert)
alert.addAction(UIAlertAction(title: "Click", style: UIAlertActionStyle.Default, handler: nil))
self.presentViewController(alert, animated: true, completion: nil)
```

#### Pinch Gesture 

###### Thanks to: http://www.ioscreator.com/tutorials/scale-image-pinch-gesture-ios8-swift
```Swift

@IBAction func scaleImage(sender: UIPinchGestureRecognizer) {
    self.view.transform = CGAffineTransformScale(self.view.transform, sender.scale, sender.scale)
    sender.scale = 1
}

```
#### Draw a ring using Core Graphics

##### Thanks to: http://stackoverflow.com/questions/29616992/how-do-i-draw-a-circle-in-ios-swift
```Swift 

        let circlePath = UIBezierPath(arcCenter: CGPoint(x: 100,y: 100), radius: CGFloat(20), startAngle: CGFloat(0), endAngle:CGFloat(M_PI * 2), clockwise: true)
        
        let shapeLayer = CAShapeLayer()
        shapeLayer.path = circlePath.CGPath
        
        //change the fill color
        shapeLayer.fillColor = UIColor.clearColor().CGColor
        //you can change the stroke color
        shapeLayer.strokeColor = UIColor.redColor().CGColor
        //you can change the line width
        shapeLayer.lineWidth = 3.0
        
        view.layer.addSublayer(shapeLayer)

```
