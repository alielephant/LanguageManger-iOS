<p align="center">
 <img src="https://github.com/Abedalkareem/LanguageManger-iOS/blob/master/logo.png?raw=true"  width="150">  </center>
</p>
<br>

Language manger used to handle change app language without restart the app
<br>


<b>ScreenShots</b>

<img src="https://raw.githubusercontent.com/Abedalkareem/LanguageManger-iOS/master/screenrec.gif"  width="450">

<b>Usage</b>



```swift
    @IBAction func changeLanguage(_ sender: UIButton) {
        
        let selectedLanguage:Languages = sender.tag == 1 ? .en : .ar
        
        // change the language
        LanguageManger.shared.setLanguage(language: selectedLanguage)

        // then you must to pop all view controllers and return to root view controller then re set the root view controller 
        UIApplication.topViewController!.dismiss(animated: true) {
            let delegate = UIApplication.shared.delegate as! AppDelegate
            let storyboard = UIStoryboard(name: "Main", bundle: nil)
            delegate.window?.rootViewController = storyboard.instantiateInitialViewController()
        }
    }
```

*Note <br>
The language manager help you to support multiple languages in your app, However, there are some cases that you want to handle it yourself like some ```UILable``` or ```UITextField``` didn't change the direction, so you need to do that .
Example:

``` textAlignment =  LanguageManger.shared.isRightToLeft ? .right : .left. ```

<b>Installation</b>

Just add ```LanguageManger.swift``` in your project


<b>Note</b>

I'm going to be very happy if you give me a feedback or advice , thank you
