# AppClipQuickStart
Instructions on how to make and publish an app clip. This will eventually get cleaned up and transformed into an article.

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

9. Add your domain inside the text field, in the form of `appclips:<DOMAIN_NAME>`. Mines is `appclips:getfind.app`.

# Important!
**I'm pretty sure you need to own a custom domain first.** I bought a domain, [getfind.app](https://getfind.app/), then linked it to GitHub Pages. You should also buy a domain (`https://yourwebsite.com`) first.

![Screen Shot 2021-04-03 at 3 26 48 PM](https://user-images.githubusercontent.com/49819455/113493049-07fb2380-9491-11eb-824a-d7f478c21b6a.png)


10. That's all you need on the app side. Now, it's time to configure the web page where the app clip will be launched from. You'll need a place to host an ` apple-app-site-association` file.
11. I used GitHub Pages, because it's free. I've already set up everything in this repo, so click <kbd>Use this template</kbd> at the top of this page. Enter a name for your repo (I did "MyAppClipWebsite").

Use this template | Make sure to check "Include all branches"
--- | ---
![Screen Shot 2021-04-03 at 3 33 11 PM](https://user-images.githubusercontent.com/49819455/113493177-10a02980-9492-11eb-91a0-e4570dd24d96.png) | ![Screen Shot 2021-04-03 at 3 33 30 PM](https://user-images.githubusercontent.com/49819455/113493178-139b1a00-9492-11eb-9d63-644254c7da91.png)

Then, link your newly-generated repo to your custom domain:

### [Instructions to link your GitHub pages website to your custom domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/about-custom-domains-and-github-pages)

12. Enable GitHub Pages in the `Settings` tab of the newly-made repo. Select branch **GitHubPages** and **/ (root)** folder.


![Screen Shot 2021-04-03 at 3 42 44 PM](https://user-images.githubusercontent.com/49819455/113493340-4265c000-9493-11eb-8e35-9ca5c600d799.png)


13. Select the "GitHubPages" branch, then check out the `apple-app-site-association` file.


```JSON
---
layout: none
permalink: .well-known/apple-app-site-association
---

{
    "appclips": {
        "apps": [
            "YA533DMD5J.aheze.AppClipQuickStart.Clip
        ]
    }
}
```

13. Replace `YA533DMD5J` with your own Team ID. You can find this at:

```
https://developer.apple.com/account/#/membership/
```

![Screen Shot 2021-04-03 at 3 39 07 PM](https://user-images.githubusercontent.com/49819455/113493284-daaf7500-9492-11eb-95d1-505b59906765.png)


14. Also, replace `aheze.AppClipQuickStart.Clip` with your app clip's Bundle ID. You can find this inside Xcode, at `Project Settings -> Targets -> MyCoolAppClip -> Signing and Capabilities -> Bundle Identifier`.

![Screen Shot 2021-04-03 at 3 41 08 PM](https://user-images.githubusercontent.com/49819455/113493310-0599c900-9493-11eb-8ad3-5bd594126261.png)

15. Wait a little bit, then try going to `https://YOURGITHUBUSERNAME.github.io/MyAppClipWebsite/.well-known/apple-app-site-association` (replace `MyAppClipWebsite` with the name of your newly-generated repo). Your browser should download that file, which should look something like this:

![Screen Shot 2021-04-03 at 3 46 40 PM](https://user-images.githubusercontent.com/49819455/113493402-d5065f00-9493-11eb-9faf-d990dabc52c7.png)

If you linked GitHub Pages to your custom domain correctly, you should also be able to download the file at `https://yourwebsite.com/.well-known/apple-app-site-association`. For example, going to [https://getfind.app/.well-known/apple-app-site-association](https://getfind.app/.well-known/apple-app-site-association) will download the file.

16. That's all you need. Now, once you upload your app to App Store Connect, you should be able to configure your app clip.

![Screen Shot 2021-04-03 at 3 47 43 PM](https://user-images.githubusercontent.com/49819455/113493415-f404f100-9493-11eb-8817-d64f2b7c7579.png)

17. Once your app has been approved, try going to `https://yourwebsite.com`. You should see the app clip!

That should be it. You can find a live example at [getfind.app](https://getfind.app/).

If you have any questions, here's my contact info:

- Discord - [aheze#3125](https://discord.com/users/743230678795288637)
- Reddit - [u/aheze](https://www.reddit.com/user/aheze)
- Email - [aheze@getfind.app](mailto:aheze@getfind.app)



