---
title: "Getting Github Pages Sites To Enforce https"
date: 2021-07-08
categories:
  - blog
tags:
  - github
  - snipette
---

I've been using the [minimal mistakes theme on Github](https://github.com/mmistakes/minimal-mistakes) to create a website. So far I've loved it for my use cases.
Originally I was using wixsite for a website. But I'm so used to writing on editors that I like, or Medium's WYSIWYG editor, that I became quite annoyed by wix.
Wix is like powerpoint, except for a website. Yes everything is customizable and there's movable boxes. But I prefer something minimalist and robust, for blogs. I
could have gone ahead and made a wordpress site, but Github pages is free! And I love the idea of coding in interfaces as needed e.g. google analytics, comment sections, etc.

Github pages uses Jekyll, which is a static-site generator based in the programming language Ruby. In playing around with creating a Github pages site, I absolutely fell in love
with Ruby, that I had to learn from scratch. Ruby essentially imports all the libraries (called Ruby gems) needed for a specific project (e.g. website), so there are no dependency
issues! By contrast, I use Python a whole bunch, but had a huge issue building a website with a Python based static site generator known as Pelican, due to dependency issues
(maybe worth writing and article on this in of itself). The one issue with a Github page site is that it does not look as fresh as some paid wordpress options. For bloggers, Ghost
is becoming popular, although this also features monthly charges. Eventually I might switch to a paid option, with a better look. But for now, I'm quite comfortable with Github.
I like writing on my laptop editor in Markdown format (right now using Atom), and committing to Github. But it's important for me to have a custom domain name.


I obtained my favorite domain name  (firstnamelastname.com) - (I know I'm lucky!) on Google domains. While I found it relatively straightforward to set up a custom http domain on Github pages using a CNAME record, it was harder to make this domain secured through https, that Github just introduced a couple of years back. This was annoying as I didn't like people seeing "not secure" right next to my website. It just looks unprofessional. Maybe I'm being too nit picky. Google didn't offer up any solutions that worked, and I ended up finding something that worked through a bunch of combinations.


<figure >
    <a href="/assets/images2/dns.png"><img src="/assets/images2/dns.png" alt="DNS configurations by Skanda Vivek"></a>
</figure>

First, I created alias name records to point my domain to the 4 IP addresses for Github pages site as [described in the Github webiste](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site). Next, I created a CNAME record pointing to my github.io site.

<figure >
    <a href="/assets/images2/github-https.png"><img src="/assets/images2/github-https.png" alt="Github pages https config  by Skanda Vivek"></a>
</figure>

Finally, I went to my Github pages site repository settings. Under pages, I added the custom domain pointing to my firstnamelastname.com website. Next I clicked on enfore https, and this seemed to work! Note: Github still says that my site is improperly configured, but everything seems to work just fine. I hope this is useful to anyone wanting to create a Github pages site and enfore https!
