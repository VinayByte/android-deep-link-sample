# android-deep-link-sample
In Android, the `android:scheme` and `android:host` attributes are used in the intent filter of an activity to define the URI scheme and host for deep linking.

- `android:scheme`: This attribute specifies the URI scheme that the activity can handle. A URI scheme is the part of a Uniform Resource Identifier (URI) that defines the protocol or scheme used to access or identify a resource. For example, common URI schemes include "http", "https", "tel", "mailto", and "file". When defining a custom URI scheme for your app, you can choose a unique name that starts with your app's package name or a specific identifier. For example, if your app's package name is "com.example.myapp", you can define a custom scheme like "myapp" by setting `android:scheme="myapp"`.

- `android:host`: This attribute specifies the host or domain associated with the deep link. It is used to specify the specific destination within your app that should handle the deep link. The host attribute is optional, and if you don't need to specify a specific host, you can omit it. For example, if you want to handle all deep links with the scheme "myapp", you can set `android:host="*"` to match any host.

Here's an example of how you can use these attributes in the intent filter of an activity in the Android manifest:

```xml
<intent-filter>
    <action android:name="android.intent.action.VIEW" />
    <category android:name="android.intent.category.DEFAULT" />
    <category android:name="android.intent.category.BROWSABLE" />

    <data
        android:scheme="myapp"
        android:host="example.com" />
</intent-filter>
```

In the above example, the activity with this intent filter will be able to handle deep links with the URI scheme "myapp" and the host "example.com". You can define multiple intent filters with different schemes and hosts to handle different types of deep links within your app.

In your web page or browser, create a link with the custom URI scheme to open your Android app. For example:

html
Copy code
<a href="myapp://open">Open My App</a>
When the user clicks the link, it will trigger the custom URI scheme, and if your app is installed on the device, it will be opened.(For Testing copy test-deeplink.html to device and open it on browser and click Open My App button.)
