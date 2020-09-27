# famous-bugs :bug: :honeybee: :ant: :beetle:

Remarkable bugs and problems fixed by developers are listed thay may inspire others.

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
## Table Of Contents

- [Introduction](#introduction)
- [Problems](#problems)
  - [Justin Bieber Problem of Instagram](#justin-bieber-problem-of-instagram)
- [Bugs](#bugs)
  - [Gangnam Style Broke YouTube](#gangnam-style-broke-youtube)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Introduction

As software developers, we can define our work as correcting mistakes and developing solutions to problems. This is a curated list of problems and bugs that developers may find useful to know.

## Problems

### Justin Bieber Problem of Instagram

> Bieber would post a photo, and so many Beliebers would "Like" it that Instagram's computers couldn't keep up.
>
> [Wired.com](https://www.wired.com/2015/11/how-instagram-solved-its-justin-bieber-problem/)

When Justin Bieber posts a photo, so many Beliebers would "Like" it that causes tremendous amount of notifications, queries and processes. This problem faced by the Instagram team is actually a very good example of [the thundering herd problem](https://en.wikipedia.org/wiki/Thundering_herd_problem). They did many improvements to avoid this problem happen again and explained in this [article](https://instagram-engineering.com/instagration-pt-2-scaling-our-infrastructure-to-multiple-data-centers-5745cbad7834).  

See also:

- [Thundering herd problem](https://www.wikiwand.com/en/Thundering_herd_problem)
- [How Instagram Solved Its Justin Bieber Problem](https://www.wired.com/2015/11/how-instagram-solved-its-justin-bieber-problem/)

## Bugs

### Gangnam Style Broke YouTube

> We never thought a video would be watched in numbers greater than a 32-bit integer.
> 
> YouTube

YouTube's counter was previously using  a 32-bit integer which means the maximum possible views it could count was 2,147,483,647. And "[Gangnam Style](https://www.youtube.com/watch?v=9bZkp7q19f0)" surpassed the 2-billion-view marker. YouTube has upgraded to a 64-bit integer so that the maximum views a video can receive is now 9,223,372,036,854,775,808.
