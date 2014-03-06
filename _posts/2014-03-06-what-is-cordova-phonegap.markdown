---
layout: post
title:  "What the Cordova?"
date:   "2014-03-06 08:00:00"
categories: ionic
author: '<img src="http://www.gravatar.com/avatar/e130a4be9fba5eb5d932c813fbe3a58d?s=48&amp;d=mm" class="author-icon"><a href="http://twitter.com/maxlynch" target="_blank">@maxlynch</a>'
published: false
---

As we've built out Ionic, we've gotten a ton of questions about Cordova and PhoneGap. These range from confusion with the naming (are Cordova and PhoneGap the same thing?), to a misunderstanding of the goals and capabilities of these projects.

## A quick history lesson

PhoneGap proper was created around 2009 by a startup called Nitobi as an open source way to access the "native" environment through an embedded Web View in a native app. The goal of the project was to make it possible to build the bulk of a mobile app experience with pure web technologies like HTML5, CSS, and Javascript, but still be able to call into native code when necessary.

In 2011 Adobe purchased Nitobi and with it the rights to the PhoneGap brand, and the open source core was donated to the [Apache Software Foundation](http://apache.org/) under the name Cordova.

## A rose by any other name

So what is the difference between Cordova and PhoneGap? One helpful analogy Adobe uses is Cordova is to WebKit as PhoneGap is to Chrome. PhoneGap is Cordova plus extra Adobe stuff.

At first, the differences between Cordova and PhoneGap were minimal. But Adobe always had plans to build out a proprietary set of services around the PhoneGap ecosystem, and has started to execute on that plan with PhoneGap Build.

So, when you start a new hybrid app project, you can either decide to use Cordova proper, or enter into Adobe's ecosystem and use the PhoneGap distribution of Cordova.

Note: Ionic uses Cordova proper at the core, we do not use PhoneGap at all (though it can be used just fine).

## You don't know what I'm capable of!

At its core, Cordova offers a simple but powerful API to call Javascript functions that map to native code or plugins. This means you can transfer any kind of data across from the native land into the web land. 

This is something people don't always realize. Cordova is capable of pretty much anything you need to do on mobile. It's a powerful low-level API that comes with a set of pre-made, simple plugins to do things like access the camera or compass.

Also, mobile devices didn't run web content very well until the iPhone 4S generation, so PhoneGap had a reputation for being slow. That is no longer the case with today's devices.

## Part technology, part dream

So if Cordova can do anything native apps can do, why doesn't it seem like it? For that, you can thank the vision of the project.

Adobe has always said that the big goal of Cordova is to make itself obsolete. Basically, that Cordova's feature APIs would eventually implemented by browser vendors, making the project less necessary.

Take, for example, the Geolocation API. While GPS on mobile was made popular with the iPhone, mobile browsers didn't support it well until later. So, Cordova built bridge for that, through a `navigator.geolocation` Javascript object that they expected or wanted to become the standard in the future. Cordova uses the native browser implementation when available, or uses the bridge when it's not.

The same thing can be seen today with the `navigator.camera` API. This is a very simple API for getting a picture from a device's camera. You might imagine browsers offering this as a standard in the future.

So, Cordova is part low-level bridge, and part simple browser-style API. This means the API available for doing things like interacting with the camera is overly simple, and can be limiting when trying to create really custom native apps (like Instagram, for example).

## Plugins!

I personally disagree with that interpretation of Cordova's vision. I think we should be working toward a better, more standard browser, but we should also be enabling creation of really creative and unique apps through a more powerful and generic browser-to-native API.

This is the difference between the existing `navigator.camera.getPicture()` API and a theoretical `navigator.camera.getPhotos(start, count)`. The first uses a pre-defined UI, and the latter leaves it up to you to build the experience.

Luckily, Cordova has a high quality plugin API, we just need more great plugins that expose *data* from the native layer, not just hard coded features or UIs.