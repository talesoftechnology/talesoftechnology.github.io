---
title: Pangea Cyber a Spaas for developers Part 1
date: 2023-05-10
categories: [pangea ,api, cyber security]
tags: [pangea, redact, security, secure applications]
author: verlaine
---

### **The Tale:**  

**Pangea Cyber a Spaas for developersPart 1**

Will all the continents reunite in 2023? If you are a bibliophile chances are you know Pangea as a supercontinent that incorporated all the landmasses on earth as one continent 200 to 300 million years ago, just a bit of history in a nutshell.

Let’s talk coding now,writing clean code is not as easy as we always think, every developer can build an app, but few can deliver secure solutions protecting the user’s privacy daily with different attacks from hackers.

thwarting the bad guys takes time and money, also a dedicated team of skilled professionals to secure apps and infrastructures.

During my tech journey with Cisco Devnet, I had the opportunity to learn with the **[secure code warrior tournaments and coding competition**](https://www.securecodewarrior.com/products/tournaments)** twice, the challenge gives developers the opportunity to discover vulnerabilities in different code challenges, once a vulnerability is found another stage is unlocked.

![](/assets\img\favicons\pc1.png)

The experience showed me that without proper secure coding practices, every app shipped with vulnerabilities puts the users' privacy and infrastructures at risk.

Back on May 25th, 2018, a legal framework was announced as the [General Data Protection Regulation](https://gdpr-info.eu/)(**GDPR**) that sets rules for the collection and processing of personal information of individuals within the European Union and since then, users' privacy has become trendy around the world, one of the Pangea services gives a solution to developers by respecting what the framework wants when building apps, for **PII redaction**.

The bad news is 95 % of breaches are caused by human error and the cybersecurity skills gap continues to grow!

The good news is Pangea Cyber as a Spaas comes to the rescue to help developers secure their apps and data even if they are not cybersecurity experts, integrating the Apis into their apps will secure their customers for a safer world.

you don’t have to be a cybersecurity expert to use Pangea APIs!

200 to 300 million years ago Pangea as a supercontinent incorporated all the landmasses on earth as one continent,2023 Pangea cyber as a Spaas incorporate a set of world-class APIs and reuniting all the developers for a safer cyber world by integrating the Apis into their Apps.

**What is Pangea Cyber?**

Pangea is a security platform as a service(**SPass**) that delivers comprehensive security functions which app developers can leverage with a simple call to Pangea’s APIs.

it offers foundational security services such as:

- *PII redaction*
- *Embargo*
- *Domain Intelligence*
- *Authentication*

Whether you want to integrate the APIs into your app, by following the GDPR framework restricting publishing access to personal information or quickly checking IP addresses and country codes against known sanction and embargo lists, Pangea offers everything you need as a developer for a safer cyber world.

to discover the world-class platform: <https://pangea.cloud>

**First hands-on experience with the platform**

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.002.jpeg)

Here is the landing page with insightful information for developers. By clicking in the upper corner you can log in if you have an account and signup if it’s not done yet.

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.003.jpeg)

Once logged in, Pangea shows a console and convivial interface to see what happens in the backend, the number of services activated and the experience is worth testing.

**Testing the redact service**

Since the release of the GDPR framework, I’m curious to know what happens between the European Union and tech companies, for some developers coding and shipping apps is enough as a job and they forget that without respecting some legal frameworks, their apps can be banned by legislators.

One of the Pangea services is GDPR-ready “**Redact**”, it helps developers to remove sensitive information such as **PII**, and financials, comply with privacy regulations, protect user data, and anonymize data…

With a plethora of world-class services coming all the time, I chose “**Redact**” to see how the service detects sensitive information with a simple API request.

in this short demo, I am using:

- **Ubuntu 18.04 Bionic (WSL)**
- **pip 23.1.2**
- **Python 3.7.16**
- **a Python virtual environment**
- **the cloned Pangea code sample**

to run the sample, i set environment variables.

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.004.jpeg)

the domain and token are exported,Pangea uses **aws** and **GCP** to maximize availability and minimize latency around different regions around the world.

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.005.jpeg)

I clone the git repository with the sample app.

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.006.jpeg)

i install the SDK to run the sample app.

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.007.jpeg)

After running the sample app, the redact service is able to recognize the **PII** (personally identifiable information), in the output the PII is the phone Number.

How to hide such information?

**Customs rules from the console**

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.008.jpeg)

With the sample app, I was able to see how the redact service detects the PII in the api request.

what if I want to write my own rules to detect and hide information such as Email, Nationality, location, person, and phone number?

The redact service gives available options through the PII section

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.009.jpeg)

let’s choose all the rules from the PII section and write a test like :

*Hello dear Verlaine muhungu, your mail is verlaine\*\*\*@gmail.com and your nationality is Congolese.*

*your location is Congo and your phone number is +24382082\*\*\*\**

with the PII information section, I have the possibility to choose to display my data with a mask or partial, displayed with \*\*\*.

![](Aspose.Words.9255fa55-4157-4dbf-a41b-d16c10808450.010.jpeg)

after hiding the PII it’s impossible to read sensitive information such as email, phone number, and location.

Pangea did it!

**The excitement**

security remains a big concern in our digital society, Pangea is the bridge between developers and security services for a safer world.

it’s a great opportunity for developers even with fewer security skills to secure apps.

I wanted to showcase that Pangea is precious for developers, this article is short and I hope you wanted to discover more things with my demo.

be patient i have a surprise for you for the second part, the onboarding experience was worth testing.

The documentation is top-notch, clear, and more things to discover, everything around Pangea is not difficult to use, from the console to the docs.

Will you cross the bridge to save time with your security gaps as developers?

create your account on Pangea: [https://pangea.cloud ](https://pangea.cloud)choose a service of your choice: redact, vault, or embargo Run a code sample

create your custom rules and test

do you have an app? integrate the services!

Follow Pangea on : [Linkedin](https://www.linkedin.com/company/pangea-cyber/)

[Twitter](https://twitter.com/pangeacyber)

[and Join the builders on slack](https://pangea.cloud/)

More articles on pangea Coming soon!

Follow us on [tales of technology](https://talesoftechnology.github.io) for more such articles.

our twitter profile - [toftechnology](https://twitter.com/toftechnology)

Our Linkedin profile to follow 

[Verlaine's linkedin](https://www.linkedin.com/in/verlaine-j-muhungu-363507b2/)

[Herald's linkedin](https://linkedin.com/in/herald126/)

please comment below for any queries or feedback