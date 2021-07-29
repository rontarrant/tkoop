---
title: "0004: When is a Frame More Than a Frame?"
layout: post
tag: frame
topic: frame
description: How to use a Frame without a window and adding a second import statement to cut back o typing.
---

## Introduction

Last time, we looked at a minimal OOP demo, but I also said there’s a more convenient way to phrase our import statement so we don’t have to keep typing the `tkinter.` prefix over and over. We’ll start with that while also moving our window code to its own class for modularity’s sake.

Second, we’ll see how a tkinter Frame can pretend to be in a window and get away with it.

Here we go…

## And Now, Some Neatly-phrased OOP

<!-- z, y -->
<!-- FIRST occurrence of application and terminal screen shots on a single page -->
<div class="screenshot_two_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- LEFT SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="imgz" src="/images/screenshots/001_window/window_003_oop_minimal.png" alt="Current example output">		<!-- img# -->
			
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
			<img id="imgy" src="/images/screenshots/001_window/window_003_oop_minimal_term.png" alt="Terminal image">		<!-- img#, filename -->

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
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_003_oop_minimal.py" target="_blank">
		DOWNLOAD the code file for this example.
		</a>.
	</div>
</div>
<BR>
<!-- end of snippet for FIRST (1st) occurrence of application and terminal screen shots on a single page -->


So, what’s the least amount of code you can use to open a tkinter window? It’ll be something like this:

```python
from tkinter import *

def main():
	window = Window()
	window.mainloop()

class Window(Tk):
	def __init__(self):
		super().__init__()

if __name__ == "__main__":
	main()
```

### Breakdown

Yes, it’s another do-nothing example, but keep in mind that we’re still laying groundwork for what’s to come. Now let’s look at the differences from our previous minimal example.

Import Everything and be Done with It

That `tkinter.` prefix… this thing:

```python
tkinter.Tk()
```

No more of that. Import all of tkinter and we can just do this instead:

```python
Tk()
```

But also, we’re going to derive our own class and call it Window because… well, let’s call a window a Window. Why not?

#### Window Class

At the top of the class, we define an __init__() method. This isn’t important for this particular example, but we’re working on good OOP habits for now. All this initialization method does is call the parent class’s __init__() method—which is done by prefixing  with `super()`. And don’t forget the round brackets or the dot. It’s gotta look like this:

```python
super().__init__()
```

Yes, it’s awkward to type, but very Pythonic and OOPish enough to pass muster with even the most stoic of programmers. And without it? No window.

Another benefit of using a Window class is this: it allows us to play with that fire known as (gasp) global variables without actually getting burned. We’ll talk more about this later.

#### main()

Instead of instantiating our window directly from the library, we instantiate the Window class. This keeps `main()` neat and tidy and for this and all future examples, we don’t have to change anything in `main()`. It’s evolved as far as it needs to.

The second line—as before—opens the window.

Now let’s look at a pretentious frame…

## It’s a Frame Up

<!-- x, w -->
<!-- SECOND occurrence of application and terminal screen shots on a single page -->
<div class="screenshot_two_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- LEFT SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="imgx" src="/images/screenshots/002_frame/frame_001_minimal.png" alt="Current example output">		<!-- img# -->
			
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
			<img id="imgw" src="/images/screenshots/002_frame/frame_001_minimal_term.png" alt="Terminal image">		<!-- img#, filename -->

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
		<a href="https://github.com/rontarrant/tkoopython/blob/master/002_frame/frame_001_minimal.py" target="_blank">
		DOWNLOAD the code file for this example.
		</a>.
	</div>
</div>
<BR>
<!-- end of snippet for SECOND (2ND) occurrence of application and terminal screen shots on a single page -->


Remember last time when I said that all tkinter applications need a window to put widgets in? Well, that’s not exactly true… well, it sort of is. Let me explain.

Here’s out next example:

```python
from tkinter import *
from tkinter import ttk

def main():
	app = MainFrame()
	app.mainloop()

class MainFrame(ttk.Frame):
	def __init__(self, master = None):
		super().__init__(master)
		print(self.winfo_toplevel().winfo_children())
		
if __name__ == "__main__":
	main()
```

### Breakdown

There are no statements adding a window to that code, but it’s still there.

We don’t actually need to define it for it to exist and to see proof, just run the example. A window opens and the `print()` statement outputs a list of the window’s children to the terminal. There’s only one—the frame—but the point is made… a frame can be the highest-level widget defined in your code, but tkinter steps in and creates a window so the frame has a place to live.

BTW, we’ll be coming back to that winfo_toplevel() method in later posts to see what other magic it affords us. Here’s a hint: it relates to what I said earlier about (gasp) global variables.

So, why code a Window class when just a Frame will do?

That window class is a convenient place to store attributes used throughout the rest of an application. We’ll dig deeper into this as we go along.

## Conclusion

And that’s all for this time. Next time, we’ll see what a properly-OOP frame looks like as well as how it fits into the scheme of things.

‘Til then, take care of yourselves and may the elves of useable code visit you every night.


<div class="blog-nav">
	<div style="float: left;">
		<a href="/2021/08/10/0003-windows-first-steps.html">Previous: Windows - First Steps</a>
	</div>
	<div style="float: right;">
		<a href="/2021/08/17/0005-not-so-minimal.html">Next: Not So Minimal</a>
	</div>
</div>

