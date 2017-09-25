# LanguageManger-iOS
Language manger used to handle change app language without restart the app
<br>
*Note <br>
This language manger change the Bundle in the run time, so you need to handel other things like right to left in subviews and don't forget to add the localized files for laguages you are using.

<b>ScreenShots</b>

<img src="https://raw.githubusercontent.com/Abedalkareem/LanguageManger-iOS/master/screen.gif"  width="450">

<b>Usage</b>



```swift
    @IBAction func changeLanguage(_ sender: UIButton) {
        let selectedLanguage = sender.tag == 1 ? "en" : "ar"
        // set the language you need
        LanguageManger.shared.setLanguage(language: selectedLanguage)
        
        // then you must to pop all view controllers and return to root view controller then re set the root view controller 
        UIApplication.topViewController!.dismiss(animated: true) {
            UIApplication.topViewController!.dismiss(animated: true) {
                let delegate = UIApplication.shared.delegate as! AppDelegate
                let storyboard = UIStoryboard(name: "Main", bundle: nil)
                delegate.window?.rootViewController = storyboard.instantiateInitialViewController()
            }
        }
    }
```

<b>Installation</b>

Just add ```LanguageManger.swift``` in your project


<b>Note</b>

I'm going to be very happy if you give me a feedback or advice , thank you
