---
title: "0002: Installing Python and Common Fonts"
layout: post
tag: general
topic: general
description: "How to install Python 3.x on the most-used operating systems and creating a baseline set of fonts."
---

## Intro — What We're Doing

Here's the list:

- install Python/Tkinter,
- check the install to make sure everything's working, and
- (if you're using Linux or one of the BSD's) install fonts common to other OS's.

## Installing Python/Tkinter

Let’s get this out of the way right up front... for all operating systems, I recommend installing the 64-bit version of *Python*. But, if for any reason you can’t, the 32-bit version will also do.

For those operating systems that use them (*Windows* and *MacOS* mostly), installers can be <a href="https://www.python.org/downloads/" target="_blank">downloaded from here</a>.

Now, on to specifics.

### Windows

<!-- 1a -->
<!-- FIRST occurrence of application screen shots on a single page -->
<div class="screenshot_one_grid_container">
	<div class="gridheader">
		
	</div>
<!-- SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="img1a" src="/images/diagrams/post_0002/win_installer.png" alt="Current example output">		<!-- img# -->
			
			<!-- Modal for screenshot -->
			<div id="modal1a" class="modal">																	<!-- modal# -->
				<span class="close1a">&times;</span>															<!-- close# -->
				<img class="modal-content" id="img1a1a">															<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modal1a");														// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("img1a");															// img#
			var modalImg = document.getElementById("img1a1a");													// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("close1a")[0];											// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>
			<figcaption>
			Python Windows Installer
			</figcaption>
		</figure>
	</div>
</div>
<!-- end of snippet for FIRST (1st) occurrence of application screen shot on a single page -->

- start the installer,
- when the dialog appears, make sure to check the box at the bottom to:
	- *Add Python 3.x to PATH*,
- from there, just follow the prompts.

### GhostBSD/FreeBSD

Open an elevated terminal and locate the latest *Python* version

*Nit: If you don't know what an elevated terminal is, you have two choices: 1) go hit the books and find out, or 2) you might wanna rethink your choice of OS. :)*

	pkg search python

Install it:

	pkg install python-xxx

Locate the latest version of *tkinter*:

	pkg search tkinter

In this next step (below) the command shown is for the version of *Python* and *tkinter* I found while testing these installation procedures on my computer. But if enough time has passed since the publishing of this post, you may have a more up-to-date version to deal with. In that case, the previous command (above) will tell you which version that is. Simply do the substitution before you install it with:

	pkg install py39-tkinter-3.9.1_6

### Linux

Chances are, you’re using a *Debian/Ubuntu*-based *Linux* release. If so, you’re likely familiar with `apt`. If you’re using *SUSE Linux* or another distro that doesn’t use `apt`, you may have to build *Python* from source and that’s beyond the scope of this blog. However, in a case like that, you likely don’t need me to explain how to install *Python*, anyway. If you do, though, I refer you to this page on <a href="https://realpython.com/installing-python/#how-to-install-on-opensuse" target="_blank">Real Python</a> and we’ll talk again in a few hours once you’re finished.

Getting back to the subject at hand...

To install using the `apt` package manager...

- hook up the repository:
	- `sudo add-apt-repository ppa:deadsnakes/ppa`
- make sure everything’s up to date:
	- `sudo apt-get update`
- find the latest Python (without venturing out onto the bleeding edge):
	 - `sudo apt-cache search python`
- install it (and, of course, substitute the actual minor version for the `x`):
	- `sudo apt-get install python3.x python3-pip`

### MacOS

Just download and install. That’s it.

Well, one other thing you'll likely want to do is add *Python* to the system path. This means you can simply type `python <script>.py` to launch a script instead of typing the entire installation path name. Here's a step-by-step procedure:

- open a *Terminal*,
- type this command:
	- `sudo nano /etc/paths`
	- type your password when asked,
- (contents of the `PATH` variable will appear), so
- at the end of this list, type the full path of the *Python* install directory,
- `Ctrl + X` to quit, and
- `Y` to save the changes.

## Configure an Alias

**(Optional, but Recommended)**

If you’re using *Windows*, you can run *Python* by typing `py` or you can execute a script with `py <script>.py`, but there’s no reason why you can’t have the same convenience no matter which OS you’re using.

### Linux or BSD

Create or edit `.bashrc` in your home directory and add this line:

	alias py=’python3.9’

And, again, if you're using a later version of *Python*, substitute the proper version number. Restart the shell for this to take effect.

