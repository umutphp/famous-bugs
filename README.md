# famous-bugs :bug: :honeybee: :ant: :beetle:

![Markdown Linter](https://github.com/umutphp/famous-bugs/workflows/.github/workflows/markdown-linter-action.yml/badge.svg?branch=master) [![Contributor Covenant](https://img.shields.io/badge/Contributor%20Covenant-v2.0%20adopted-ff69b4.svg)](./.github/CODE_OF_CONDUCT.md)

A curated list of problems and bugs that developers may find useful to know.

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table Of Contents

- [Introduction](#introduction)
- [Problems](#problems)
  - [Justin Bieber Problem of Instagram](#justin-bieber-problem-of-instagram)
  - [Year 2000 Problem](#year-2000-problem)
  - [NPM Leftpad Breakage](#npm-leftpad-breakage)
  - [Heathrow Terminal 5 Opening](#heathrow-terminal-5-opening)
- [Bugs](#bugs)
  - [The First Bug](#the-first-bug)
  - [Gangnam Style Broke YouTube](#gangnam-style-broke-youtube)
  - [The Explosion of the Ariane 5](#the-explosion-of-the-ariane-5)
  - [Metric System Mess Of NASA’s Mars Climate Orbiter](#metric-system-mess-of-nasas-mars-climate-orbiter)
  - [The Morris Worm](#the-morris-worm)
- [Contributing](#contributing)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

---

## Introduction

As software developers, we can simply define our work as fixing bugs and developing solutions to problems. This is a curated list of problems and bugs that developers may find useful to know. I hope it will become a community driven list to create a value.

## Problems

### Justin Bieber Problem of Instagram

> Bieber would post a photo, and so many Beliebers would "Like" it that Instagram's computers couldn't keep up.
>
> [Wired.com](https://www.wired.com/2015/11/how-instagram-solved-its-justin-bieber-problem/)

When Justin Bieber posts a photo, so many Beliebers would "Like" it that causes tremendous amount of notifications, queries and processes. This problem faced by the Instagram team is actually a very good example of [the thundering herd problem](https://en.wikipedia.org/wiki/Thundering_herd_problem). They did many improvements to avoid this problem happen again and explained in this [article](https://instagram-engineering.com/instagration-pt-2-scaling-our-infrastructure-to-multiple-data-centers-5745cbad7834).  

See also:

- [Thundering herd problem](https://www.wikiwand.com/en/Thundering_herd_problem)
- [How Instagram Solved Its Justin Bieber Problem](https://www.wired.com/2015/11/how-instagram-solved-its-justin-bieber-problem/)

### Year 2000 Problem

> ... making the year 2000 indistinguishable from 1900.
>

The Year 2000 problem (also known as the Y2K problem, the Millennium bug, Y2K bug, the Y2K glitch, or Y2K) refers to fails occured becuase of the formatting and storage of calendar data for dates beginning in the year 2000. Many failures were already documented all over the world. Here are some examples:

- On 1 January 1999, taxi meters in Singapore stopped working.
- On 1 January 2000, in Onagawa, Japan, an alarm sounded at a nuclear power plant at two minutes after midnight.
- On 1 March 2000, In the United States, the Coast Guard's message processing system was affected.
- Norway and Finland had to change their national identification number, to indicate correctly the century in which a person was born.

See also:

- [Year 2000 Problem at Wikipedia](https://en.wikipedia.org/wiki/Year_2000_problem)

### NPM Leftpad Breakage

> An 11 line npm package called left-pad with only 10 stars on github was unpublished...it broke some of the most important packages on all of npm.
>
> [Reddit](https://www.reddit.com/r/programming/comments/4bjss2/an_11_line_npm_package_called_leftpad_with_only/)

[Azer Koçulu](https://kodfabrik.com/) had been publishing a simple code he wrote to npm and It became very popular. Many projects has used his package as a dependency. On March 11, he received an email from a patent and trademark agent who works for Kik which was a messaging app. KiK was also the name of another package of him. They wanted him to rename the Kik package but he did not accept. Then the agency forced NPM to do so. After NPM's decision, Azer Koçulu had taken down all of his packages including left-pad. Then, many JavaScript programmers around the world started getting an error message "npm ERR! 404 'left-pad' is not in the npm registry".

See also:

- [I've Just Liberated My Modules
](https://kodfabrik.com/journal/i-ve-just-liberated-my-modules)
- [kik, left-pad, and npm](https://blog.npmjs.org/post/141577284765/kik-left-pad-and-npm)

### Heathrow Terminal 5 Opening

> ... simple real scenarios which for some reason weren’t tested.
>

Heathrow Terminal 5 was officially opened on 14 March 2008. On the day of opening, it did not operate as planned, so It forced British Airways to cancel 34 flights and suspend baggage check-in.

The newest luggage transporting system software couldn’t handle some simple real scenarios which for some reason weren’t tested. For example, a luggage was carried back manually because the owner forgot something in. In this case, the program went off and an item wasn’t recorded. The luggage processing was always disrupted by such kind of little details.

During the following ten days, around 42,000 items weren’t delivered to owners, and over 500 flights were canceled. Check-in to other flights became temporarily unavailable. 

See also;

- [Technical glitches hit T5 opening](http://news.bbc.co.uk/2/hi/uk_news/7314816.stm)
- [Heathrow Terminal 5](https://en.wikipedia.org/wiki/Heathrow_Terminal_5#Opening) at Wikipedia

## Bugs

### The First Bug

> First actual case of bug being found.
>
> [Grace Murray Hopper](https://en.wikipedia.org/wiki/Grace_Hopper)

On September 9, 1947, the [Mark II](https://en.wikipedia.org/wiki/Harvard_Mark_II) (at Harvard University) broke down. Engineers investigated and diagnosed the cause. A moth had entered the machine and had shorted out relay number 70 of Panel F. They attached the bug to the page with with a note "First actual case of bug found.". This is how the term "bug" was born.

![First Bug](./assets/images/first_bug.jpg)

The sheet is kept at the [National Museum of American History of the Smithsonian Institution](https://americanhistory.si.edu/collections/search/object/nmah_334663) in Washington.

See also:

- [Harvard Mark II](https://en.wikipedia.org/wiki/Harvard_Mark_II)
- [Grace Hopper](https://en.wikipedia.org/wiki/Grace_Hopper)

### Gangnam Style Broke YouTube

> We never thought a video would be watched in numbers greater than a 32-bit integer.
>
> YouTube

YouTube's counter was previously using  a 32-bit integer which means the maximum possible views it could count was 2,147,483,647. And "[Gangnam Style](https://www.youtube.com/watch?v=9bZkp7q19f0)" surpassed the 2-billion-view marker. YouTube has upgraded to a 64-bit integer so that the maximum views a video can receive is now 9,223,372,036,854,775,808.

### The Explosion of the Ariane 5

> ... a 64 bit floating point number ... was converted to a 16 bit signed integer.
>

On June 4, 1996 the Ariane 5 rocket launched by the European Space Agency exploded just forty seconds after its lift-off. The rocket was on its first voyage, after a decade of development costing $7 billion. The destroyed rocket and its cargo were valued at $500 million. The accident was a significant setback for Europe’s space program.

The horizontal velocity of the rocket with respect to the platform was larger than 32,767, the largest integer storeable in a 16 bit signed integer, and thus the conversion failed.

See also:

- [Report: Software Design Errors Caused Ariane 5 Explosion](https://apnews.com/article/1d85f290e31cad8532636fcb576f4788)

### Metric System Mess Of NASA’s Mars Climate Orbiter

The Mars Climate Orbiter was a robotic space probe launched by NASA on December 11, 1998 to study the Martian climate. The navigation team used the metric system in its calculations, while the team designing and building the spacecraft, provided crucial acceleration data in the English metric system. The acceleration readings measured in units of pound-seconds^2 for a force called newton-seconds^2. In a sense, the spacecraft was lost in translation.

See also:

- [Mars_Climate_Orbiter#Cause_of_failure](https://en.wikipedia.org/wiki/Mars_Climate_Orbiter#Cause_of_failure)

### The Morris Worm

> This was a design flaw ...
>

According to its creator, [Robert Tappan Morris](https://en.wikipedia.org/wiki/Robert_Tappan_Morris), It was not written to cause damage, but to highlight security flaws. It was programmed to exploit the known vulnerabilities in [sendmail](https://en.wikipedia.org/wiki/Sendmail), [finger](https://en.wikipedia.org/wiki/Finger_protocol), [rsh/rexec](https://en.wikipedia.org/wiki/Berkeley_r-commands) and weak passwords. While creating the worm, Robert programmed the worm to copy itself 14% of the time to avoid system administrators trying to defeat the worm by instructing the computer to report a false positive. This was a design flaw and created fork bombs and crashes in the affected computer.

The Morris Worm is accepted as one of the first computer worms distributed via the Internet and It was the first to gain significant mainstream media attention. A floppy disk containing the source code for the Morris Worm is held at the [Computer History Museum](https://computerhistory.org/).

See also:

- [Morris Worm](https://en.wikipedia.org/wiki/Morris_worm)
- [Robert Tappan Morris](https://en.wikipedia.org/wiki/Robert_Tappan_Morris)

## Contributing

Please do contribute! :pray:

[Raise an issue](https://github.com/umutphp/famous-bugs/issues/new) if you'd like to suggest an addition or change, or [Open a pull request](https://github.com/umutphp/famous-bugs/pulls) to add your own.

Please read the [Contributing Guidelines](./.github/contributing.md) and the [Code of Conduct](./.github/CODE_OF_CONDUCT.md) documents.
