---
title: Mobile Friendly Blogging
date: 2026-08-14
author: Akelas Maestro
categories: blog
layout: post
---

These are the notes I took while trying to find a way to make updating my website from my phone easier. I eventually settle on using GitHub Pages.  I found it really helpful to keep an on going project report like this. It's messier, but taking the time to write what I had found and what I was doing helped me navigate a complicated problem. 

Let's rewind to a couple weeks ago. Past me is worried that once the semester starts, I won't have time to manage my website. But I will be spending a lot of time on public transit and thus a lot of time on my phone...
# How can I update Neocities from my phone?

## The current Situation

My current workflow uses Jekyll to build markdown notes into a static website. The markdown files get pushed to GitHub and the built site gets pushed to Neocities. This is tedious and laptop-only. 

How else can I convert Markdown to a static website?
Can that conversion process be down with an Obsidian plugin?

## Promising Plugins

[HTML exportor](obsidian://show-plugin?id=webpage-html-export). Lets me convert notes into html. Seems to replicate whatever Publish is doing as far as style and layout goes. But I get a neat folder that I can drag and drop into Neocities. I can use the [settings](https://docs.obsidianweb.net/getting-started/7.-settings.html) to remove the side navigation bar, and insert my navigation links in the header. It even supports Dataview, so home, projects, and blog can update automatically.

I have not found other options that do exactly what I would like them to do. There are other options designed for other websites, but not neocities.

[Enveloppe](https://enveloppe.ovh/Getting%20Started/Plugin/). Lets me push notes with the "shared: true" tag in the frontmatter to be pushed to a github repo. That same github repo can be a github page which uses Jekyll to build the website and then we're off to the races! Since every published note has to be tagged explicitly, it puts another barrier between me and accidently publishing private information. 

## GitHub Pages

I really think that Enveloppe paired with a GitHub page will give me the best result. I also think I might need to rebuild the site from scratch, following the tutorials and instructions provided by GitHub pages. 

**Plan Of Action**
- get Enveloppe installed and start pushing notes to a repo
- Use Obsidian as my editor while following the [GitHub Setup tutorial](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)

We'll start there and see where it goes.

## 2026-07-31

### Step 1: Link notes to GitHub

I have linked Obsidian via the plugin Enveloppe to my github repo! I had to fiddle with the settings a little bit until I got the behavior I was looking for, but I think it's working! The main changes I made to the default Enveloppe settings are as follows:

- Share everything EXCEPT my private folder
	- I updated Obsidian to put all new notes in that private folder
	- This only sends markdown files, not photos or anything else 
- Share any linked attachments
	- Ensures any photos I include in my notes gets published as well
- Follow the folder structure inside Obsidian
	- Jekyll expects certain folders like 'posts' to work properly

This step was surprisingly painless, but there was one hick up. The Enveloppe command 'purge' doesn't seem to be working right now, so i don't have a way to remove files from the github repo from within Obsidian. I suspect the documentation I'm reading may be outdated. The only command I see is 'refresh published notes' but some experimentation suggests that that command does not remove files. My current solution is to either delete individual files using the browser or GitHub app and having a clone of the repo on my laptop for larger batch operations. Cloning the repo and having the files stored in my Obsidian vault is not memory efficient, but I only have 36 MB of website content so far. Public repos are meant to be kept down to 5 GB, so worse case I have 10 GB of storage taken up on my laptop. That is manageable. (Editor's update: [GitHub](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github#repository-size-limits) actually prefers repos stay down to 1 GB with 5 GB being a hard upper limit. If they notice your repo is causing issues they will reach out to you.)

I was able to quickly duplicate the Enveloppe settings on my phone. Publishing notes from my phone is as simple as pushing a button, which was the whole point of this exercise. I'm feeling really good. Now for the slightly harder part: getting GitHub to build my site.

### Step 2: GitHub Pages

I already know how to push the "make it a website" button in the repo settings. What I need to figure out is how to utilize Jekyll within GitHub. The good news is that I'm already vaguely familiar with Jekyll as it was what I used to build the original Neocities website. But I had troubles setting up jekyll themes, so built things up from scratch and it shows. I have a clearer idea of what I want the final site to look like, but I'm not sure how to get there. I'm going to start with following the [GitHub Setup tutorial](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll) I found yesterday and see where it takes me.

Okay, it's been another hour or two and I think It's working? I just activated pages and it needs a minute to update...

`10 minutes later`

... It's not working. At least, not like I hoped it would. Testing the site locally seems to work great. It looks identical to what I have currently on Neocities and the links work. But the very same files on GitHub are not using the my css file, aren't showing images, and the links to other parts of the site aren't working. 

I think this is due to either my janky Jekyll themeing OR the site isn't getting built when I push updates. I'm going to hope it's the first as that should be easier to fix. I'll continue with the [GitHub tutorials on Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll) and see where they take me.

`10 more mintes later`

I think I might need to let go of fixing my current theme and accepting a prebuilt version. That might solve the issue. Once the site is basically functional, I can go back and change themes or styles.

`Several hours later`

It's not working. I do not know why. testing the build locally works just fine. I think my permalinks are messed up and are conflicting with how github pages creates url's. I'm not sure how to move forward. 

`another hour later`

Holy shit, it's working! I fixed it!!!!! It's working! AHHHH!!!!!!!

I skipped a step in the initial creation. Too smart for my own good; I thought I already knew how to make a repo, so I skipped the repo creation steps in the tutorial. The GitHub repo needs to be named username.github.io in order to work. When I renamed the repo, suddenly all the links started working again! Even my custom theme is back! Only the home page is showing up as plain, default HTML text. I don't know what that's about yet, but I'll figure it out.

In attempts to get the website working, I tried using other themes and I just quite figure it out, and at this point I don't want to. It might be weird and backwards to someone who knows Jekyll better, but my site is functional! I like that it looks a little rough. It is unique. Even as I was going through the possible themes, even finding the [original theme I had meant to use](https://github.com/tajacks/lightspeed), I felt a little sad to lose my what I have put so much effort into. I'm glad to let circumstance force me to keep my own work.

**next steps:**

1) Fix the home page styling so it matches the other pages
2) Fix obsidian posting to GitHub - I think merge conflicts caused it to create a new branch
3) Fix image links since I renamed some photos