### MacOS

To set up an alias:
- launch *Terminal*
- go to your home directory:
	`cd`
- create or edit the shell profile:
	`nano .bash_profile`
- add the alias:
	`alias py=’python3’`
- refresh the shell so the alias takes effect:
	`source ~/.bash_profile`

## Final Check

No matter which OS you’re using, if you followed the above recommendations, you can now check that *Python* is working by opening a shell/terminal/*Terminal*/*Command Prompt* and typing:

	py --version

And to make sure *tkinter* is working properly:

	py -m tkinter

This should open a small *tkinter* window that shows which version of *tkinter* you have. It should be 8.6 or later to follow the demos on this blog.

<!-- 2b -->
<!-- SECOND occurrence of application screen shots on a single page -->
<div class="screenshot_one_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="img2b" src="/images/screenshots/001_window/window_000_test.png" alt="Current example output">		<!-- img# -->
			
			<!-- Modal for screenshot -->
			<div id="modal2b" class="modal">																	<!-- modal# -->
				<span class="close2b">&times;</span>															<!-- close# -->
				<img class="modal-content" id="img2b2b">															<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modal2b");														// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("img2b");															// img#
			var modalImg = document.getElementById("img2b2b");													// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("close2b")[0];											// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>
			<figcaption>
			Results of 'py -m tkinter'
			</figcaption>
		</figure>
	</div>
</div>
<BR>
<!-- end of snippet for SECOND (2nd) occurrence of application screen shot on a single page -->


If you’re using a *UNIX*-like OS, there’s a slim chance that *tkinter* isn’t installed at this point or isn’t up to date. If that’s the case, type:

	pip install tk

Then rerun the `py -m tkinter` command to make sure you’re up-to-date.

Just one more thing (if you’re using *Linux* or a *BSD*) and then we’re ready to roll...

## Install Core Fonts for the Web

**(Optional, but Highly Recommended)**

Let’s establish a baseline for fonts so we're all on the same page.

We don’t need more than a few different fonts for the types of demos that’ll be covered here, but in the interests of flexibility and good design, we’ll want at least the following:

- a couple of serif fonts,
- a couple sans-serif,
- a fixed-width (monospace) font or two, and
- something playful for when we want a sense of whimsy.

*Core Fonts for the Web* gives us:

- *Andalé Mono* (fixed width),
- *Arial* (sans-serif),
- *Arial Black* (sans-serif),
- *Comic Sans MS* (fanciful),
- *Courier New* (fixed width,
- *Georgia* (serif),
- *Impact* (sans-serif),
- *Times New Roman* (serif),
- *Trebuchet MS* (sans-serif),
- *Verdana* (sans-serif), and
- *Webdings* (weird stuff).

These give us a couple of choices for each of the font styles listed above.

If you’re working on *Windows* or *MacOS*, these fonts (with the exception of *Andalé Mono*) are installed along with the OS, but they’re also free to use with *Linux* and the *BSD*’s.

### MS Webfonts on GhostBSD/FreeBSD

Use an elevated terminal to install and configure them.

Install:

	pkg search webfonts
	pkg install webfonts-<VERSION>
	touch /usr/local/etc/X11/fontpath.d/fontpath.conf 

To configure, just edit `/usr/local/etc/X11/fontpath.d/fontpath.conf` and add these lines:

	Section "Files"
		ModulePath "/usr/local/lib/xorg/modules"
		FontPath "/usr/local/share/fonts/webfonts"
	EndSection

### MS Webfonts on Linux (Apt)

Make sure you’re using an appropriate repository:

	sudo add-apt-repository multiverse

install the fonts:

	sudo apt update
	sudo apt install ttf-mscorefonts-installer

The installer will ask you to agree to the license and—since you won’t be signing away your firstborn—you might as well.

Once that’s done, update your font cache:

	sudo fc-cache -f -v

## Conclusion

And now that that’s all sorted out, it’s way past my bedtime, so I’ll sign off. Next time we’ll start by looking into some windows... through some windows...? Out some windows...?

Whatever. I’ll see you then.

<div class="blog-nav">
	<div style="float: left;">
		<a href="/2021/08/03/0001-blog-introduction.html">Previous: Introduction to the Tkooper Blog</a>
	</div>
	<div style="float: right;">
		<a href="/2021/08/17/0003-windows-first-steps.html">Next: Windows - First Steps</a>
	</div>
</div>
