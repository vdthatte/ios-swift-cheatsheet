# ios-swift-cheatsheet

Compilation of some of the most commonly used stuff while I develop apps

```Swift
// Code Unwind to previous home screen.

@IBAction func unwindToPrevious(segue: UIStoryboardSegue) {
} // unwindToPrevious

'''

// Code to produce UIColor from hex values

'''Swift
func UIColorFromHex(rgbValue:UInt32, alpha:Double=1.0)->UIColor {
        let red = CGFloat((rgbValue & 0xFF0000) >> 16)/256.0
        let green = CGFloat((rgbValue & 0xFF00) >> 8)/256.0
        let blue = CGFloat(rgbValue & 0xFF)/256.0
        return UIColor(red:red, green:green, blue:blue, alpha:CGFloat(alpha))
} // UIColorFromHex
'''

// code to present view controller

'''Swift
let vc = ViewController() //change this to your class name
self.presentViewController(vc, animated: true, completion: nil)
'''

// prepare to segue

'''Swift
override func prepareForSegue(segue: UIStoryboardSegue, sender: AnyObject?) {
        // Get the new view controller using segue.destinationViewController.
        // Pass the selected object to the new view controller.
}
'''
