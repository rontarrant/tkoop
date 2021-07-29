---
title: "0001: Introduction to Tkooper"
layout: post
tag: general
topic: general
description: "The who, what, where, when, and how of this blog and a bunch of other things that might be good to know."
---

# 001: Introduction
## Why Me?

<!-- LEFT -->
<div class="inpage_diagram">
	<figure class="left">
		<img src="{{ site.baseurl }}/images/founder/chained_scientist.jpg" alt="The Founder" style="width: 200px; height: 253px;">
		<figcaption>
			(photo credit: Elise Amyot)
		</figcaption>
	</figure>
</div>

I’ve been a computer nerd since 1985 when my Dad introduced me to them and started my lifelong fascination with programming. My friend, Duane, and I spent the late 80’s and early 90’s in friendly competition as we drank in everything computer science threw our way. In the mid-to-late 90’s, along with some other friends, we worked for one of the first companies to develop online banking software which is where I also got my feet wet as a technical writer. Over the years since, I’ve written code in about two dozen languages, but didn’t embrace *Python* until recently.

One of my hobbies for the last 16 years has been writing blogs about GUI toolkits. This is my third. The first one, *PHP-GTK*, is now lost to the Ether. Perhaps this is for the best since *GTK 2* is the latest version supported in *PHP*, so it’s kind of gone stagnant. The second blog covered *GTK-D* and is still available at [GtkD Coding](https://gtkdcoding.com), although there haven’t been any new articles for a while.

## Why Python?

During the time I was writing the *GtkD* blog, a lot of *GTK 3.x* examples I found were written in Python which I then ported to *D* and *GtkD*. As a result, I learned *Python* by accident. When I moved on from *GtkD* and was looking for another toolkit to write about, my first thought was to tackle *PyGTK*. But then I discovered that *Python* had its own toolkit.

## Why Tkinter?

The short answer is: Because it comes with *Python*. But to be fair, I picked this toolkit because it’s easier to work with that any of the others I’ve ever researched. No other toolkit can boast a two-line script that not only opens a window, but throws in a couple of buttons... And one of them even works! Yes, it’s just a demo, but I was still impressed.

Further, the simplest *Python* script to open a window (ignoring OOP & Pythonic conventions) is a mere three lines. Now, that’s a lot of bang for the buck. Needless to say, I was intrigued. To top things off, a GUI is far less complicated to implement with Tkinter than most other toolkits.  

## Why Cross-platform?

In this blog, I’ll be covering *Python*/*tkinter* as used in cross-platform development. I use *Windows 10* knowing that it’s the worst end-user OS... except for all the others (to paraphrase Mary Albright’s remarks about democracy in *3rd Rock from the Sun*). But, if ever I decide to use *Linux* again, or go back to *FreeBSD*, or I strike it rich and buy a *Mac*, it’s nice to know that I can take my code with me without rewriting it. For me, that’s reason enough to do x-plat dev... and that’s the last time I’ll ever use that expression.

## Why OOP?

<!-- RIGHT -->
<div class="inpage_diagram">
	<figure class="right">
		<div class="mascot_lap_dissolve"></div>
		<figcaption class="centered">
			Tkooper Mascot — OOP Guy
		</figcaption>
	</figure>
</div>

I’ve been an advocate of object-oriented programming for the last twenty years and, frankly, it’s so ingrained now, it’s a struggle to write using any other paradigm. And when I do succeed, it just looks wrong and if I come back to that code a few months later, it takes me longer to figure out what the code's doing.

Yes, there will be some coupling—loose, tight, and otherwise—in these examples, but I’ll do my best to keep it to a minimum so this code can easily be adapted to your projects.

I found that a lot of *tkinter* examples online, if they use OOP at all, take it only so far, rarely going for maximum modularity. But, that’s what we strive for here.

OOP isn’t the perfect paradigm. In fact, you might even paraphrase Mary Albright again here, stating that it’s the worst programming paradigm except for all the others... unless we're talking about organizing code. IMO, you can't beat OOP for that.

I’m sure every non-OOP adherent has a great way to organize code, but with Python being object-oriented to its very core, if we push OOP as far as we reasonably can, our code will fall into a natural organizational structure that's easy to follow, easy to replicate, and anyone will be able to figure out exactly what’s going on after just a few minutes glancing over the code.

## Why These Demos?

The plan is to cover the entire *tkinter* toolkit with each demo stripped down to just what's needed to make things work. No extra stuff to muddy the water and each new idea presented by itself to maintain clarity. And as mentioned, this will all be in the OOP paradigm. There are two reasons for this:

- consistency of presentation, which will facilitate...
- ease of adaptation for your own purposes.

All demos should work equally well on *Windows 10*, *Mac* *OS*, *Linux*, *FreeBSD*—or any other OS you may be using—without the need to rewrite. We'll deal with OS differences where necessary with a little fancy footwork without losing sight of our cross-platform goals.

## A Word on Site Navigation

You may have noticed the links along the top of each page:

- *Home*,
- *About Tkooper, et al*,
- *Posts in Date Order*, and
- *Posts by Topic*.

They’re pretty self-explanatory, I suppose, but I’ll throw in these tidbits...

- If you’re new to the site and don’t wanna have to scroll to the bottom to start at the beginning, *Posts in Date Order* will give you all the posts in the order they were written so you can learn this stuff step by step.
- If you’ve come back to find a specific post or a specific example, *Posts by Topic* might prove handy.
- *Home*... well, nothing needs to be said about that, and
- *About* gives you a bit more background on me and why I started this whole thing.

But before we wrap things up, one more thing we need to talk about is...

## Why Those Fonts?

Cross-platform fonts can be a pain in the butt if you want a consistent look across platforms. In fact, it can be nigh on impossible, but one place where we can be consistent is with fonts. In *GTK-D*, I resorted to a bunch of `if-else` OS-dependent statements that handed off font equivalents based on which OS was in use. Here, though, I decided to work with a subset that can be made available to all platforms. We’ll talk more about this in the next post where we’ll also cover installation of *Python* and *tkinter*.

## Conclusion

And speaking of the next post, it’s time to wrap things up so I can get back to writing it. We’ll talk about installing *Python* and *tkinter* on the four most common operating systems as well as sorting out that font business.

Until then, remember that programming paradise is just a dream away. Good night.

<div class="blog-nav">
	<div style="float: right;">
		<a href="/2021/08/06/0002-python-font-installation.html">Next: Installing Python and Common Fonts</a>
	</div>
</div>