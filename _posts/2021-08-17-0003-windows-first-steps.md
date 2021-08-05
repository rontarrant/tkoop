---
title: "0003: Windows: First Steps in Tkinter"
layout: post
tag: window
topic: window
description: "Dipping toes into the Tkinter waters."
---

## Before We Begin...

To run these demos:

- type the code into an editor (I use *Notepad++*), or
- download the script using the link below each screen-shot,
- open a terminal (or *Terminal*, *Command Prompt*, *Bash* shell, or *PowerShell* — from now on, I'll just say 'terminal'),
- navigate to where you saved the script, and
- run it like so:
	- `py <script>.py`
- or so:
	- `python <script>.py`
- or so:
	- `python3 <script>.py`

Substitute the script name where it says `<script>`, naturally.

I'll always indicate substitutions with angle brackets. It's archaic, but clear. 

*Nit: Above, I said you can download the files, but repetitive typing of code examples is the best way to absorb this stuff.*

## Intro — What We're Doing

We'll be looking at:

- a script version of the test we ran last time,
- a simple OOP demo on which we can base an application, and
- how to run the OOP demo from a separate script.

## The Simplest tkinter Application

<!-- 0, 1, 2 -->
<!-- FIRST occurrence of application, terminal, and source code screenshots on a single page -->
<div>
	<!-- GRID HEADER -->
	<div class="grid_header">
		<p class="screenshot_grid_header_blurb">Results of This Example:</p>
	</div>
	<div class="columns">
		<!-- COLUMN 1 -->
		<div>
			<figure>
				<img id="img0" src="/images/screenshots/001_window/window_000_test.png" alt="Current example output">		<!-- img# -->
				
				<!-- Modal for screenshot -->
				<div id="modal0" class="modal">																<!-- modal# -->
					<span class="close0">&times;</span>														<!-- close# -->
					<img class="modal-content" id="img00">														<!-- img## -->
					<div id="caption"></div>
				</div>
				
				<script>
				// Get the modal
				var modal = document.getElementById("modal0");													// modal#
				
				// Get the image and insert it inside the modal - use its "alt" text as a caption
				var img = document.getElementById("img0");														// img#
				var modalImg = document.getElementById("img00");												// img##
				var captionText = document.getElementById("caption");
	
				img.onclick = function()
				{
				  modal.style.display = "block";
				  modalImg.src = this.src;
				  captionText.innerHTML = this.alt;
				}
				
				// Get the <span> element that closes the modal
				var span = document.getElementsByClassName("close0")[0];										// close#
				
				// When the user clicks on <span> (x), close the modal
				span.onclick = function()
				{ 
					modal.style.display = "none";
				}
				</script>
				<figcaption>
					Current example output<BR>(click to enlarge)
				</figcaption>
			</figure>
		</div>
		<!-- END COLUMN 1 -->
	</div>
	 <!-- GRID FOOTER -->
	<div id="downloadbox" class="grid_footer">
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_000_test.py" target="_blank">DOWNLOAD the code file for this example.</a>
	</div>
</div>
<BR>
<!-- end of snippet for FIRST (1st) occurrence of application, terminal and source code screenshots on a single page -->

As they say on TV, this is just a test. But it’s only two lines and—considering what it does—it's pretty impressive. Here it is:

```python
import tkinter
tkinter._test()
```

You'll recognize the results of this script from <a href="/2021/07/16/0002-python-font-installation.html" target="_blank">Post #002 — Python and Font Installation</a>.

You can type it, save it as `000_window_test.py`, and take your a step further into *tkinter*-land when you run it from a terminal. And if you did the alias trick I mentioned, you can run it by typing:

	py 000_window_test.py

The results will be the same as we got when we used the *Python* interpreter directly like this:

	py -m tkinter

### Breakdown

There isn’t much to breakdown, but there are two tidbits of information to take away from this:

- we can’t use *tkinter* without importing it, and
- it’s now obvious that `py -m` on the command line is the same as an `import` statement in a script. The difference is that, on the command line, importing tkinter like this automatically runs the test. In our script, we have to call it explicitly.

Both allow us to use a *Python* module.

## A Minimal Window Demo

<!-- 3, 4, 5 -->
<!-- SECOND occurrence of application, terminal, and source code screenshots on a single page -->
<div>
	<!-- GRID HEADER -->
	<div class="grid_header">
		<p class="screenshot_grid_header_blurb">Results of This Example:</p>
	</div>
	<div class="columns">
		<!-- COLUMN 1 -->
		<div>
			<figure>
				<img id="img3" src="/images/screenshots/001_window/window_001_minimal.png" alt="Current example output">		<!-- img# -->
				
				<!-- Modal for screenshot -->
				<div id="modal3" class="modal">																<!-- modal# -->
					<span class="close3">&times;</span>														<!-- close# -->
					<img class="modal-content" id="img33">														<!-- img## -->
					<div id="caption"></div>
				</div>
				
				<script>
				// Get the modal
				var modal = document.getElementById("modal3");													// modal#
				
				// Get the image and insert it inside the modal - use its "alt" text as a caption
				var img = document.getElementById("img3");														// img#
				var modalImg = document.getElementById("img33");												// img##
				var captionText = document.getElementById("caption");
	
				img.onclick = function()
				{
				  modal.style.display = "block";
				  modalImg.src = this.src;
				  captionText.innerHTML = this.alt;
				}
				
				// Get the <span> element that closes the modal
				var span = document.getElementsByClassName("close3")[0];										// close#
				
				// When the user clicks on <span> (x), close the modal
				span.onclick = function()
				{ 
					modal.style.display = "none";
				}
				</script>
				<figcaption>
					Current example output<BR>(click to enlarge)
				</figcaption>
			</figure>
		</div>
		<!-- END COLUMN 1 -->
		
		<!-- COLUMN 2 -->
		<div>
			<figure>
				<img id="img4" src="/images/screenshots/001_window/window_001_minimal_term.png" alt="Current example terminal output"> 		<!-- img#, filename -->
	
				<!-- Modal for terminal shot -->
				<div id="modal4" class="modal">																			<!-- modal# -->
					<span class="close4">&times;</span>																	<!-- close# -->
					<img class="modal-content" id="img44">																	<!-- img## -->
					<div id="caption"></div>
				</div>
				
				<script>
				// Get the modal
				var modal = document.getElementById("modal4");																// modal#
				
				// Get the image and insert it inside the modal - use its "alt" text as a caption
				var img = document.getElementById("img4");																	// img#
				var modalImg = document.getElementById("img44");															// img##
				var captionText = document.getElementById("caption");
	
				img.onclick = function()
				{
				  modal.style.display = "block";
				  modalImg.src = this.src;
				  captionText.innerHTML = this.alt;
				}
				
				// Get the <span> element that closes the modal
				var span = document.getElementsByClassName("close4")[0];													// close#
				
				// When the user clicks on <span> (x), close the modal
				span.onclick = function()
				{ 
					modal.style.display = "none";
				}
				</script>
	
				<figcaption>
					Current example terminal output<BR>(click to enlarge)
				</figcaption>
			</figure>
		</div>
		<!-- END COLUMN 2 -->
	</div>
	 <!-- GRID FOOTER -->
	<div id="downloadbox" class="grid_footer">
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_004_size.py" target="_blank">DOWNLOAD the code file for this example.</a>
	</div>
</div>
<BR>
<!-- end of snippet for SECOND (2nd) occurrence of application, terminal and source code screenshots on a single page -->



It's possible to write a three-line script that opens a window, but it’s rather *unPythonic*, so let’s go with something a little more elaborate. Other than the quick test demo above, this is just about the least amount of code we can write to get an actual *tkinter* application while maintaining good coding practices. I did add one extra line (the `print()` statement) which we’ll discuss. Here’s the code:

```python
import tkinter

def main():
	print(f"__name__: = {__name__}")
	window = tkinter.Tk()
	window.mainloop()
	
if __name__ == "__main__":
	main()
```

### Breakdown

Again, we start by importing the *tkinter* library.

Skipping over that `print()` statement, the rest of `main()` declares and opens a window. I’ll get back to the `print()` statement in a second.

The window declaration does obscure what's going on, so here's the dope...

- `Tk()` is the window class which is part of the `tkinter` module,
- `tkinter.Tk()` is shorthand for calling `tkinter.Tk().__init__()` and that creates the window object, and
- the `window` then opens automatically when `window.mainloop()` starts.

One other thing to note here. The way we imported tkinter means that every time we make a call to the tkinter library, we'll have to prefix the call with `tkinter.` (the name of the library followed by a dot) to avoid a `name <widget> not defined` error. In the next demo—and from them on—we'll change the way we import the library to avoid this situation.

Now let’s talk about the `print()` statement—which will make more sense if we do so in conjunction with the `if` statement at the bottom of the script. So, we’ll start there...

The `if` statement checks the script’s namespace. *Python* always gives an executing script the namespace `__main__`. Thus, the `if` statement is `True` and `main()` is executed.

And looking back at the `main()` function, the `print()` statement will write the namespace to the terminal. Take a look at the terminal's screenshot above to see the results.

Now let’s look at what happens when *Python* imports this same script as a module...

## Importing The Previous Demo

<!-- 6, 7, 8 -->
<!-- THIRD occurrence of application, terminal, and source code screenshots on a single page -->
<div>
	<!-- GRID HEADER -->
	<div class="grid_header">
		<p class="screenshot_grid_header_blurb">Results of This Example:</p>
	</div>
	<div class="columns">
		<!-- COLUMN 1 -->
		<div>
			<figure>
				<img id="img6" src="/images/screenshots/001_window/window_002_start_external.png" alt="Current example output">		<!-- img# -->
				
				<!-- Modal for screenshot -->
				<div id="modal6" class="modal">																<!-- modal# -->
					<span class="close6">&times;</span>														<!-- close# -->
					<img class="modal-content" id="img66">														<!-- img## -->
					<div id="caption"></div>
				</div>
				
				<script>
				// Get the modal
				var modal = document.getElementById("modal6");													// modal#
				
				// Get the image and insert it inside the modal - use its "alt" text as a caption
				var img = document.getElementById("img6");														// img#
				var modalImg = document.getElementById("img66");												// img##
				var captionText = document.getElementById("caption");
	
				img.onclick = function()
				{
				  modal.style.display = "block";
				  modalImg.src = this.src;
				  captionText.innerHTML = this.alt;
				}
				
				// Get the <span> element that closes the modal
				var span = document.getElementsByClassName("close6")[0];										// close#
				
				// When the user clicks on <span> (x), close the modal
				span.onclick = function()
				{ 
					modal.style.display = "none";
				}
				</script>
				<figcaption>
					Current example output<BR>(click to enlarge)
				</figcaption>
			</figure>
		</div>
		<!-- END COLUMN 1 -->
		
		<!-- COLUMN 2 -->
		<div>
			<figure>
				<img id="img7" src="/images/screenshots/001_window/window_002_start_external_term.png" alt="Current example terminal output"> 		<!-- img#, filename -->
	
				<!-- Modal for terminal shot -->
				<div id="modal7" class="modal">																			<!-- modal# -->
					<span class="close7">&times;</span>																	<!-- close# -->
					<img class="modal-content" id="img77">																	<!-- img## -->
					<div id="caption"></div>
				</div>
				
				<script>
				// Get the modal
				var modal = document.getElementById("modal7");																// modal#
				
				// Get the image and insert it inside the modal - use its "alt" text as a caption
				var img = document.getElementById("img7");																	// img#
				var modalImg = document.getElementById("img77");															// img##
				var captionText = document.getElementById("caption");
	
				img.onclick = function()
				{
				  modal.style.display = "block";
				  modalImg.src = this.src;
				  captionText.innerHTML = this.alt;
				}
				
				// Get the <span> element that closes the modal
				var span = document.getElementsByClassName("close7")[0];													// close#
				
				// When the user clicks on <span> (x), close the modal
				span.onclick = function()
				{ 
					modal.style.display = "none";
				}
				</script>
	
				<figcaption>
					Current example terminal output<BR>(click to enlarge)
				</figcaption>
			</figure>
		</div>
		<!-- END COLUMN 2 -->
	</div>
	 <!-- GRID FOOTER -->
	<div id="downloadbox" class="grid_footer">
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_002_start_external.py" target="_blank">DOWNLOAD the code file for this example.</a>
	</div>
</div>
<BR>
<!-- end of snippet for THIRD (3rd) occurrence of application, terminal and source code screenshots on a single page -->


The next script looks like this:

```python
import window_001_minimal

def main():
	window_001_minimal.main()

if __name__ == "__main__":
	main()
```

The `import` statement brings in our previous script by name—minus the `.py` suffix. It doesn’t mention the `tkinter` module because that's already imported in `window_001_minimal.py`.

Also, `main()` doesn’t declare and open a window. For that, we reach into `window_001_minimal.py` and call *that* `main()` function instead. Let's save this script as `window_002_start_external.py`.

Running this demo, we find that the namespace printed to the terminal is different. It's now the same as the imported script’s file name... minus the `.py` extension. Compare this demo's terminal screen-shot to the previous one to see how they differ.

But notice this... we’re testing for the namespace in exactly the same way in both scripts.

## Script Namespace Awareness

Adding those two lines at the end of every script is a good habit to get into. *Python* takes care of namespace details so we don't have to.

## Conclusion

Next time, we’ll touch on frames and discover that the statement made at the top of this post about windows being foundational to all things GUI may not be true. Until then, keep your campfires burning and, as they say in some parts, don’t let the COVID get you.

<div class="blog-nav">
	<div style="float: left;">
		<a href="/2021/08/10/0002-python-font-installation.html">Previous: Installing Python and Common Fonts</a>
	</div>
	<div style="float: right;">
		<a href="/2021/08/24/0004-just-ooping-along.html">Next: Just OOPing Along</a>
	</div>
</div>
