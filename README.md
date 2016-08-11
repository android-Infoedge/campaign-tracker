##utm-grabber

Using this library anyone can extract the campaign parameters (e.g. utm source,utm medium,utm term,utm content and utm campaign) value from campaign url.
These parameters can be used to track the traffic sources and campaign that are bringing users to your app. 


##### include in build.gradle:-
    repositories {
    maven {
        url 'https://dl.bintray.com/android-infoedge/maven/'
    } 
    }
    dependencies {
        compile 'com.infoedge.campaign:utm-grabber:1.0.0'
    }
   
 To test your install referrer you can run this command from terminal:-
     
 
    adb shell
    am broadcast -a com.android.vending.INSTALL_REFERRER -n <your.package>/.<path.up.until.your.BroadcastReceiver> --es "referrer" "utm_source=test_source&utm_medium=test_medium&utm_term=test_term&utm_content=test_content&utm_campaign=test_name"
  
 Example:-
 
    adb shell
    am broadcast -a com.android.vending.INSTALL_REFERRER -n installreferrer.demo.com.myapplication/.customreciever.InstallReferrerReceiver --es "referrer" "utm_source=test_source&utm_medium=test_medium&utm_term=test_term&utm_content=test_content&utm_campaign=test_campaign"
       
 To reterive the campaign parameters values in your activity:-
    
    UtmSourceInfo utmSourceInfo=ReferralReceiver.retrieveReferralParams1(getApplicationContext()); 
    utmSourceInfo.getUtmSource();
    utmSourceInfo.getUtmTerm();
    utmSourceInfo.getUtmMedium();
    utmSourceInfo.getUtmCampaign();
    utmSourceInfo.getUtmContent()
 
 Clear the referrer file from your application:         
     
     ReferralReceiver.clearReferralFile(getApplicationContext());     
  
  


##License

Copyright 2016 Info Edge India Limited

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
