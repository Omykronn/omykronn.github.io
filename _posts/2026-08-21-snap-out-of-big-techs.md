---
layout: post
tags: data-sovereignty privacy self-hosting
---

I am a cybersecurity student, therefore I am sensible to what happens to my data online. So, the idea of self-hosting my own cloud application to store my documents was on my mind for a few years. But since the re-election of Trump in the US and the current geopolitical context, I want to go even further by hosting my own infrastructure where I know that my data are used by me and only me.

## Why now ?

The idea to self-host my data is not new. It appeared in my mind a few years ago after I noticed that many of my official documents are stored on [Dropbox](https://dropbox.com). But now, I considered this as pretty big privacy flaws. So, I decided to host a small file server on a Raspberry Pi that can be accessed through a VPN.

But since the comeback of Trump in the Oval Office in 2025 and his multiple forced negocations with the whole world, I started to question how I could decrease my dependance to the American IT corporations.

This feeling was even reinforced when I listened to the podcast "[L'Europe, esclave numérique des Etats-Unis ?](https://www.radiofrance.fr/franceinter/podcasts/serie-l-europe-esclave-numerique-des-etats-unis)" (litt. Europe, the digital slave of the US) by the French public radio [RadioFrance](https://www.radiofrance.fr). They hightlight both the dependance of Europe to the US through the softwares, but also juridically. The main point they focused on is the Omnibus directive currently discussed in the European Parliament. It would aim to change how personnal data are defined : instead of being globally defined in the GDPR (and so being the same for every company), each company would be able to define by themself what is a perosnnal data and so potentially avoid the application of the GDPR.

## Big Techs know a lot on me

If I want to build my own infrastructure, I need to know which applications I want to stop using to replace them by open-source and self-hosted ones. So I made this list with less or more the software/company and what features I use :

- Google
    - Email client (Gmail)
    - Online file storage (Drive & Photos)
    - Video streaming (Youtube)
    - Application distribution system (Play Store)
    - DNS (8.8.8.8)
- Facebook, Instagram & WhatsApp (Meta)
    - Social media
    - Messaging
- Garmin and Strava
    - Workout tracking
- DropBox:
    - Online file storage
- Linkedin (Microsoft)
    - Professional social medium
- OneDrive (Microsoft)
    - Online file storage
    - File editing

So, there exists some servers where one can find my hobbys, some links to my relatives, my "official" life and my biometrics. Hopefully, it is not one same server owned by only one s company, but this still raise serious concerns. 

## PC: good, phone: (very) bad

A lot of data is collected by the softwares one uses, but the hardware used can also induce some privacy leaks. In my case, I consider my PC quite safe : I moved to Debian five years ago. Since, I use open-source softwares with a big enough community to be sure of their quality. I am also very careful on their configuration in order to not send data.

On the other hand, I also have an Android smartphone as I need one, mostly because of my bank. My phone has always focused most of my privacy concerns as I don't understand its system as well as I do for a computer. This has changed recently after a lecture on the Android system, which looks quite good for privacy with its permissions (on the paper at least).

But, still knowing that each smartphone company wraps the vanilla Android kernel with a closed source layer disturbs me.



Indeed, I own a Google Pixel 7a which looks very strange for someone trying to quit Big Techs. And it is : Google constantly offers you to save your pictures, contacts and passwords on its cloud. But the true reason why I still have it is that I want to change its OS to [GrapheneOS](https://grapheneos.org/) which is an open-source Android implementation focused on security and privacy. And for this, you need a Google Pixel as they are the only devices which support GrapheneOS because they embed the "purest" Android kernel.

I migrated my phone to GrapheneOS a few months ago but I had to switch back to Google OS as I wasn't able to emit bank transfers. But since, I found [this repositry](https://privsec.dev/posts/android/banking-applications-compatibility-with-grapheneos/#international-banking-apps) which lists which bank app can be used normally on GrapheneOS. So, I should move again to GrapheneOS.


## It's gonna be challenging

As listed before, I have a broad usage of a lot of different apps. So, building my own infrastructure which will satisfy me is going to be a long and time-consuming project which will require a lot of researches. Of course, it has to be secure too.

Some usages like email messaging or file hosting are quite easy to self host. I will use the [Awesome-Selfhosted list](https://awesome-selfhosted.net/) to find open-source softwares which fit to my needs.

Other ones are not that simple to replace, mostly when they involve communication with other people. That's why I will continue to use Instgram and WhatsApp in order to still be able to communicate with my family and my friends. But I will use them only for communication purposes and use a self-hosted application for pictures sharing.

For now, I tried to reduce the variety of private data I store on the cloud, mostly on focusing on my biometrics sent to Garmin and Strava. I used to always upload my daily workouts to Garmin Connect, which were then synced with Strava. After giving it some thoughts, I concluded that it was not necessary. So, I deleted my Garmin account. I still have a Strava account, but I upload there only activities from competitions manually without heart rate and breathing rythm data.
