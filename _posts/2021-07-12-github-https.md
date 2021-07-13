---
title: "Getting GitHub Pages Sites To Enforce https"
date: 2021-07-12
categories:
  - blog
tags:
  - GitHub
  - snipette
---

I've been using the [minimal mistakes theme on GitHub](https://github.com/mmistakes/minimal-mistakes) to create a website. So far I've loved it for my use cases.
Originally I was using Wixsite for a website. But I'm so used to writing on editors that I like, or Medium's WYSIWYG editor, that I became quite annoyed by Wix.
Wix is like powerpoint, except for a website. Yes everything is customizable and there's movable boxes. But I prefer something minimalist and robust, for blogs. I
could have gone ahead and made a WordPress site, but GitHub pages is free! And I love the idea of coding in interfaces as needed e.g. google analytics, comment sections, etc.

GitHub pages uses Jekyll, which is a static-site generator based in the programming language Ruby. In playing around with creating a GitHub pages site, I absolutely fell in love
with Ruby, that I had to learn from scratch. Ruby essentially imports all the libraries (called Ruby gems) needed for a specific project (e.g. website), so there are no dependency
issues! By contrast, I use Python a whole bunch, but had a huge issue building a website with a Python based static site generator known as Pelican, due to dependency issues
(maybe worth writing and article on this in of itself). The one issue with a GitHub page site is that it does not look as fresh as some paid WordPress options. For bloggers, Ghost
is becoming popular, although this also features monthly charges. Eventually I might switch to a paid option, with a better look. But for now, I'm quite comfortable with GitHub.
I like writing on my laptop editor in Markdown format (right now using Atom), and committing to GitHub. But it's important for me to have a custom domain name.


I obtained my favorite domain name  (firstnamelastname.com) - (I know I'm lucky!) on Google domains. While I found it relatively straightforward to set up a custom http domain on GitHub pages using a CNAME record, it was harder to make this domain secured through https, that GitHub just introduced a couple of years back. I would get an "ERR_TOO_MANY_REDIR" message. Probably due to a misconfiguration of the CNAME record, causing a browser to go back and forth between URLs. I did not have this message pop up when I didn't enforce https.

This was annoying as I didn't like people seeing "not secure" right next to my website. It just looks unprofessional. Maybe I'm being too nit picky. Google search didn't offer up any solutions that worked, and I ended up finding something that worked through a bunch of combinations.


<figure >
    <a href="/assets/images2/dns.png"><img src="/assets/images2/dns.png" alt="DNS configurations by Skanda Vivek"></a>
</figure>

First, I created alias name records to point my domain to the 4 IP addresses for GitHub pages site as [described in the GitHub website](https://docs.GitHub.com/en/pages/configuring-a-custom-domain-for-your-GitHub-pages-site/managing-a-custom-domain-for-your-GitHub-pages-site). Next, I created a CNAME record pointing to my github.io site. Previously I named the URL prefix as www, which is what I was told on other blogs. But that didn't work. But this time I named the URL prefix as https, which did the trick!

<figure >
    <a href="/assets/images2/GitHub-https.png"><img src="/assets/images2/GitHub-https.png" alt="GitHub pages https config  by Skanda Vivek"></a>
</figure>

Finally, I went to my GitHub pages site repository settings. Under pages, I added the custom domain pointing to my firstnamelastname.com website. Next I clicked on enforce https, and this seemed to work! Note: GitHub still says that my site is improperly configured, but everything seems to work just fine. I hope this is useful to anyone wanting to create a GitHub pages site and enforce https!
