# ios-swift-cheatsheet

Compilation of some of the most commonly used stuff while I develope apps

### Unwind to previous/home screen.

@IBAction func unwindToPrevious(segue: UIStoryboardSegue) {
}

### Hex colors ### 
func UIColorFromHex(rgbValue:UInt32, alpha:Double=1.0)->UIColor {__
        let red = CGFloat((rgbValue & 0xFF0000) >> 16)/256.0__
        let green = CGFloat((rgbValue & 0xFF00) >> 8)/256.0__
        let blue = CGFloat(rgbValue & 0xFF)/256.0__
        return UIColor(red:red, green:green, blue:blue, alpha:CGFloat(alpha))__
}//UIColorFromHex__
