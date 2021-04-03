# AppClipQuickStart
Instructions on how to make an app clip.

1. Add a new target

![File -> New -> Target](https://user-images.githubusercontent.com/49819455/113492885-d6ce2380-948f-11eb-8b3d-6f4d564eacd4.png)


2. Choose "App Clip," then hit <kbd>Next</kbd>

![Screen Shot 2021-04-03 at 3 18 51 PM](https://user-images.githubusercontent.com/49819455/113492895-e77e9980-948f-11eb-8c5e-9974ce7543eb.png)

3. Fill in the name of your app clip (I did "MyCoolAppClip")
 
![Screen Shot 2021-04-03 at 3 19 50 PM](https://user-images.githubusercontent.com/49819455/113492918-0a10b280-9490-11eb-9c40-7acc6852de6a.png)

4. Press <kbd>Activate</kbd>

![Screen Shot 2021-04-03 at 3 20 22 PM](https://user-images.githubusercontent.com/49819455/113492955-30cee900-9490-11eb-8797-d02248c7046d.png)

5. Your project navigator should look like this:

![Screen Shot 2021-04-03 at 3 21 23 PM](https://user-images.githubusercontent.com/49819455/113492965-46dca980-9490-11eb-9145-1e1534d7ca5d.png)

6. Now add, edit, and make the App Clip just like you would for a normal Xcode project. For example, I added this inside `MyCoolAppClip -> ContentView.swift`:

```swift
struct ContentView: View {
    var body: some View {
        Text("Hello, world! This is an app clip")
            .padding()
    }
}
```

![Screen Shot 2021-04-03 at 3 22 57 PM](https://user-images.githubusercontent.com/49819455/113492987-7a1f3880-9490-11eb-956e-8c4c8b28211a.png)

7. Once you're done. it's time to configure the URLs. First, go to Project Settings -> Targets -> MyCoolAppClip -> Signing and Capabilities -> <kbd>+ Capability</kbd>.

![Screen Shot 2021-04-03 at 3 23 50 PM](https://user-images.githubusercontent.com/49819455/113493011-af2b8b00-9490-11eb-9d7b-bb2e138254f1.png)
 

8. In the popup, select "Associated Domains".

![Screen Shot 2021-04-03 at 3 26 01 PM](https://user-images.githubusercontent.com/49819455/113493036-ef8b0900-9490-11eb-83bb-3ba7ae2bfb36.png)

9. Add your website inside the text field. Mines is `getfind.app`. I'm not sure about this, but don't put the `www` in front.

![Screen Shot 2021-04-03 at 3 26 48 PM](https://user-images.githubusercontent.com/49819455/113493049-07fb2380-9491-11eb-824a-d7f478c21b6a.png)


10. That's all you need on the app side. Now, it's time to configure the web page where the app clip will be launched from.
11. 

