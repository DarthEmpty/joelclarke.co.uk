---
layout: default
---

So, it's finally here! My website - complete with blog and gallery - has finally managed to reach a decent standard and find a spot for itself on the internet.

:tada: **Yay!** :tada:

This is kinda big for me mainly because this is the first time I've done something like this. Turns out, I tend to focus on academic work when it calls - which is basically why this hasn't been done earlier than now. I did attempt to make a personal website around a year ago but, for some reason or another, I didn't manage to make very much of it during the Summer before my 3rd year at Uni started. Long story short, the site ended up taking a backseat. Once 3rd year was over and done with, however, I had *loads* of time to just sit back and work solidly on it.

*And it was a lot easier than I thought it was going to be.*

Honestly, It's probably never been easier to set up a secure static blog. Now that [GitHub Pages supports HTTPS for custom domains](https://blog.github.com/2018-05-01-github-pages-custom-domains-https/), it's relatively simple to:

1. Set up a GitHub repository to host your site for free
2. Create said site
3. Buy a domain and use it as an alias for said site
4. Attain a free SSL Certificate for said site

What's hard, however, is finding instructions on how to do all of this (probably because doing all of this wasn't possible until just over a month ago). I found this quite frustrating, thus this blog post was born.

Hopefully, by the end of this, you'll have a website that works like mine. It might be better looking than mine and it might be more useful than mine but it'll be on the internet, under your preferred domain name, encrypted on the wire for nothing but the price of your domain name.

**Please Note:** This post assumes that you have basic knowledge of Git and GitHub.

## Hosting the Site Using GitHub Pages

The first step to creating any project stored on GitHub is to make a repository for it. This is simple enough - the difference here being that you'll be using your repository as a web server through [GitHub Pages](https://pages.github.com/).

Initialise a new repository on GitHub under the name `<your-username>.github.io`. The name is *very* important - it's what tells GitHub that you want to use the repository to host a website using GitHub Pages.

Clone the new repository before following the next step.

## Creating a Site

Your site can be created any which way you want. As long as it's static and stored in the repository set up and cloned previously, GitHub Pages will be able to host it with no issues.

I do, however, highly recommend that you use [Jekyll](https://jekyllrb.com/), a really simple static site generator, when doing so. I can testify to it being a very easy way to create web pages using Markdown and to maintain a blog with little hassle.

If you do decide to use Jekyll and you're new to it, I would give [this tutorial](https://www.taniarascia.com/make-a-static-website-with-jekyll/) a go - it walks you through how to generate a static site, how to make your own custom theme, and more. I found it very helpful when creating this site, in fact!

**Please Note:** Some of the steps will be unnecessary in your case. However, it should be relatively easy to figure out which steps are such and to figure out what to do instead. For example, when reaching the section entitled *Install Jekyll*, you won't have to initialise another repository. Instead, you can achieve the same effect by just running:

```bash
jekyll new <path/to/your/repository>
```

## Getting a Custom Domain

:confetti_ball: **Congratulations!** :confetti_ball: By this point, your brand new static site should be on the internet for all the world to see (provided that you've pushed your site up). You can see it too by visiting `<your-username>.github.io`.

That's a good looking website that deserves a good looking domain name to go with it!

You'll need to buy an available domain name from a Domain Name Registrar. Personally, if you're going to buy it from anybody, I would recommend [gandi.net](https://www.gandi.net) simply because their slogan is literally *No bullshit*. 

Once you've bought the domain name, you can go to your repository's settings and go to the *GitHub Pages* section. There, you'll see a *Custom Domain* subsection. Fill the text field in said subsection with your domain name as below.

![Custom Domain Subsection](/assets/images/custom_domain.png)

You may have to wait a few hours or so before you can edit the Domain's DNS records but that's what you'll be doing next (With Gandi, this is done by going to the [Domain Admin Page](https://admin.gandi.net/domain/) and clicking on the appropriate domain name, followed by *DNS Records*).

**Remove all records that are currently stored.** Then, you'll want to create 4 new DNS records of type A pointing to the following IP Addresses:

- 185.199.108.153
- 185.199.109.153
- 185.199.110.153
- 185.199.111.153

After that, visit the repository settings on GitHub 

Then go to sleep. It takes a very long time for Registrars to update your DNS records so you'll be waiting a long time before you can access your website through its new domain name.

## Getting an SSL Certificate

When you wake up, go and check out your website using your new domain name. We're very nearly done - now just to make sure that all users that access the site can access it securely through HTTPS.

Thankfully, this bit is very easy. GitHub Pages has paired with [Let's Encrypt](https://letsencrypt.org/) to provide free, automatic SSL Certificates to everyone using GitHub Pages. All you have to do is go back to your GitHub repository settings, go back to the *GitHub Pages* section and, this time, go to the subsection entitled *Enforce HTTPS*.

![Enforce HTTPS Subsection](/assets/images/enforce_https.png)

However, there are 2 possible error messages that may appear next to the checkbox, preventing you from checking it:

- **Not yet available for your site because the certificate has not finished being issued**

  This just means that GitHub is busy generating your SSL Certificate necessary for enforcing HTTPS. Eventually, the message will go away and you should be able to check the box.

- **Unavailable for your site because you have a custom domain configured**
  
  All you need to do here is add the custom domain name again. This is done by going back to the *Custom Domain* subsection, removing the custom domain, saving, re-entering it and saving again. This error message had me stumped for a good long while and I only solved the issue thanks to [this blog post](https://timeandupdate.com/2018/05/custom-domain-in-github-page-support-https/).

And that's it! Now, when you visit your site, you can rest with the knowledge that it has a free SSL Certificate; that it's hosted using a free, easy to use system; and that it can be found under your custom domain name :+1:.