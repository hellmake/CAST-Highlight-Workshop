---
title: "Software Composition Analysis"
chapter: true
weight: 2
---

# Software Composition Analysis
It's no secret that developers don't like to reinvent the wheel. It is therefore a good thing that there are many wheels available out there *for free*: online repositories such as Maven and Npm host literally millions of packages and libraries that will enable you to create PDFs, manage secure connections or draw fractals (and much more) at the cost of a single *Include* in your project file. 

What's often overlooked, though, is that by adding these third-party libraries to your code, you become dependent on them: what happens when the package's developer loses interest and stops maintaing it? What if you encounter a rare bug that needs urgent solving? What will you do if this 5-year old library stops working when you upgrade your app to the latest version of *.Net Core*? ***Obsolescence*** of third-party code is a very real threat to many IT departments... and it's not the only one.

By the way, when you downloaded this nifty *tool-that-makes-colorful-worksheets-from-your-data*, did you really read the *License Agreement* that it came with? You know, the one that says that the app you're now selling should be entirely *Open-Sourced*. Many development teams don't worry about this and they sometimes end up creating situations that would make an IP lawyer faint. ***Licensing Risks*** hiding behind proprietary applications embedding open-source code are an ever growing area of concern for organizations.

Furthermore, what would happen if this core open-source library that everybody uses had a massive [security weakness](https://www.ncsc.gov.uk/information/log4j-vulnerability-what-everyone-needs-to-know) that potentially [exposes the data](https://heartbleed.com/) of thousands of companies? There's a lot of publicly available information out there to help us prevent this, but are we using it? ***Security Vulnerabilities*** embedded into open-source libraries are something companies can't afford to miss... especially if they're in the process of moving their applications to a place where they can be reached much more easily (aka *the Cloud*).

## The Application's Software Composition Dashboard
Our application's ***SCA*** dashboard looks like this:
![SCA Dashboard](/images/DetailedSCA-1.png)

There's lots going on here:
- We see that there are many third-party libraries embedded within our codebase
	- CAST Highlight detects them either from them being required within the project files or from actually finding the package's files within the scanned code (CAST has an ever-growing database containing the *fingerprints* of every version of every file of every package we can find on popular repositories. Every file scanned is checked against that database.)
- Some packages are quite old
- There is a ***High-Risk Licenses***
- There are a number of ***High and Medium Severity Security Vulnerabilities*** related to those packages.

Let's start with the ***Vulnerabilities*** subtab:
![Vulnerabilities Button](/images/Vulnerabilities-Button.png)

### CVEs and CWEs
According to the US [National Institute of Standards and Technology](https://nvd.nist.gov/vuln), *The Common Vulnerabilities and Exposures ***(CVE)*** Program’s primary purpose is to uniquely identify vulnerabilities and to associate specific versions of code bases to those vulnerabilities.*
This organization hosts a public database detailing all known security issues of open-source packages. 

Since this information is out in the open, it's a safe bet that hackers know about the security hole in *that unpatched library we use to secure our connections*. Let's see what we can do about it:
![Vulnerabilities](/images/DetailedSCA-2.png)

Sorting by the ***CVE*** column, we see the most vulnerable packages associated with our application. We can click on any of jetty's red boxes of high-severity vulnerabilities to get details on them:
![Critical CVEs](/images/DetailedSCA-3.png)
This piece of information is important as it will allow the application's team to evaluate their actual exposure to the identified risks and better decide what to do about it. Most of the time an update of the library is enough to solve most issues, which we can check by clicking on the component's name:
![Component Timeline](/images/DetailedSCA-4.png)
On this ***Component's Timeline*** we can see that the latest version is only affected by a single medium-severity CVE, which may or may not be acceptable for us.

[The next most problematic component on this list is Log4j: on top of sporting several (yet unresolved) CVEs, you'll see that by performing a thorough analysis of its code using ***CAST Imaging***, we have also identified several ***Common Weaknesses (CWEs)*** in there. Clicking on the little black tile brings up their list:]: #

### Licenses and obsolescence
![Licenses Button](/images/Licenses-Button.png)
Going to the ***Licenses*** subtab you can find a breakdown of the licenses claimed by the third-party libraries. We suggest to focus on the red (High Risk) ones. Clicking on an individual license brings up the license's text and a summary of what it allows and doesn't allow.
![License Details](/images/DetailedSCA-6.png)
... maybe we'll want to have a lawyer take a look at this.

Finally, clicking on the ***Obsolescence*** subtab, we can see which components have the biggest gap between the version used and the latest available one... 10 years is quite a long time.
![License Details](/images/DetailedSCA-7.png)

As with the other topics, we can get a compiled version of this feedback by clicking on the ***Download BOM*** button in the upper-right part of the dashboard. This will let you choose the format in which you'd like to get your *Software Bill of Materials*.

### The path to clean code
So, is our code good now that we've removed cloud Blockers and vulnerable dependencies? Well, there's still some things we should look at...
