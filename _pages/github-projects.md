---
permalink: /github-projects/

title: Projects on GitHub
---

I'm a major proponent of having tiny personal projects that use languages / frameworks / technologies / etc.. that you don't use in your normal 40+ hour work week. Here's a few that I've made over the years.

## robertjmarlow.github.io

<div class="small"><a href="https://github.com/robertjmarlow/robertjmarlow.github.io">🔗 on GitHub</a></div>

<div class="small sub-header-bottom"><b>Technologies Used</b>: <i>Ruby css Jekyll</i></div>

👋 Hi! You are here! GitHub Pages has made it _super simple_ to get a website off the ground _and_ hosted all on GitHub. The feature I like the most is the extremely fast deployment process on every `git push`. Here's a screenshot below for a 55 second deployment from a previous commit:

![pages deployment]({{ "/assets/images/github-pages-deployment.png" | relative_url }})

## Three Trails Timelapse

<div class="small"><a href="https://github.com/robertjmarlow/threetrailstimelapse">🔗 on GitHub</a></div>

<div class="small sub-header-bottom"><b>Technologies Used</b>: <i>Java Maven Redis</i></div>

Cerner was busy constructing a huge new campus. Before it was renamed to "Innovations Campus", it was named "Three Trails Campus", referencing the [Santa Fe](https://en.wikipedia.org/wiki/Santa_Fe_Trail), [Oregon](https://en.wikipedia.org/wiki/Oregon_Trail), and [California](https://en.wikipedia.org/wiki/California_Trail) Trails that once crossed there.

The company that was constructing the fancy new campus had a webcam posted outside to view the progress which updated several times a day. I found myself clicking through entire days to watch progress but that was slow and boring. How about assembling a bunch of frames together all at once to make a timelapse?

`jsoup` was used to scrape the website for both images and text. Assembling together a date range of images was pretty straightforward. After getting all of the images, an artifact with the coordinates of `org.jcodec:jcodec-javase` was used to assemble them together into a movie.

After fiddling around with various date ranges, I was realizing that downloading these images from the construction company's website was _slow_. After recognizing that these images will never change, I decided to create a cache of the images via **Redis**. The key for the image was the URL of the image. If that key existed, the value was retrieved from Redis; otherwise, the image was downloaded from the website and then cached to Redis.

The end result was pretty neat:

<div style='position:relative; padding-bottom:calc(56.25% + 44px)'><iframe src='https://gfycat.com/ifr/WiltedEnergeticCopepod' frameborder='0' scrolling='no' width='100%' height='100%' style='position:absolute;top:0;left:0;' allowfullscreen></iframe></div>

<!-- ## Electron Demo -->
