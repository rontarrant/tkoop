---
title: "0003: Windows: First Steps in Tkinter"
layout: post
tag: window
topic: window
description: "Dipping toes into the Tkinter waters."
---

## Before We Begin...

In case you're new to all this, to run any of these demos:

- type the code into your favourite editor (mine is *Notepad++*), or
- in the case of longer files (or if you just don't wanna do all that typing) download the file by following the link provided below each screen-shot,
- open a terminal, *Command Prompt*, shell, or *PowerShell*,
- navigate to the directory/folder where you saved/downloaded the code file, and
- run it using one of the following:
	- `py <script>.py`
	- `python <script>.py`
	- `python3 <script>.py`

Substituting the actual name of the script file where it says `<script>`, naturally.

BTW, that's how I'll indicate that you need to substitute file names or whatever. It's archaic, but clear. 

## About Them Windows We Spoke of...

Since a window is needed as a place to put widgets—you could say they're foundational to the whole GUI thing—it seems like a great place to start...

As I mentioned in an earlier post, getting a window open using *tkinter* is dead simple and that’s where we’re going to start, with the two-line *tkinter* demo. Really, it’s more of a built-in test, but no matter. You’ll see it in a bit.

Next, we’ll look at a very simple OOP demo which is far more practical because it can act as the basis for an actual application. Third, we’ll look at how to use the OOP demo from a separate script as a way to introduce code modularity, something you'll find extremely handy as your  confidence builds and your applications get larger.

Ready? Let’s get at it.

## The Simplest tkinter Application

<!-- z, y -->
<!-- FIRST occurrence of application and terminal screen shots on a single page -->
<div class="screenshot_two_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- LEFT SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="imgz" src="/images/screenshots/001_window/window_000_test.png" alt="Current example output">		<!-- img# -->
			
			<!-- Modal for screenshot -->
			<div id="modalz" class="modal">																	<!-- modal# -->
				<span class="closez">&times;</span>															<!-- close# -->
				<img class="modal-content" id="imgzz">															<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modalz");														// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("imgz");															// img#
			var modalImg = document.getElementById("imgzz");													// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("closez")[0];											// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>
			<figcaption>
			Current example output
			</figcaption>
		</figure>
	</div>
<!-- RIGHT SCREENSHOT -->
	<div class="gridterm">
		<figure class="right">
			<img id="imgy" src="/images/screenshots/no_output/no_output_term_window.png" alt="Terminal image">		<!-- img#, filename -->

			<!-- Modal for terminal shot -->
			<div id="modaly" class="modal">																				<!-- modal# -->
				<span class="closey">&times;</span>																		<!-- close# -->
				<img class="modal-content" id="imgyy">																		<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modaly");																	// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("imgy");																		// img#
			var modalImg = document.getElementById("imgyy");																// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("closey")[0];														// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>

			<figcaption>
				Current example terminal output (click for enlarged view)
			</figcaption>
		</figure>
	</div>

	<div class="gridfooter">																								<!-- ------------- filename (below) --------- -->
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_000_test.py" target="_blank">
		DOWNLOAD the code file for this example.
		</a>.
	</div>
</div>
<BR>
<!-- end of snippet for FIRST (1st) occurrence of application and terminal screen shots on a single page -->



Okay... not really an application, just a test. But it’s only two lines and—considering what it does—I find that pretty impressive for a GUI toolkit. Here it is:

```python
import tkinter
tkinter._test()
```

This is the same as what we did near the end of <a href="/2021/07/16/0002-python-font-installation.html" target="_blank">Tkooper Post #002 — Python and Font Installation</a>. The only difference is that here we’re going to run it as a script instead of from the command line.

So, if you type those lines into an editor and save it as `000_window_test.py` — or whatever— you’ll have made your first step into *tkinter*-land.

Run it from *Git Bash*, a *Bash* shell, *Terminal*, a *DOS* prompt... whatever’s your poison and (if you did the alias trick I mentioned in that previous post, you can run it by typing:

	py 000_window_test.py

The results will be the same as we got when we used the *Python* interpreter directly like this:

	py -m tkinter

### Breakdown

There isn’t much to breakdown, but there are two tidbits of information to take away from this:

- we can’t use *tkinter* without importing it, and
- it’s now obvious that `py -m` on the command line is the same as an `import` statement in a script. 

Both allow us to use an external *Python* module.

## A Minimal Window Demo

<!-- x, w -->
<!-- SECOND occurrence of application and terminal screen shots on a single page -->
<div class="screenshot_two_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- LEFT SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="imgx" src="/images/screenshots/001_window/window_001_minimal.png" alt="Current example output">		<!-- img# -->
			
			<!-- Modal for screenshot -->
			<div id="modalx" class="modal">																	<!-- modal# -->
				<span class="closex">&times;</span>															<!-- close# -->
				<img class="modal-content" id="imgxx">															<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modalx");														// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("imgx");															// img#
			var modalImg = document.getElementById("imgxx");													// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("closex")[0];											// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>
			<figcaption>
			Current example output
			</figcaption>
		</figure>
	</div>
<!-- RIGHT SCREENSHOT -->
	<div class="gridterm">
		<figure class="right">
			<img id="imgw" src="/images/screenshots/001_window/window_001_minimal_term.png" alt="Terminal image">		<!-- img#, filename -->

			<!-- Modal for terminal shot -->
			<div id="modalw" class="modal">																				<!-- modal# -->
				<span class="closew">&times;</span>																		<!-- close# -->
				<img class="modal-content" id="imgww">																		<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modalw");																	// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("imgw");																		// img#
			var modalImg = document.getElementById("imgww");																// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("closew")[0];														// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>

			<figcaption>
				Current example terminal output (click for enlarged view)
			</figcaption>
		</figure>
	</div>

	<div class="gridfooter">																								<!-- ------------- filename (below) --------- -->
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_001_minimal.py" target="_blank">
		DOWNLOAD the code file for this example.
		</a>.
	</div>
</div>
<BR>
<!-- end of snippet for SECOND (2ND) occurrence of application and terminal screen shots on a single page -->


It's possible to write a three-line script that opens a window, but it’s rather *unpythonic*, so let’s go with something a little more elaborate. Other than the quick test demo above, this is just about the least amount of code you can write to get an actual *tkinter* application while maintaining good coding practices. I did add one extra line (the `print()` statement) which we’ll discuss. Here’s the code:

```python
import tkinter

def main():
	print(f“__name__: = {__name__}”)
	window = tkinter.Tk()
	window.mainloop()
	
if __name__ == "__main__":
	main()
```

### Breakdown

Again, we start by importing the *tkinter* library.

Skipping over that `print()` statement, the rest of `main()` declares and opens a window. I’ll get back to the `print()` statement in a second.

The window declaration does hide a bit of what's going on, so here's the dope...

- `Tk()` is the window class which is part of the `tkinter` module,
- `tkinter.Tk()` is shorthand for calling `tkinter.Tk().__init__()` and that creates the window object, and
- the `window` then opens automatically when `window.mainloop()` starts.

One other thing to note here. The way we imported tkinter means that every time we make a call to the tkinter library, we'll have to prefix the call with `tkinter.` to avoid a `name <widget> not defined` error. We'll change the way we import the library in later demos so we won't have to type that prefix over and over.

Now let’s talk about the `print()` statement... which will make more sense if we do so in conjunction with the `if` statement at the bottom of the script. So, we’ll start there...

The `if` statement checks the script’s namespace. *Python* always gives an executing script the namespace `__main__`. That’s why this `if` statement works. The script is executed, *Python* finds the namespace is `__main__` and so executes `main()`.

And the `print()` statement reflects this. When the script is run and the window opens, the terminal displays:

```python
__name__: __main__
```

But, that's not the end of the story. Let’s look at what happens when *Python* imports this same script as a module...

## Importing The Previous Demo

<!-- u, v -->
<!-- THIRD occurrence of application and terminal screen shots on a single page -->
<div class="screenshot_two_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- LEFT SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="imgu" src="/images/screenshots/001_window/window_002_start_external.png" alt="Current example output">		<!-- img# -->
			
			<!-- Modal for screenshot -->
			<div id="modalu" class="modal">																	<!-- modal# -->
				<span class="closeu">&times;</span>															<!-- close# -->
				<img class="modal-content" id="imguu">															<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modalu");														// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("imgu");															// img#
			var modalImg = document.getElementById("imguu");													// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("closeu")[0];											// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>
			<figcaption>
			Current example output
			</figcaption>
		</figure>
	</div>
<!-- RIGHT SCREENSHOT -->
	<div class="gridterm">
		<figure class="right">
			<img id="imgv" src="/images/screenshots/001_window/window_002_start_external_term.png" alt="Terminal image">		<!-- img#, filename -->

			<!-- Modal for terminal shot -->
			<div id="modalv" class="modal">																				<!-- modal# -->
				<span class="closev">&times;</span>																		<!-- close# -->
				<img class="modal-content" id="imgvv">																		<!-- img## -->
				<div id="caption"></div>
			</div>
			
			<script>
			// Get the modal
			var modal = document.getElementById("modalv");																	// modal#
			
			// Get the image and insert it inside the modal - use its "alt" text as a caption
			var img = document.getElementById("imgv");																		// img#
			var modalImg = document.getElementById("imgvv");																// img##
			var captionText = document.getElementById("caption");

			img.onclick = function()
			{
			  modal.style.display = "block";
			  modalImg.src = this.src;
			  captionText.innerHTML = this.alt;
			}
			
			// Get the <span> element that closes the modal
			var span = document.getElementsByClassName("closev")[0];														// close#
			
			// When the user clicks on <span> (x), close the modal
			span.onclick = function()
			{ 
				modal.style.display = "none";
			}
			</script>

			<figcaption>
				Current example terminal output (click for enlarged view)
			</figcaption>
		</figure>
	</div>

	<div class="gridfooter">																								<!-- ------------- filename (below) --------- -->
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_002_start_external.py" target="_blank">
		DOWNLOAD the code file for this example.
		</a>.
	</div>
</div>
<BR>
<!-- end of snippet for THIRD (3RD) occurrence of application and terminal screen shots on a single page -->


The next script looks like this:

```python
import window_001_minimal

def main():
	window_001_minimal.main()

if __name__ == "__main__":
	main()
```

The `import` statement brings in our previous script by name—minus the `.py` suffix. It doesn’t mention the `tkinter` module because that's done in `window_001_minimal.py`. Also, `main()` doesn’t declare and open a window. For that too, we rely on the previous script. Let's save this script as `window_002_start_external.py`.

What’s really neat about all this is that when we execute this demo, we find that the namespace given to the previous script—as evidenced by the `print()` statement—has changed. It's now the same as the script’s file name... minus the `.py` extension. In other words, when we run `window_002_start_external.py` the terminal will now display:

```python
__name__: window_001_minimal
```

And notice, too, that we’re still testing for the namespace `__main__` in `window_002_start_external.py`. If we were to copy the `print()` statement from `window_001_minimal.py` and plunk it down anywhere in this script, it would print out:

```python
__name: __main__
```

Thus proving that it's always the namespace for the script being executed.

## Script Namespace Awareness

Adding those two lines at the end of every script is a good habit to get into. It’ll help *Python* keep the scope straight, help us maintain the modularity expected by the OOP paradigm, and it means you can reuse any script with a minimum of fussing about. We can test for the `__main__` namespace in every script and never have to worry about collisions because *Python* makes sure the namespace for each imported script gets a unique name while the executing script always gets named `__main__`.

## Conclusion

Next time, we’ll touch on frames and discover that the statement made at the top of this post about windows being foundational to all things GUI may not be true. Until then, keep your campfires burning and, as they say in some parts, don’t let the COVID get you.

<div class="blog-nav">
	<div style="float: left;">
		<a href="/2021/08/06/0002-python-font-installation.html">Previous: Installing Python and Common Fonts</a>
	</div>
	<div style="float: right;">
		<a href="/2021/08/13/0004-just-ooping-along.html">Next: Just OOPing Along</a>
	</div>
</div>