`two hours later`

Okay... The home page styling was do an faulty 'layout' option in the frontmatter. That was an easy fix.  What took so much time was trouble shooting build errors. I tried to get GitHub Actions working to build the site instead of using the github-pages gem like the tutorial mentioned by following instructions I found from [Jekyll's website](https://jekyllrb.com/docs/continuous-integration/github-actions/#control-over-gemset). But then I had two workflows building the site at once, so I removed the GitHub workflows folder for now. I have a sneaking suspicion this decision will come back to bite me, but it works for now so it stays.

I did have a brief issue with the blog and projects pages not loading their respective generated lists of content. But that seems to have fixed itself. I don't know if my browser had cached a bunch of pages and it took a while to update, or if it's related the github-pages gem. If the issue persists, I think I'll switch to using Obsidian's Dataview plugin to generate the lists instead of depending on Jekyll. Enveloppe has an option to convert Dataview renders into markdown before it sends the files to GitHub. While that creates some technical debt if I ever want to switch away from my Obsidian-GitHub workflow, it's the first and clearest solution that comes to mind.

Also, the image links don't work anymore. Previously, my post on the [watch tower](~/posts/2026-07-02-watch-tower.md) showed all the photos, but not anymore for some reason. The photos show up in Obsidian, just not the website. I'll have to take time tomorrow to figure out why.

**Next steps:**
1) figure out why image links aren't working in GitHub pages
2) fix image links in Obsidian
3) fix link between Obsidian and GitHub pages

_Sigh._ I will figure this out eventually. And when I do, it's going to so great. But man, this is taking forever.

## 2026-08-03

A few days away from a problem does wonders. 

