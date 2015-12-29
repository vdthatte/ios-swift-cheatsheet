# ios-swift-cheatsheet

Compilation of some of the most commonly used stuff while I develope apps

### Unwind to previous/home screen.

@IBAction func unwindToPrevious(segue: UIStoryboardSegue) {
}

### Hex colors ### 
func UIColorFromHex(rgbValue:UInt32, alpha:Double=1.0)->UIColor {
        let red = CGFloat((rgbValue & 0xFF0000) >> 16)/256.0
        let green = CGFloat((rgbValue & 0xFF00) >> 8)/256.0
        let blue = CGFloat(rgbValue & 0xFF)/256.0
        return UIColor(red:red, green:green, blue:blue, alpha:CGFloat(alpha))
}//UIColorFromHex
