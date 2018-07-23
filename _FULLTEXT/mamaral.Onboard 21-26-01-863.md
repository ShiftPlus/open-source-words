onboard click here for more examples important onboard is no longer under active development and as such if you create any issues or submit pull requests its not very likely to be integrated thanks to all that helped make onboard better over the last few years usage adding the following to your podfile and running pod install should do the trick pod onboard if you dont want to use cocoapods you can use carthage or grab the files located in the source folder and pull them into your project manually each onboarding experience is comprised of two primary components the background and the content pages the background includes the static background image video the page control and the skip button the content pages are made up of four pieces an image icon title body and action button create individual pages by creating instances of onboardingcontentviewcontroller provide a title body image text for an action button and within the action block handle whatever you want to do when the users press the button if you dont want a button you can leave both the button text and action handler nil objective c objective c onboardingcontentviewcontroller firstpage onboardingcontentviewcontroller contentwithtitle page title body page body goes here image uiimage imagenamed icon buttontext text for button action do something here when users press the button like ask for location services permissions register for push notifications connect to social media or finish the onboarding process swift swift let firstpage onboardingcontentviewcontroller title page title body page body goes here image uiimage named icon buttontext text for button void in do something here when users press the button like ask for location services permissions register for push notifications connect to social media or finish the onboarding process then create the onboardingviewcontroller by providing either a background image or a url to a local video file in your project and an array of content view controllers you just created you can then present the view modally and get the onboarding process started objective c objective c image onboardingviewcontroller onboardingvc onboardingviewcontroller onboardwithbackgroundimage uiimage imagenamed background contents firstpage secondpage thirdpage video nsbundle bundle nsbundle mainbundle nsstring moviepath bundle pathforresource yourvid oftype mp4 nsurl movieurl nsurl fileurlwithpath moviepath onboardingviewcontroller onboardingvc onboardingviewcontroller onboardwithbackgroundvideourl movieurl contents firstpage secondpage thirdpage swift swift image let onboardingvc onboardingviewcontroller backgroundimage uiimage named background contents firstpage secondpage thirdpage video let bundle nsbundle mainbundle let moviepath bundle pathforresource yourvid oftype mp4 let movieurl nsurl fileurlwithpath moviepath let onboardingvc onboardingviewcontroller backgroundvideourl movieurl contents firstpage secondpage thirdpage with only a few lines of code you have a beautiful end to end onboarding process that will get your users excited to use your awesome application customization the iconimageview titlelabel bodylabel and actionbutton properties are exposed for customizing fonts sizing etc and the spacing between elements on the content pages can be customized as well objective c onboardingvc toppadding 20 onboardingvc undericonpadding 10 onboardingvc undertitlepadding 15 onboardingvc bottompadding 20 blurring masking and fading by default the image you use for the background will have a mask applied over it darkening it a bit this is to add a little bit of contrast so the text can more easily be seen this can easily be disabled if your image is already edited or looks fine as is objective c onboardingvc shouldmaskbackground no defaults to yes we can also apply a blur to your background image objective c onboardingvc shouldblurbackground yes defaults to no apply a fade effect to the icons text and buttons while transitioning between pages contents fade out as you scroll away and the contents for the next page fade in as they scroll in objective c onboardingvc shouldfadetransitions yes defaults to no note ensure you do not cause the onboard view controllers view to be loaded prior to setting these properties as these values only take effect when the view controllers viewdidload is called so doing something like setting your onboardingvc view backgroundcolor uicolor whitecolor before setting this values would lead to the setting of these to not take effect you can tweak these settings in a few different combinations to get your desired effect auto navigation if you want to automatically move users to the next page in the onboarding process when they press the action button simply set the movestonextviewcontroller property to yes on any onboardingcontentviewcontroller that isnt the last view controller in the onboarding process coupled with this you can disable the ability to swipe between contents by setting the swipingenabled property on the onboardingviewcontroller to no this allows you to have greater control over the onboarding process if you desire finally if your design lends itself to not having a page control or if it is only one page you can set the hidepagecontrol property to yes and the page control dots will not appear objective c contentvc movestonextviewcontroller yes onboardingvc swipingenabled no onboardingvc hidepagecontrol yes skipping if you want to allow users to skip the onboarding process enable skipping on the onboarding view controller and set a block to be executed when the skip button is pressed objective c onboardingvc allowskipping yes onboardingvc skiphandler dismiss fade out etc blocks there may be cases in which you want to do something when the content pages are about to appear and when they did appear in this case you can set the viewwillappearblock and viewdidappearblock properties on any or all of the content pages to handle whatever youd like objective c contentvc viewwillappearblock do something when the view will appear here… contentvc viewdidappearblock do something when the view appears here… notes im not currently supporting landscape at the moment so i would recommend either using this in an application that only supports portrait or wrapping it in a subclassed uinavigationcontroller that only supports portrait community questions comments issues and pull requests welcomed license this project is made available under the mit license see license txt for details