First, it took less than 3 minutes to get Obsidian synced up with GitHub again. It looks like the plugin I'm using isn't pulling from the repo. If I make changes to the markdown files outside of Obsidian, then try to push different updates from Obsidian, the new changes go into a new branch. I simply copied the current files from the repo into my Obsidian vault so they're all up to date, and we're good to go. I just have to be careful only to use Obsidian to update the markdown content on my website, but that is kind of the point anyway.

I also noticed that my original Neocities website isn't working anymore. I think something got messed up between my custom domain, my Neocities GitHub repo, and my browser storing website info. The good news is that the GitHub pages website works just fine other than the images. 

First, I'm going to update the links in Obsidian, and then I'll go from there.

## 2026-08-06

The family and I have been travelling a lot lately, so progress has been slow. I've fixed the links in Obsidian, and now I'm pushing the updates. 


I'm going to pivot from fixing the images and get the custom domain situation in order. I'll be following the resources found on the [GitHub Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).

`30 minutes later`

For a minute, I thought I would need a separate DNS provider, but it looks like my registrar, [namecheap.com](namecheap.com), includes that service for free. It should be working now. I think it just takes a minute for the DNS servers and GitHub to get updated. FYI, the GitHub tutorial mentions running the `dig` command in the terminal, but that command is part of the `bind` package. The package goes by a few names depending on your OS, so Google accordingly.

`A few minutes of poking around`

Okay! Looks like everything is good. I did have to **delete browser history** to see the fully updated website. I have also gone and removed the custom domain from Neocities. That should be it for setting up the custom domain.

### Images on GitHub Pages

I do not know why, but the images I have in my posts aren't showing up in the website. The images show up in the markdown documents in both Obsidian and in code view of GitHub. It's just the finished site that doesn't show the images. A quick search in Chat (I use [duck.ai](duck.ai) since it's supposedly private but I can't confirm that) suggests something is off with my file paths, so I'm going to try pulling that string for a minute.

`a little while later`

So, as has been my experience, Chat's suggested solution was wrong, but it was helpful in pointing me in the right direct. I looked closer at the image links in Obsidian, GitHub, and the finished site and it turns out, when I push from Obisidian to GitHub, my image links go from absolute to relative. When Jekyll builds the site, each post gets nested into a series of folders based on the post's category and date. The relative image link in GitHub gets fed to Jekyll, and Jekyll's generated HTML looks for images inside the nested folders rather than the resources folder in the root directly. I had worried something was wrong with GitHub, but it's actually in connection between Obsidian and GitHub so it's a plugin issue.

I found the setting. Enveloppe -> Content -> Internal Links must be set to false. I had changed that setting in the initial set up thinking I was going to utilize the Dataview plugin, but I didn't.  With that setting changed, I can push the posts to GitHub again and all the photos show up!

### Compressing Images

The biggest files I have on my website are images. Most are photos, some are screenshots. None need to be high quality. Mine is not a photography blog and my website limits any images to a max height of 500 pixels for better readability anyway. Because of that fixed height limit, I can resize images and then compress them to dramatic effect. Most photos in my phone are usually a little over a megabyte in size. Depending on the purpose of the image, I can resize and compress that image to as small as 50 to 70 kilobytes. 

While working on the laptop, I tried to automate the resize-and-compress workflow but the automation was getting more and more complicated and less and less feasible to replicate on my phone. Then, while cleaning out unused apps on my phone, I realized I had already found the perfect solution! [Image Toolbox](https://f-droid.org/packages/ru.tech.imageresizershrinker/) from the F-Droid app store could already handle batch resizing and can compress images down until they meet a specified file size. 

## Conclusions

I have completed what I have I set out to do. I can now control the bulk of the content on my site from my phone. Obsidian handles text and delivery to GitHub and Image Toolbox lets me process any photos. Along the way, I found a way to save money (cancelling Neocities subscription to have a custom domain) and learned more about the functionality of GitHub Pages. Refining my website will be an ongoing process, and I already have a short list of things that need to be done, but this part at least is complete. Thanks for following along the journey.

All the best, Akelas