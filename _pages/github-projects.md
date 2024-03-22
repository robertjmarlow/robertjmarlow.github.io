---
permalink: /github-projects

title: Projects on GitHub
---

I'm a major proponent of having tiny personal projects that use languages / frameworks / technologies / etc.. that you don't use in your normal 40+ hour work week. Here's a few that I've made over the years.

## robertjmarlow.github.io

<div class="small"><a href="https://github.com/robertjmarlow/robertjmarlow.github.io">🔗 on GitHub</a></div>

<div class="small sub-header-bottom"><b>Technologies Used</b>: <i>Ruby css Jekyll</i></div>

👋 Hi! You are here! GitHub Pages has made it _super simple_ to get a website off the ground _and_ hosted all on GitHub. The feature I like the most is the extremely fast deployment process on every `git push`. Here's a screenshot below for a 55 second deployment from a commit:

![pages deployment]({{ "/assets/images/github-pages-deployment.png" | relative_url }})

## Three Trails Timelapse

<div class="small"><a href="https://github.com/robertjmarlow/threetrailstimelapse">🔗 on GitHub</a></div>

<div class="small sub-header-bottom"><b>Technologies Used</b>: <i>Java Maven Redis</i></div>

Cerner was busy constructing a huge new campus. Before it was renamed to "Innovations Campus", it was named "Three Trails Campus", referencing the [Santa Fe](https://en.wikipedia.org/wiki/Santa_Fe_Trail), [Oregon](https://en.wikipedia.org/wiki/Oregon_Trail), and [California](https://en.wikipedia.org/wiki/California_Trail) Trails that once crossed there.

The company that was constructing the fancy new campus had a webcam posted outside to view the progress which updated several times a day. I found myself clicking through entire days to watch progress but that was slow and boring. How about assembling a bunch of frames together all at once to make a timelapse?

`jsoup` was used to scrape the website for both images and text. Assembling together a date range of images was pretty straightforward. After getting all of the images, an artifact with the coordinates of `org.jcodec:jcodec-javase` was used to assemble them together into a movie.

After fiddling around with various date ranges, I was realizing that downloading these images from the construction company's website was _slow_. After recognizing that these images will never change, I decided to create a cache of the images via **Redis**. The key for the image was the URL of the image. If that key existed, the value was retrieved from Redis; otherwise, the image was downloaded from the website and then cached to Redis.

The end result was pretty neat:

<div class="small">...There used to be an animation here but it appears to have been removed from the host 😭</div>

## Blog Spring Boot Kotlin

<div class="small"><a href="https://github.com/robertjmarlow/blog-spring-boot-kotlin">🔗 on GitHub</a></div>

<div class="small sub-header-bottom"><b>Technologies Used</b>: <i>Kotlin Gradle Spring Hibernate</i></div>

I have a _lot_ of experience with [Eclipse Jersey](https://eclipse-ee4j.github.io/jersey/) as a JAX-RS implementation. However, I knew that [Spring](https://spring.io/) and [Spring Boot](https://spring.io/projects/spring-boot) are _very very_ widely used throughout the industry. Spring Boot gives an opinionated set of dependencies, tooling, and environments that have been proven.

Not wanting to completely miss out, I started to go through [a simple Spring Boot + Kotlin tutorial](https://spring.io/guides/tutorials/spring-boot-kotlin/). I've barely used Kotlin and Gradle so there were a _bunch_ of learning curves to go up.

After getting to the end, I started to see what else I could add. Other stuff added:

- **Better unit test code coverage** A few endpoints had 0% code coverage at the end of the tutorial. [Jacoco](https://www.eclemma.org/jacoco/) got a bit confused by some of the [Kotlin data classes](https://kotlinlang.org/docs/data-classes.html) and reported no coverage (even though they were _clearly_ used), but I got the rest of the coverage 100%.
- **Adding a code formatter** Everyone loves opinionated ways to format their code, right? This uses [`ktlint-gradle`](https://github.com/JLLeitschuh/ktlint-gradle) and is invoked from the command line via a `gradle ktlintFormat`
- **Adding SpotBugs** I've leveraged [SpotBugs](https://spotbugs.github.io/) many times over the years to find "easy bugs". In this case, it was less than useful--it highlighted a lot of problems in the bytecode of the [Kotlin data classes](https://kotlinlang.org/docs/data-classes.html) which I really couldn't do anything about.

Stuff I'd like to add:

- **Make it look nicer** It's just black and white and serif fonts right now. Boring 😴
- **Add thumbnails** The database in use is good old [H2](https://www.h2database.com/html/main.html) and I have no clue how _images_ would be stored / retrieved on there. Moving toward a "real" database like Mongo or Redis would be fun, too.
- **Deploy to cloud** One of the most difficult parts of software development is deploying. Even this tiny test project would have several challenges to overcome to get it available at a public URL.

## Electron Demo

<div class="small"><a href="https://github.com/robertjmarlow/electron-demo">🔗 on GitHub</a></div>

<div class="small sub-header-bottom"><b>Technologies Used</b>: <i>Electron NodeJS WebPack Babel React JavaScript</i></div>

Everything runs on [Electron](https://www.electronjs.org/) nowadays! From [Slack](https://slack.com/) to [Teams](https://www.microsoft.com/en-us/microsoft-teams/log-in) to [VSCode](https://code.visualstudio.com/)! You've got dozens of gigabytes of RAM--may as well use all of them in a ton of V8 child processes! 😅

Electron gets a lot of hate because [it's pretty much a glorified Chrome window](https://www.reddit.com/r/ProgrammerHumor/comments/v9ar7b/no_you_dont_understand_memeory_is_cheap/?utm_source=share&utm_medium=web2x&context=3), but it _is_ cross-platform and it _is_ pretty easy to write a frontend with the huge amount of JavaScript libraries out there. Sooooooo 🤷‍♂️ **Ship It**, I guess 🐿.

This app does some simple NodeJS stuff like reading the file system and getting some Operating System info--stuff that can't be done in a normal website for numerous security concerns. It's pretty basic.
