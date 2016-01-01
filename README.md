# ios-swift-cheatsheet

Compilation of some of the most commonly used stuff while I develop apps

### Unwind to Previous Screen
```Swift

@IBAction func unwindToPrevious(segue: UIStoryboardSegue) {
} // unwindToPrevious

```

### Produce UIColor from Hex Values

```Swift

func UIColorFromHex(rgbValue:UInt32, alpha:Double=1.0)->UIColor {
        let red = CGFloat((rgbValue & 0xFF0000) >> 16)/256.0
        let green = CGFloat((rgbValue & 0xFF00) >> 8)/256.0
        let blue = CGFloat(rgbValue & 0xFF)/256.0
        return UIColor(red:red, green:green, blue:blue, alpha:CGFloat(alpha))
} // UIColorFromHex
```

### Present View Controller

```Swift
let vc = ViewController() //change this to your class name
self.presentViewController(vc, animated: true, completion: nil)
```

### Present View Controller with Storyboard ID

```Swift 
let storyboard = UIStoryboard(name: "Main", bundle: nil)
let vc = storyboard.instantiateViewControllerWithIdentifier("nav1") as! CustomNavigationVC
self.presentViewController(vc, animated: true, completion: nil)
```

### Prepare to Segue

```Swift
override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
        // Get the new view controller using segue.destinationViewController.
        // Pass the selected object to the new view controller.
}
```
