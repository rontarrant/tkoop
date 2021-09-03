---
title: "0004: When is a Frame More Than a Frame?"
layout: post
tag: frame
topic: frame
description: How to use a Frame without a window and adding a second import statement to cut back o typing.
---

## Intro — What We're Doing

- we'll rephrase our import statement so we don’t have to keep typing the `tkinter.` prefix each time we make a library call, and
- we’ll see how a tkinter `Frame` can pretend to be in a window and get away with it.

Here we go...

## And Now, Some Neatly-phrased OOP

<!-- 0, 1, 2 -->
<!-- FIRST occurrence of application, terminal, and source code screen-shots on a single page -->
<div>
	<!-- GRID HEADER -->
	<div class="grid_header">
		<p class="screenshot_grid_header_blurb">Results of This Example:</p>
	</div>
	<div class="columns">
		<!-- COLUMN 1 -->
		<div>
			<figure>
				<img id="img0" src="/images/screenshots/001_window/window_003_oop_minimal.png" alt="Current example output">		<!-- img# -->
				
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
		
		<!-- COLUMN 2 -->
		<div>
			<figure>
				<img id="img1" src="/images/screenshots/001_window/window_003_oop_minimal_term.png" alt="Current example terminal output"> 		<!-- img#, filename -->
	
				<!-- Modal for terminal shot -->
				<div id="modal1" class="modal">																			<!-- modal# -->
					<span class="close1">&times;</span>																	<!-- close# -->
					<img class="modal-content" id="img11">																	<!-- img## -->
					<div id="caption"></div>
				</div>
				
				<script>
				// Get the modal
				var modal = document.getElementById("modal1");																// modal#
				
				// Get the image and insert it inside the modal - use its "alt" text as a caption
				var img = document.getElementById("img1");																	// img#
				var modalImg = document.getElementById("img11");															// img##
				var captionText = document.getElementById("caption");
	
				img.onclick = function()
				{
				  modal.style.display = "block";
				  modalImg.src = this.src;
				  captionText.innerHTML = this.alt;
				}
				
				// Get the <span> element that closes the modal
				var span = document.getElementsByClassName("close1")[0];													// close#
				
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
		<a href="https://github.com/rontarrant/tkoopython/blob/master/001_window/window_003_oop_minimal.py" target="_blank">DOWNLOAD the code file for this example.</a>
	</div>
</div>
<BR>
<!-- end of snippet for FIRST (1st) occurrence of application, terminal and source code screen-shots on a single page -->

Changing the import statement so we're left with the least amount of code to open a window looks something like this:

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

Yes, it’s another do-nothing example, but now we’re laying groundwork for what’s to come. Let’s look at the differences from our previous minimal example.

#### Import Everything and be Done with It

First, the `tkinter.` prefix:

```python
tkinter.Tk()
```

This library call can be done like this now:

```python
Tk()
```

Second, we derive our own `Window` class. It's not necessary, but it helps keep our code neatly modular.

#### The Derived Window

At the top of the class, we define an `__init__()` method. For this demo, it isn’t important, but when we start passing arguments to the super-class, it will be. And that call is made with the `super()` prefix. Be careful with the order of the brackets, dot, and underscores. The call has to look like this:

```python
super().__init__()
```

It’s awkward to type, but *Pythonic* as all git-out... OOPish, too.

There are other benefits to using a `Window` class which we’ll talk more about later.

#### main()

Instead of instantiating our window directly from the library, we instantiate the `Window` class. This keeps `main()` neat and tidy.

*Note: For this and all future examples, we don’t have to change anything in `main()`. It’s evolved as far as it needs to.*

The second line of `main()`—as before—opens the window.

Now let’s look at a pretentious frame...

## It’s a Frame Up

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
				<img id="img3" src="/images/screenshots/002_frame/frame_001_minimal.png" alt="Current example output">		<!-- img# -->
				
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
				<img id="img4" src="/images/screenshots/002_frame/frame_001_minimal_term.png" alt="Current example terminal output"> 		<!-- img#, filename -->
	
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
		<a href="https://github.com/rontarrant/tkoopython/blob/master/002_frame/frame_001_minimal.py" target="_blank">DOWNLOAD the code file for this example.</a>
	</div>
</div>
<BR>
<!-- end of snippet for SECOND (2nd) occurrence of application, terminal and source code screen-shots on a single page -->

So far, we've operated under the assumption that all tkinter applications need a window to put widgets in. Well, that’s not exactly true. We can get a window by sneaking in the back door, so to speak.

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

This code doesn't include a statement to add a window, but a window still opens. I'm not saying this is a great idea, but it is possible.

We can see further proof of the window's existence in the terminal where a list of the window's children is displayed using a call to `self.winfo_toplevel().winfo_children()`. There’s only one child—the frame—but the point is made... a frame can be the highest-level widget defined in your code.

We’ll be coming back to `winfo_toplevel()` and more of its child methods in later posts because it's a quick-n-easy way to access the attributes of an application's window... including those we add for ourselves.

## Conclusion

And that’s all for this time. Next time, we’ll see what a properly OOPed-up frame looks like as well as how it fits into the scheme of things.

‘Til then, take care of yourselves and may the elves of reusable code tinker with your tkinter.

<div class="blog-nav">
	<div style="float: left;">
		<a href="/2021/08/17/0003-windows-first-steps.html">Previous: Windows - First Steps</a>
	</div>
	<div style="float: right;">
		<a href="/2021/08/31/0005-not-so-minimal.html">Next: Not So Minimal</a>
	</div>
</div>

