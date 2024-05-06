+++
title = 'CI/CD is Awesome'
date = 2024-04-14T22:00:25-05:00
draft = true
type = 'post'
+++
So I have been playing around with Cloudflare Pages to host my Status Site for my company. Cloudflare has the option to pull and deploy your project directly from GitHub, which is cool. But it wasn't til I tested entire workflow did I realized what my 'trash' deployment process I have been using. 

I knew that CD/CI (Continuous Deployment/Continuous Integration) made development easier to do. But I didn't realize how quickly and efficiency it did it. I have used all the little parts of the CD/CI pipe line over the years, but I have never had them all just work together to deliver the final product to production.

So I recently setup Gitea as local VM and I have started it using it more, since I know if I commit sensitive information no one is going to see. _I don't want to want to do that but things happen_. I have also started playing around with [Hugo](https://gohugo.io), for this site. I decided that I wanted to put Hugo through it pace with a 'real' project, so I decided that I wanted to move my company's [status site](https://status.madscitech.net) away from Tumblr. 

<aside class="pullRight"><strong>Aside</strong>: Funny thing is I found while doing this that Tumblr is going to start charging for custom domains, but my account is currently grandfather in with an existing domain. So this project was well timed.</aside> 

I wanted have more control over the design and continue my over arching goal owning my data and the services I use. (Well as much as you can own the 'cloud'.)

So I had to figure out where I was going to host the site because if my primary server is down, so wouldn't the status site. My initial thought was just throw it up on AWS S3 Bucket. So I started to look for a way to have the git repo pull or pushed to the S3 bucket. Then I remembered that GitHub Pages exist, I have used that in the past but it was clunky and had to use Jekyll. But it seem to allow other options now. The I remember Cloudflare Pages/Workers is also exist and also free. 'Well I'm not really use much over at Cloudflare, let try Pages out', I thought to myself. 

So let go over the plan, I work on the Hugo site locally, which is git tracked in git. Then I will push code to my local Gitea Server, which in turn push the code to GitHub, where Cloudflare connects to the repo. Then Cloudflare will pull the code, build the site and deploy it on there network/CDN. All of this happens under 30 seconds because this particular static sites is small (less than 3 MiB). I don't even have enough time to load the GitHub Repo before it done deploying. 

There is one problem with this system...

I usually push code to my remote repos when I'm done for the day or if I'm going to be away from my keyboard for while. And I tend to work only on the 'main' branch, instead of creating a new branch for each feature or task 😒🤷‍♂️ (iknow). 

<aside class="pullRight"> <strong>Why</strong> I tend to push code to the remote just in case something happens to the local workstation. So if the local machine has a problem, my changes are not lost with that machine.</aside>

It only ever been myself on the repos I work on, so working on main (master) has been my method for years. I learned Git thinking that main was unstable/bleeding edge of development, while tags/branches were cut for 'stable' releases. In my world everything is always on the unstable, if something is broken, it going to be changed fast. But with this setup I'm going to start forcing my self to work in branches, like I'm suppose to do.

----

The next thing up in the automation train, how to setup CD pipe line for WordPress Themes. My current setup uses; PHP script, webhook and git, but it has been busted for long while now. I will write up solution, when I figure out a plan there. 

If you have suggestions, tag me on [Twitter](https://twitter.com/mad9scientist) or [contact me](https://mad9scientist.com/about/contact/).
