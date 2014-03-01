# Keeping Track of Terms

## Markdown
Markdown is a way of writing simple text documents that have rich text formatting (font sizes and styles, images, lists, and so forth). For more information, refer to the [markdown cheat sheet](http://blog.lib.umn.edu/crosb002/leadership/Markdown_Cheat_Sheet.pdf).

This document is written in markdown, so you can open it in your text editor to get an idea of how it works

## HTML(5)
HTML is the markup language that describes the structure of a web page. It is a standardised colleciton of tags that define the most basic elements of a page (paragraphs, headings, links, images) but **not** their look and feel. HTML is interpreted or *parsed* by the web browser.

HTML5 is the most recent version of the standard. Among other significant changes, it emphasises the use of so-called 'semantic' tags over generic tags. Two examples of generic tags are the containers `<div>` and `<span>`, which typically must be assigned classes or IDs to be differentiated from one another. For example to create a footer, one might define a container as `<div class="footer">`. The convention in HTML5 is to use semantically appropriate tags such as `<aside>`, `<header>`, `<footer>`, and `<article>` instead.

## CSS
*Cascading Style Sheets* are designed to let web developers keep the look and feel of a website separate from the structure (as defined by HTML), which makes designing a website cleaner and more efficient. CSS files (any file ending `.css`) are collections of rules that describe how HTML elements look and behave, incliding colours, fonts, spacing, and positioning on the page.

## Less
LESS is a CSS *pre-processor*. This means that it produces CSS files according to special rules. The LESS syntax is a subset of CSS, which means that all valid CSS is also valid LESS. So why would we use LESS and not normal CSS?

LESS allows a number of time saving shortcuts to be used when writing long or complex CSS files. A good example is the way that LESS manages colours. In CSS, colours are properties of elements. See the example below:

	.my-navigation-bar {
		background: #ff0000;
		font-family: "Helvetica", "Arial", sans;
		color: white;
	}
	
	.my-active-navigation-button {
		background: #aa0000;
	}
	
	.my-heading {
		color: #ff0000;
	}

In this example (using regular CSS) a class for a navigation bar sets the background colour of the element to red. Meanwhile, a class for an active navigation button sets the background to a slightly darker red. Finally, a class sets some headings to have the same color as the navigation bar, for the purposes of visual continuity. 

This CSS is perfectly valid, and will work as expected. The issue for a developer comes when they might wish to change the colours. Changing the navigation bar colour will require the developer to also adjust the active button colour, and the heading colour. This is simple enough when the rules are written next to each other and the colour codes are easy to remember, but if the rules were spread across a large CSS document and the code is too complex to remember, this can be a real pain. LESS solves this problem by introducing the idea of *variables* into CSS. 

Variables are 'containers' which can be assigned any value by the developer. Wherever the variable is references, the LESS compiler will substitute the value of the container. In the example above, we could use a variable to define our navbar colour, and then reference this variable throughout our code.

	@nav-color: #ff0000;

	.my-navigation-bar {
		background: @nav-color;
		font-family: "Helvetica", "Arial", sans;
		color: white;
	}
	
	.my-active-navigation-button {
		background: #aa0000;
	}
	
	.my-heading {
		color: @nav-color;
	}
	
Using this approach, we only have to remember to change one value (the value of `@nav-color`) and this change will be reflected wherever we reference that variable.

But what about our slignly darker avtive nav button? LESS also allows us to pass variables through *functions* that apply rules to the value of the variable in order to change it. LESS has a variety of built-in functions for modifying colours, including `lighten()`, `darken()`, `saturate()`, `desaturate()`, `fadein()`, `fadeout()`, `fade()` `spin()` and `mix()`. In our previous example, we could pass the value of `@nav-color` to our `darken()` function, to automatically calculate a darker colour. 

	@nav-color: #ff0000;

	.my-navigation-bar {
		background: @nav-color;
		font-family: "Helvetica", "Arial", sans;
		color: white;
	}
	
	.my-active-navigation-button {
		background: darken(@nav-color, 10%);
	}
	
	.my-heading {
		color: @nav-color;
	}
	

## Git
Git is a version management system. It gives developers a way to keep track of the work they are doing, and to collaborate with each other on large projects. Git uses a complex and often difficult to understand set of commands issued from the terminal. It is probably not worth learning in isolation, though you should try to understand the core concepts. 

Among these, the most significant are:

* **Repository** - A container for a project. The fundamental `unit` of git. They can be stored on your local computer, or on a remote computer, or both.
* **Pushing** - Sending your local copy of the code to a remote repository.
* **Pulling** - Copying the code from a remote repository to your local repository.
* **Commit** - An individual push.

## GitHub
Github is a free online git repository. It lets you store your code on a website that is accessible via a website.

## Bootstrap
Bootsrap is a HTML/CSS/JavaScript framework. It provides nicely styled default components, including buttons, navigation bars, and notifications. One of the biggest strengths of bootstrap is its grid system. Read about it on the [bootstrap website](http://getbootstrap.com).

Bootstrap uses LESS, which means it can be customised by overriding Bootstrap's LESS variables.

## CodeKit
Codekit is an application designed to automate and simplify a typical web development workflow. Among other features:

* It acts as a LESS compiler. This means that it watches LESS files in your project for changes, and then compiles them into CSS files.
* It allows frameworks like Bootstrap to be automatically included in projects. To understand how this works, see the `less/style.less` file in this project. The include statement tells CodeKit to import the bootstrap LESS files we downloaded from GitHub.
* It has the ability to minify (compress) JavaScript and CSS files to save space.

## Mou
Mou is a markdown viewer and editor. It opens and creates `.md` files. 

I used it to create this document.

## SublimeText
SublimeText is in many ways the most important piece of software for you to understand. It is a text editor with advanced features such as text completion (the ability to automatically complete text as you are writing it) and syntax highlighting (the ability to detect the language you are writing in, and to highlight different aspects of the code with different colours to help with visual clarity). You will use SublimeText to edit almost all the files you create as part of the web development process. It natively understands HTML, CSS, and JavaScript, and I have installed an add-on which allows it to understand LESS.

Learning SublimeText is an endeavor in its own right. Comprehensive vdeo tutorials are available on YouTube.
