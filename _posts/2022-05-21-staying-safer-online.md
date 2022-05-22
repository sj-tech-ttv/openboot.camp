---
layout: post
title:  "Staying Safer Online"
date:   2022-05-21
excerpt: "You can't be safe, but you can be safer"
image: "/images/pic06.jpg"
---

Staying safe online has been an issue as long as there's been an internet. Although some things have changed, many things have not. 80% of online safety is just thinking about what you put online, who and what you trust online, as well as some basic password management. This guide is focused on the most basic things you can do, such as regularly checking what others can see about you, verifying that you're talking to who you think you're talking to, never reusing passwords, and using two factor authentication (2fa). Without further ado, let's get started.

## Who knows what about me, and how do they know?
Seeing what's publically available about you online can be as simple as googling your username. This isn't everything out there about you, but it's a simple way to start if you have a unique enough username. Googling yourself occasionally lets you know what other people can figure out about you easily. If you find something that could potentially dox you, you can either attempt to remove the content from the website serving it, or you can ask Google to take down the search result by [following these instructions](https://support.google.com/websearch/troubleshooter/3111061#ts=2889054). The information will still be available on the website hosting it, but it won't show up in Google's search results. There are plenty more sources of information you can use that are similarly freely available, some of which I will describe below. Looking for your username or information with some of these tools can help you understand what people can find out about you.

#### What is OSINT?
OSINT stands for Open Source Intelligence. What that means is gathering information from sources that are publicly available. Even something as simple as googling yourself, as described above, is open source intelligence. There are many more sources that are more complicated, but it can be that easy to gather.

#### Reverse Image Search
Posting the same image from multiple accounts can be a good way for people to connect the dots between accounts. For example, posting a picture you posted on Facebook or Instagram in Discord can lead people to from Discord to your Facebook or Instagram via a reverse image search. Some examples of reverse image search sites are [https://images.google.com](https://images.google.com), [https://tineye.com/](https://tineye.com/), and [https://yandex.com/images/](https://yandex.com/images/). The image doesn't need to be the same size to show up in a reverse image search, but they usually do have to have the same proportions, so the ways to defeat a reverse image search include cropping part of the image so the proportions don't match, flipping the image, rotating slightly then cropping the image, and other similar transformations of the image. Sometimes, these are even sufficient to trick image classification neural networks, but things like adversarial images are ever better at tricking things like that. We won't get into that topic today, though.

#### EXIF data in images
Common image formats like JPEG, PNG, TIFF, and others make room within the image file for information about the image. This space is called Exchangeable Image File, or EXIF for short. Different cameras store different information, for example, a DSLR camera might store information about the camera's model, the lens, focal distance, color correction, contrast, and so on. Some cameras have GPSes so you can see where your photos were taken. Your phone might store your phone's model, your Apple username, along with some of the same things that a DSLR camera stores like color and contrast information. If you want to look at an image's EXIF data, you can upload images to [https://exif.tools](https://exif.tools), or there are likely software libraries for your favorite programming language if you want to access this data programatically. For safety, most social media websites strip this information after uploading your image, and prior to displaying your image, however it's good to assume that EXIF data is preserved if you're not completely sure. Discord didn't strip EXIF data on images until 2 years ago. Parler never stripped EXIF data, and when all images uploaded became public, all location data associated with those images was still attached, which helped to implicate numerous people involved in January 6th in Washington DC. Even if the social media service strips EXIF data, know that the company who you're providing data to likely mines this data and preserves it for their own purposes. Stripping this data yourself can be as simple as taking a screenshot of the image you want to share instead of sharing it directly. Again, there's probably a library for your favorite programming language which can also allow you to strip or spoof data more directly, but it's easy enough to just take a screenshot of your picture, no need to make it complicated.

#### Sherlock
Sherlock is a tool for identifying users across multiple platforms. Think of it as a search engine for usernames. You can find the source code for the tool at [https://github.com/sherlock-project/sherlock](https://github.com/sherlock-project/sherlock). Clone the repo, create a virtualenv, and install dependencies in your venv. Once you've set up the necessary dependencies, you can run Sherlock from the command line, by running `python3 sherlock/sherlock.py <username>`. It should start listing accounts as soon as you hit enter. You can search multiple usernames at the same time just by adding them at the end of that command, so if you want to search for some variations on user account names without running Sherlock more than once, you can.

#### Other OSINT sources
There are plenty more sources of information. Some other sources you can use are outlined in the link below:

[https://github.com/jivoi/awesome-osint](https://github.com/jivoi/awesome-osint)

## Foiling Corporate data collection
While the previous section was more focused on knowing what information is publicly available about you, this will be more focused on 

#### Ad Blockers
#### Other Privacy Extensions

## Username safety
Picking a username is a necessary part of being online. This is how people will know you and refer to you, so it's important to pick a username you like, that tells other people as little about you as possible. A popular format for usernames is to put your first initial and last name 

## Password safety

#### Never reuse passwords
#### Password managers
#### Have I been pwned?
[https://haveibeenpwned.com/](https://haveibeenpwned.com/)


## Are you sure you're talking to who you think you're talking to?

#### HTTPS certificates
#### Email headers


## Anonymity tools and how they fail

#### VPNs and TOR