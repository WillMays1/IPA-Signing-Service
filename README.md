# IPA-Signing-Service

Dont forget to request access to my private IPA Signing Server
ss.wmaystech.com
(We dont get revoked ;) )

Hello, I am going to show you how to create an IPA Signing Service using an Apple Developer Account ($99/year) and your website.

The instructions below are not going to show you how to create a Apple Dev Account or set-up your website. Let's begin.

1. Download all the required files above.

2. Open your Apple Dev Account and click on Certificates, Identifiers, and Profiles.

3. Open up the Certificates tab and create a Production cert (might be stuck here just use google.com)

4. Create an App ID, give it any name you want. 
 - Check Wildcard App ID. 
 - Make the Bundle ID what you want it to be like this -> com.example.*
 - For App Services enable “Data Protection”, “iCloud”, “Inter-App Audio”, “Network Extensions”, “SiriKit”, and “Wallet”

5. Go to Devices tab and add any devices you are going to sign the apps to.

6. Go to Provisioning Profiles tab and create a new profile
 - Select Ad Hoc under Distribution
 - Select your iOS Distribution profile. 
 - Select the devices you are going to sign the apps to.
 - Enter a profile name and download the profile

7. Obtain your desired .ipa and open iOS App Signer Application
 - Drag your ipa into the input file location
 - For Signing Certificate choose iPhone Distribution
 - For Provisioning Profile choose custom file and select the file we downloaded earlier
 - For the New Application ID enter your wildcard app id and the name of the app -> com.example.battery
 - Click Start and choose your desired output location and wait for it to complete

8. Open the .plist file downloaded from my github earlier
 - Change <key>url</key> <string>example.com/exampleapp.ipa</string> to where the ipa is located on your website
 - Change the bundleid to what you used in the iOS App Signer App <key>bundle-identifier</key> <string>com.example.battery</string>
 - Change the title if you want (if you don’t it will be default title)

9. Open up the index.html file you downloaded earlier
 - Change the ending to where your plist is located on your website itms-services://?action=download-manifest&url=https://example.com/exampleapp.plist

10. Upload the “index.html”, “example.ipa”, and “example.plist” to your website

11. Open the index.html page on your iDevice.

12. Click download and the app will be downloaded to your device.

Check ERROR FIXES file for possible fixes if they apps are not working

**Every time you add a device to your account you have to redo steps 7-8 and edit the profile to add the devices then re download the profile
