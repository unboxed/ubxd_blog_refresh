---
layout: "blog"
date: "2015-03-03 10:00:00 UTC"
published: true
title: "Guest blog: A technical guide to mobile usability testing"
author: "Rian Van Der Merwe"

---

When I worked on the agency side of user experience design I learned one thing very quickly. I learned that usability testing is the hardest thing to sell to potential clients. That is, until they observe their first session. As soon as someone sees a real user interacting with their product, all doubts about the value of usability testing gets replaced by regret that they hadn’t started doing it sooner. There is simply no better methodology for uncovering ([sometimes very expensive](http://www.uie.com/articles/three\_hund\_million\_button/)) usability problems with your product.  


Setting aside the details of recruiting, script writing, and interviewing, from a technical perspective doing usability testing on desktop web applications is pretty simple, thanks to software like [Morae](http://www.techsmith.com/morae.html) and [Silverback](http://silverbackapp.com). There is, however, no straight-forward, single solution for doing usability testing on mobile devices. I recently went through the process of setting up our own mobile usability testing process at [Jive](https://www.jivesoftware.com), so I thought I’d share some of what we learned about the components of a good setup.  


First, as with all design projects, it is important to define your constraints. What is essential, and what is nice to have? For us, a couple of things emerged as essential:  


• **It needs to be a _mobile_ lab.** To make mobile usability testing as useful as possible, we need to (duh!) be able to go where users are. We need to visit them in their offices or homes, or wherever they would normally use their devices. This means that we need a solution that is lightweight enough to take anywhere. Which leads to the second point.  


• **We need to be able to record all sessions (including user interactions).** If we’re going to be truly mobile, it is essential to record each session so that the rest of the team can view the session later. This should include video of the phone, where the user interacts, as well as a picture-in-picture view of the user’s face.  


There are other things one can compromise on, but for mobile usability testing I believe these two points are non-negotiable. So with those requirements defined, I set out, full of hope, to find a good solution.

## Prototyping
 After reviewing and trying out every prototyping tool known to man, I settled on [Proto.io](https://proto.io) as a good solution for most projects. There are so many great options out there that it’s hard to go wrong on a choice of tool. That said, Proto.io has all of the key features that I believe are important to make a mobile usability test useful:  


• **Full interactivity.** To get the best feedback prototypes need to feel as real as possible. There are tools that allow for hot spots on static mockups to approximate a real app, but that’s not truly interactive. An app doesn’t feel real unless you can select dropdowns, type into text fields, and perform some basic functionality (even if it’s faked). Proto.io is the only tool that I’ve seen that allows for this much interactivity in a mobile prototype. The best part of this is their companion app that creates a true native experience that doesn’t require loading a URL in a mobile browser.  


• **Flexibility in the animations/transitions supported.** It’s important to try out many different solutions to see how they feel (to you and to users), and Proto.io supports any interaction you can throw at it (including the fairly scarce “long tap” action).  


• **Mix and match built-in components with your own assets.** Proto.io handles this pretty well, which means you can make the fidelity of the prototype as high as your heart desires.  


This isn’t a post on how to use Proto.io, but Smashing Magazine recently published a great introduction called _[Mobile Prototyping With Proto.io](http://www.smashingmagazine.com/2015/02/19/mobile-prototyping-with-protoio/)_, and it’s definitely worth checking out.  
  

## Mobile usability testing rig
 If you’re going to record a mobile device, you’re going to need a camera and a rig. So I got lost in mobile usability testing rig guides for days. I was on the verge of giving up and just go with remote testing instead, because it just seemed like such a hassle. But I persisted because I realized it just isn’t a good option for testing prototypes. If you’d like to do part IDI (in-depth interview) and part usability testing, you need a way to be in the room with users and dig deep into certain areas.  


I’ve seen some crazy setups — my favorite and weirdest is probably MailChimp’s _[“hug your laptop”](http://blog.mailchimp.com/remote-usability-testing-on-mobile-devices/)_ idea. It’s a brilliant hack, but I’m worried about the ability of non-tech savvy users to get comfortable with this, so I needed another solution.  


I ended up going with [Bowmast](http://www.bowmast.com)’s [Mr. Tappy](http://www.mrtappy.com) kit, and I attached a [Logitech HD Pro Webcam C920](http://www.amazon.com/Logitech-Webcam-Widescreen-Calling-Recording/dp/B006JH8T3S/ref=sr\_1\_1?sr=8-1&ie=UTF8&tag=leavethegreat-20&qid=1422922486) to it. This is what it looks like with a prototype loaded on an iPhone:  


![image1](http://i1291.photobucket.com/albums/b548/grammccram/Screen%20Shot%202015-02-27%20at%2014.17.43\_zpsxgosgalf.png)  


One of the more annoying issues you’ll have to sort out is focus and brightness. With autofocus and automatic brightness adjustment, most cameras are way too smart for this kind of dynamic recording. What ends up on the screen is often blurry and/or awash in a sea of bright light — especially since the user’s fingers are frequently in the way. So you’ll need to download your camera’s OEM software to be able to adjust focus and brightness manually (I used [Logitech’s Camera Settings](https://itunes.apple.com/us/app/logitech-camera-settings/id638332853?mt=12)).  


With that out of the way, it was on to the next challenge — how to record the sessions.  
  

## Recording mobile usability tests


Recording proved much harder than I expected it to be. It turns out it’s easy to record a desktop screen and a built-in camera (see Silverback, Morae). It’s also easy to record a mobile screen natively (see [Camtasia](http://www.techsmith.com/camtasia.html)) — but of course that doesn’t record taps on the screen so you can’t tell what a user is doing (there are tools that can do that kind of interactive recording, but it uses a custom browser, and in most cases we need to test native apps, hence the need for an external camera).  


The final thing I couldn’t figure out is how to record a mobile screen (via external camera) _and_ a built-in camera (for picture-in-picture faces) at the same time.  


We were stuck.  


The solution we came up with seems like quite a hack, but it ended up working really well, and I’ll definitely use it again. The setup (for Macs) is as follows:  


• First, you’ll have to purchase [iGlasses for Mac](http://www.ecamm.com/mac/iglasses/) to have better control over which camera is used by what software. Without this your Mac will get really confused. It’s not fun.  
 • Open QuickTime, create a new movie recording, and set the camera input to the external camera (pointed to the mobile device). Don’t hit record, just let it sit there. You’re just using this as a viewer for the phone, not a recorder. Minimize all other windows.  
 • Start up Silverback and create a new usability session as you normally would for a desktop app.  


The Silverback recording will now record the desktop (which has the QuickTime viewer on the testing rig camera), as well as a picture-in-picture using the webcam. Voila! Here’s what it looks like when it’s all set up and recording:  


![image2](http://i1291.photobucket.com/albums/b548/grammccram/Screen%20Shot%202015-02-27%20at%2014.17.53\_zpsatmj9wvj.png)  


With this setup we accomplished all our goals. Everything you see in that photo can easily fit in my backpack so we can take it wherever we want. And since we’re recording all sessions the entire team is able to view the sessions once they’re all done. I do usually make highlight videos, but hey, if someone wants to watch 5 hours of usability testing on a Friday night, who am I to judge!  


I hope this guide will spark some ideas on how to get mobile usability testing going in your own work. And please, if you have a better solution for any of these steps, please let me know.  
**Further reading:**  
 • [Recording Mobile Device Usability Testing Sessions](http://www.thoughtworks.com/insights/blog/recording-mobile-device-usability-testing-sessions-–-guerrilla-style)  
 • [How we built a research lab for mobile app testing in just a few hours](http://www.gv.com/lib/how-we-built-a-research-lab-for-mobile-app-testing-in-just-a-few-hours)  
 • [Remote Usability Testing on Mobile Devices](http://blog.mailchimp.com/remote-usability-testing-on-mobile-devices/)  
 • [How to Conduct a Usability test on a Mobile Device](http://www.measuringu.com/blog/mobile-usability-test.php)  
 • [Eight Lessons in Mobile Usability Testing](http://uxmag.com/articles/eight-lessons-in-mobile-usability-testing)  
 • [Secrets From Facebook’s Mobile UX Testing Team](http://www.fastcolabs.com/3007979/open-company/secrets-facebooks-mobile-ux-testing-team)  
  
_ **About Rian:**  
 Rian is passionate about designing and building software that people love to use. After spending several years working in Silicon Valley and Cape Town, he is currently Product Design Director at Jive Software in Portland, OR. He also [blogs](http://www.elezea.com) and [tweets](https://twitter.com/RianVDM) regularly about user experience and product management._  
