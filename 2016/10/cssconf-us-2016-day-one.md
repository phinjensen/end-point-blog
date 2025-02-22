---
author: Greg Davidson
title: CSSConf US 2016 — Day One
github_issue_number: 1259
tags:
- accessibility
- browsers
- conference
- css
- html
- javascript
- testing
date: 2016-10-07
---

<img alt="IMG 6042" border="0" height="450" src="/blog/2016/10/cssconf-us-2016-day-one/image-0.jpeg" style="display:block; margin-left:auto; margin-right:auto;" title="IMG_6042.JPG" width="600"/>  Boston Common

I attended CSSConf US 2016 last week in Boston, MA. Having been to the [2013](/blog/2013/06/css-conf-2013-when-bootstrap-attacks) and 2014 ([part one](/blog/2014/05/cssconf-us-2014-part-one), [part two](/blog/2014/06/css-conf-us-2014-part-two)) events in Florida then missing it in NYC last year, I was looking forward to seeing what it would be like in a new location. It was fun to see some familiar faces including [Eiríkur](https://twitter.com/eirikurn) (congrats on organizing a very successful [JSConf Iceland](https://2016.jsconf.is/) conference earlier this year!) and to meet many new folks in the CSS community. [Claudina Sarahe](http://itsmisscs.me/) was our MC for two days of talks and she did a great job. After each talk she took a few minutes to interview the speaker—​asking them questions from the audience and some of her own. The chats were candid and interesting on their own and gave the next speaker time to set up.

Below are my notes and some observations on the talks from Day One. Be sure to check out the [videos, slides and transcripts](https://2016.cssconf.com/#videos) at the CSSConf site. Many of the videos are there now and they are adding more as they become available.

### Sarah Drasner — Creativity in Programming for Fun and Profit

Sarah started off the day with an inspiring keynote about creativity. She explained how writing code is a creative endeavor by showing us several drastically different solutions to the classic FizzBuzz problem in computer science. She shared some stats and survey results which documented excellent, tangible results companies saw when they invested in R&D and fostering creativity. Sarah demoed some really cool creative projects she had built—​many of them just for fun. She encouraged us to work on creative projects on the side to enter into [flow](https://en.wikipedia.org/wiki/Flow_(psychology)) while designing, coding and building things. Time devoted to purely creative and fun projects can makes less interesting day-to-day tasks more bearable. It was amazing to see some of the animation work she’s done and her passion for art and programming was palpable throughout the talk.

### Brian Jordan — No Bugs in Sight: Continuous Visual Tesing at Code.org

Brian works for [code.org](https://code.org/) which is the organization behind the Hour of Code and other initiatives promoting computer science education in schools. His work on apps that teach kids to code is used on a vast variety of hardware (tablets, old underpowered school computers etc.). Testing became a challenge early for them so Brian began to incorporate testing with [Selenium](http://www.seleniumhq.org/) into their development workflow. They use [Cucumber](https://cucumber.io/) to write their tests. They use [Sauce Labs](https://saucelabs.com/) to run the tests and [circleCI](https://circleci.com/) to integrate it with their source code control system. When code is committed, the tests are run which ensures broken code does not get merged in. They also use [applitools eyes](https://applitools.com/) for visual diffing which looked very interesting. They keep a wiki of the larger and more interesting issues that it catches to help everyone remember them (and sometimes recall why they still need to keep a particular test). Brian showed us several screenshots of visual problems caught by their system including one that was a single pixel showing up in a strange (unwanted) location on the screen.

### Jessica Lord — Nativize is the new Normalize

Jessica works at GitHub on the [Electron project](http://electron.atom.io/). Her talk was about Electron and how you can use it to build cross-platform (Windows/Linux/Mac) desktop apps using web technologies. Electron is used to power [Atom](https://atom.io/), Slack and [many other interesting apps](http://electron.atom.io/apps/). It uses [V8](https://developers.google.com/v8/) as its JavaScript runtime which allows you to use Node.js in your apps. Chromium is used for the all the DOM and rendering bits. She showed off the Electron example app and talked about some tips and tricks to building apps with Electron. Jessica stressed that you have to think about apps differently than web sites. You want your app to feel like an app not a website. She pointed out several good resources for learning more about it. Electron can also be used to build menubar apps for OS X.

### Jen Kramer — CSS4 Grid: True Layout Finally Arrives

[Jen](http://www.jenkramer.org/) is a professor at [Harvard](https://developers.google.com/v8/) teaching web development. She talked about CSS grid and how it will make laying out sites much better than the current hacks techniques we have been using up to this point (tables, floats, flexbox). She explained how [flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) was designed to only work in a single dimension (grids need to work in two for both rows & columns) and showed some example layouts built with CSS grid. Jen’s examples showed how many CSS design challenges (e.g.: equal height columns) are easily solved with grid. The only thing holding it back is browser support. Today it’s available in Chrome and Firefox behind a configuration flag. Jen was really funny and engaging and drew everyone in with her presentation skills and passion for web development in general (grid too!).

### Pete Hunt — Component-Based Style Reuse

Pete talked about [React](https://facebook.github.io/react/) and how it can be used to create components (e.g.: a piece of UI that can be re-used in different contexts). He shared how [OOCSS](https://github.com/stubbornella/oocss/wiki) was a foundational concept and inspiration to him and walked through the process of building a React component that implemented an OOCSS “media block” component. Having previously worked at FaceBook, Pete discussed the issues that arise when developing many UI components at scale—​especially CSS class conflicts and the resulting style pollution. Pete used [jsxstyle](https://github.com/smyte/jsxstyle) (developed by his current team at Smyte) in his React component to keep the styles scoped to the component and avoid using descendent selectors. It was very interesting talk and I recommend watching the [video of Pete’s talk](https://2016.cssconf.com/#videos) to get the full effect.

### Keith J. Grant — Stop Thinking in Pixels

[Keith](http://keithjgrant.com/) works for the [company behind the NYSE website](https://theice.com/). He thoroughly explained how to effectively use em and rem units for font-size and other properties and how he recommends avoiding using pixels for font sizes altogether. Keith showed many examples using rem to set the font size for a container element and then use ems for all of its children. This had the benefit of flexibility and made is possible to adjust the sizes of all of the child elements by simply changing the size on the parent/container. He covered several formulas which can be used to determine the em values you will need for approximate pixel sizes. He shared [type-scale.com](http://type-scale.com/) as a web app that can help with these calculations. Once you understand the formulas, you can add mixins in Sass to perform the calculations for you. Near the end of his talk Keith showed us an example using rems for the parent, ems for the child elements and then combining calc() with viewport units (vh, vw) to smoothly scale the size of a component as the viewport changes. This was really neat to see and avoided the clunky switch between sizes that happens when the viewport changes between media queries. With the technique Keith demonstrated, the scaling was completely fluid—​very impressive. Keith wrapped up by explaining that these techniques require a little work up front and often educating other developers on the team but the benefits are immediate.

### Will Boyd — Silky Smooth Animation with CSS

Will talked about the deep dive he took into how browsers handle rendering and animation. He demoed how we can look into the process for our own performance debugging with tools like Chrome DevTools. To illustrate some of the performance wins Will had discovered in his own projects, he loaded up an animation he’d built for the talk and compared the performance before and after he used CSS properties that could be handled by the GPU. The performance improvement using transform, filter and opacity (all hardware-accelerated and rendered by the GPU) was drastic and impressive.

### Lea Verou — CSS Variables var(--subtitle);

Lea’s talk was about CSS variables (aka custom properties). I admit to being surprised when I looked it up recently and found that they were already [quite widely supported](http://caniuse.com/#feat=css-variables). The syntax looks little odd at first but it made sense when Lea explained it was intentional that they look different than preprocessor variables. I found it interesting that CSS variables are expected to be used alongside preprocessor variables rather than replacing them. Lea explained how they work, how they can be accessed by JavaScript and demonstrated several things CSS variables can do that preprocessor variables can not! Make sure to check out the [video of her talk](https://2016.cssconf.com/#videos) when you get the chance.
