# HTML Favicon

Have you noticed how all or 99% of your browser tabs have their own distinguishing logo on the side? Well that was the coolest thing (back in 1999) when Internet Explorer first supported it. This little image or icon is referred as the **favicon**, which stands for favorite icon. Although not required, the favicon is now pretty standard, used also for shortcuts across multiple devices. So all website and web apps should implement favicon(s) to distinguish themselves. 

## Adding a Favicon - The Traditional Way

Let's suppose you've finished your kick-ass app using the latest technology. You now want to add some flare and make sure that when someone visits your URL, it has a distinguishable icon that identifies your app. You have your design ready, and now you want to add your favicon to the page. 

Now, first you have to make sure your image is either already an ICO file or save it PNG (to preserve transparency) of at least 16x16 size and then convert it to ICO. 

*Why are we converting to ICO*? Because browsers have many resolutions, and favicons are also used as **shortcut icons**, so an ICO file will actually contain many PNG images inside to support different resolutions and shortcuts.

You can use one of the many online tools out there to convert our ICO from PNG. 

Now, it is commonly believed that your website will pick your favicon from the root directory. However as a practice, let's add this to your index.html on the `<head>` tag: 

```html
<link rel="icon" href="/favicon.ico" type="image/x-icon">
```

Refresh and check your icon pop up on the the tab! If you ever get a favicon.ico Not Found error, just make sure the icon is placed at the root folder and that your index.html is placed accordingly in relation to the favicon.

## Adding Favicon(s) - The Recommended Way

You might notice that when you add the ICO favicon, it might not work perfectly across all resolutions. This is because the ICO format is not as reliable anymore. To fix this, HTML5 introduced the `sizes` attribute so we could rely directly on PNG files. So now we don't have to compress down to an ICO! 

We can just save our PNG image in three sizes to match the favicon (16x16), taskbar (32x32) and shortcut icons (32x32). Then our HTML `<head>` tag can be changed as:

```html
<link rel="icon" type="image/png" href="/favicon16x16.png" sizes="16x16">
<link rel="icon" type="image/png" href="/favicon32x32.png" sizes="32x32">
<link rel="icon" type="image/png" href="/favicon96x96.png" sizes="96x96">
```

This should make our website or app more consistent with modern standards! 

## More Favicons - Getting More Complicated

When it comes to mobile support or even larger displays, our favicon list can start expanding. Take for example the `apple-touch-icon`, which is basically the icon when you add to home screen on an iOS device. Well, if you want to optimize for iOS devices, yes you'll need an specific favicon for that. So behold, our list of favicons grows:

```html
<link rel="apple-touch-icon" sizes="72x72" href="touch-icon-ipad.png" />
<link rel="apple-touch-icon" sizes="114x114" href="touch-icon-iphone.png" />
<link rel="apple-touch-icon" sizes="152x152" href="touch-icon-ipad-retina.png" />
```
Then you might ask, what about Android devices? Wait, how did we get from that single and *fabulous* favicon.ico to an ever-growing list of them? 🤦🏻‍♂️😅

## Conclusion

There are great [open source references](https://github.com/audreyfeldroy/favicon-cheat-sheet) and plenty of favicon generators to help you in your way. However, the reality is that often for a smaller app or portfolio project, you might not have the time or bandwidth to cover most or all of the favicon instances. 

At the end it all boils down to your own needs. Feel free to experiment with what works with you. A good strategy will be to **start by having a favicon.ico, 32x32 PNG and 152x152 PNG favicons, and grow from there**.

So, if you came here to learn about how to implement a single favicon to show it on the tab and maybe a shortcut, you're wrong. Today, there are a *minion* favicons to display across all devices, shortcuts, home-screen, and yes the list keeps growing!

![minion-favicons](https://media.giphy.com/media/10S4rk0J10AKlO/giphy.gif)

