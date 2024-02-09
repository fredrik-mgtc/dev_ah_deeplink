Some update in the Apple’s privacy manifest policy requirements (in random order):

iOS 17

PrivacyInfo.xcprivacy
<br>
The privacy manifest is a property list that records the types of data collected by your app or third-party SDK, and the required reasons APIs your app or third-party SDK uses. For each type of data your app or third-party SDK collects and category of required reasons API it uses, record the reasons in your privacy manifest file.
<br>
"Xcode will combine the privacy manifests across all the third-party SDKs that a developer is using into a single, easy-to-use report."
https://developer.apple.com/news/?id=av1nevon
<br>

Get started with privacy manifests - video
https://developer.apple.com/videos/play/wwdc2023/10060/?time=264

**0.**
<br>
When you submit a new app
<br>
When you submit an app update that “adds one of the listed SDKs as part of the update”
<br>
From Singular: https://www.singular.net/blog/privacy-manifest-sdks/

<br>
**1.**
<br>
https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_use_of_required_reason_api
**The file timestamp API** is on the list of APIs that needs reasons to use. I haven't found any place where we use any of these calls. 
<br>
**Unity**
<br>uses some but updating to 2022.3.18f1 should fix that (from doc "Starting with Unity Editor versions 2021.3.35f1, 2022.3.18f1, and 2023.2.7f1, Unity Engine automatically includes these reasons in the privacy manifest file.").
<br>
**Rider**
<br>
uses `fileInfo.LastWriteTime` but that is not shipped with the game so not a problem. There are all in files that are inside an Editor folder.
<br>
**Backtrace**
<br>
uses `fileInfo.CreationTime` in `BacktraceDatabaseFileContext`. We might need to include something in our own privacy manifest about this.

<br>
**2.**
We will need a privacy manifest from Firebase. They are working on this (https://github.com/firebase/firebase-ios-sdk/issues/11490). I'm following this.


**3.**
<br>
We will need a privacy manifest from Facebook. Facebook is not responding. Last question was 3 days ago.
<br>
Unity SDK: https://github.com/facebook/facebook-sdk-for-unity/issues/709
<br>
Native iOS: https://github.com/facebook/facebook-ios-sdk/issues/2264


**4.**
<br>
Scanners for possible use of "iOS required reason API".
<br>
https://github.com/omarzl/ios_17_required_reason_api_scanner/tree/binary_analyzer


**5.**
<br>
Tracking domains. iOS 17 will block calls to those domains if user didn't accept permissions.
<br>
Optional?
<br>
<br>
https://www.singular.net/blog/ios-17-privacy/
<br>
"Any endpoints you use for tracking purposes will need to be declared in privacy manifests, and if people using your apps don’t accept tracking via Apple’s ATT pop-up, all traffic to those domains will be blocked."



<br><br>
[Ashvin Harrison](https://s.mgtc.dev/ahp/open?gallery_id=ashvin_harrison_1&v1=ashvinh1&v2=ashvinh2&v3=ashvinh3)
<br><br>
<br><br>
[Nick Runge - instapost - v1shadow](https://s.mgtc.dev/ahp/open?gallery_id=nick_runge_1&v1=nickrunge&v2=instapost&v3=v1shadow&ppid=326df608-9af3-4ece-82c8-04cf24808853&listing=nick_runge)


