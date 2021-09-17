---
title: "0007: First Child Widgets"
layout: post
tag: button
topic: button
description: Populating a window/frame with a simple Button widget... with a callback. Then, a second button derived from a hand-rolled generic button class.
---

## Intro — What We're Doing

Today, we’ll start looking at widgets that populate windows (and frames) and what better way to start than with a button or two so we’ve got something to click on besides the window’s close gadget. We'll also look at:

- callbacks,
- rolling our own super-class Buttons, and
- deriving child classes from that super-class.

## A Button with a Callback

<!-- z, y -->
<!-- FIRST occurrence of application and terminal screen shots on a single page -->
<div class="screenshot_two_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- LEFT SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="imgz" src="/images/screenshots/003_button/button_001.png" alt="Current example output">		<!-- img# -->
			
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
			<img id="imgy" src="/images/screenshots/003_button/button_001_term.png" alt="Terminal image">		<!-- img#, filename -->

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
		<a href="https://github.com/rontarrant/tkoopython/blob/master/003_button/button_001.py" target="_blank">
		DOWNLOAD the code file for this example.
		</a>
	</div>
</div>
<BR>
<!-- end of snippet for FIRST (1st) occurrence of application and terminal screen shots on a single page -->

This demo will show—not just a button, but a button with a callback. Because... why create a button that does nothing?

Here’s what we’ve added to the simple code from previous OOP demos:

```
class HelloButton(ttk.Button):
	def __init__(self, frame):
		super().__init__(frame)
		# object attributes
		self.text = "Say Hello"
		self.message = "Hello, tkinter World!"
		# configure
		self.grid()
		self.config(text = self.text, command = self.say_hello)

	def say_hello(self):
		print(self.message)
	
```

The first thing you’ll notice about this demo is that it won’t win any awards for design. It does, however, illustrate the basics... plop down a button, hook up a callback, and show a result. (Check the terminal/Command Prompt/shell/what-have-you to see output.)

### Breakdown

A new class named `HelloButton`. It could also have been called simply *Button*, but it’s specialized to do that `‘Hello, World’` thing we’ve all come to love when exploring a new language or GUI toolkit. Here’s how that specialization breaks down:

- `self.text`: text to be slapped onto the button face,
- `self.message`: text to be dumped to the terminal when the callback is triggered, and
- `self.config()`: configure the button using the previous variables.

#### Callback

Like all *Python* callbacks, the first (and in this case, only) argument must be self-referential. I won’t attempt to explain why and it doesn’t matter anyway. It’s just the way things are done in Python.

The only statement here is straightforward: dump some text to the terminal. And this is why we used the `self.` prefix when we set up the object attribute in the initialization method. If we hadn’t, we’d have to pass the `message` attribute as an argument. We’ll look at doing that down the road, but for now, we’re keeping it dead simple.

So, that’s what a simple `Button` looks like, but most of the time, we’ll need more than a simple `Button`.
## Buttons of a Feather

<!-- x, w -->
<!-- SECOND occurrence of application and terminal screen shots on a single page -->
<div class="screenshot_two_grid_container">
	<div class="gridheader">
		Results of this example:
	</div>
<!-- LEFT SCREENSHOT -->
	<div class="gridscreenshot">
		<figure>
			<img id="imgx" src="/images/screenshots/003_button/button_002_derived.png" alt="Current example output">		<!-- img# -->
			
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
			<img id="imgw" src="/images/screenshots/003_button/button_002_derived_term.png" alt="Terminal image">		<!-- img#, filename -->

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
		<a href="https://github.com/rontarrant/tkoopython/blob/master/003_button/button_002_derived.py" target="_blank">
		DOWNLOAD the code file for this example.
		</a>
	</div>
</div>
<BR>
<!-- end of snippet for SECOND (2ND) occurrence of application and terminal screen shots on a single page -->

`Button`s all have a few things in common, so much so that we can set up our own super-class `Button` to configure these things, then override them when we have to in the derived `Button`s.

### Button Super-class

Things all `Button`s have in common:

- a label (might be text, might be an image, but for now, let’s stick with text),
- an action to be carried out when the user clicks it, and
- GUI placement.

And here’s the code for our super-class:

```python
class Button(ttk.Button):
	def __init__(self, parent):
		super().__init__(parent)
		# object attributes
		self.text = "*******"
		self.message = "no message"
		# configure
		self.config(command = self.do_something)
		self.grid()

	def do_something(self):
		print(self.message)
```

The object attributes are rather generic as is the `do_something()` method, but they’re fine for a demo. They define:

- the placeholder button name as a row of asterisks (in case I forget to name one of the derived buttons I write later, this should stand out enough to catch my eye), and
- the placeholder message as being `no message` at all.

As for `do_something()`, all it does is spit the message to the terminal.

### Derived Classes

First, another HelloButton:

```python
class HelloButton(Button):
	def __init__(self, parent):
		super().__init__(parent)
		# object attributes
		self.text = "Say Hello"
		self.message = "Hello, tkinter World!"
		# configure
		self.config(text = self.text)
```

Here we do an override on `self.text` (the Button label) as well as `self.message`.

The other thing we do—and we didn’t do this in the super-class—is make a call to `self.config()` to set the Button’s label text.

In fact, it doesn’t even make sense to make this call in a super-class. If we did do it there instead of in the derived class, all our buttons would have the generic label `*******` despite the fact that we change this attribute for each derived class. Since that’s the way things work in *Python*, we might as well just make the call here in the derived class and be done with it.

Second, we have a `GoodbyeButton`. The only thing of note here is that we don’t override the value of `self.message` and so clicking the `GoodbyeButton` spits out the generic message defined in our `Button` super-class.

## Conclusion

And that’s all for today. `Button`s, callbacks, and derivation of classes. Good stuff to keep in mind when building UIs.

Next time, we’ll dig into sizing a `Window` in a couple of different ways, one of which can be overridden by sizing demands made by child widgets.

Until then, keep your windows clean and stay safe.


<div class="blog-nav">
	<div style="float: left;">
		<a href="/2021/09/07/0006-site-stuff.html">Previous: Site Stuff You'll Want to Know</a>
	</div>
<!--	<div style="float: right;">
		<a href="/2021/09/21/0008-window-size.html">Next: Controlling Window Size</a>
	</div>
-->
</div>

