# Bootstrap 3.0 for MediaWiki

This is a MediaWiki skin that uses Twitter Bootstrap 3.0! The framework gives a boatload of features that play really nicely with a MediaWiki installation. To get up and rolling, there's a few things that should be done.

## Installation
First, clone the repository into your `skins/` directory.

````
git clone https://github.com/jellybellys/bootstrap-mediawiki.git
````

Next, in `LocalSettings.php` set:

````php
$wgDefaultSkin = 'bootstrapmediawiki';
````

Then add at the bottom:

````php
require_once( "$IP/skins/bootstrap-mediawiki/bootstrap-mediawiki.php" );
````

## Setup
Once you've enabled the skin, you'll want to create a few pages.

### Create: Bootstrap:Footer
This MediaWiki page will contain what appears in your footer. Here is an example of what to put in it:

	<div class="row">
		<div class="col-md-6">
			=== Stuff ===
			* [[Link to some place]]
			* [[Another link]]
		</div>
		<div class="col-md-6">
			=== More Stuff ===
			* [http://external.resource.org Go here]
		</div>
	</div>


### Create: Bootstrap:TitleBar
This MediaWiki page will control the links that appear in the Bootstrap navbar after the logo/site title.  The format that this page is expecting is as follows:

	* Menu Item Title
	** [[Page 1]]
	** [[Page 2]]
	** [[Page 3]]
	* Another Menu
	** [[Whee]]
	** [[OMG hai]]
	* [[A Link Menu]]

If you created a submenu in the older Bootstrap 2.x theme from BorkWeb, it will automagically be merged into the titlebar.

### Create: Template:Alert
This template is used to leverage Bootstrap's alert box:

	<div class="alert {{{2}}}"><strong>Heads Up!</strong> {{{1}}}</div>

Usage:

	{{alert|Message you want to say|alert-danger}}

### Create: Template:Tip
This template is used to do Bootstrap tooltips!

	<span title="{{{2}}}" class="tip" rel="tooltip">{{{1}}}</span>

Usage:

	{{tip|Something|This is the tooltip!}}

	or

	{{tip|[[Bacon]]|Delicious snack}}

### Create: Template:Pop
This template is used to do Bootstrap popovers!

	<span data-original-title="{{{2}}}" data-content="{{{3}}}" class="pop">{{{1}}}</span>

Usage:

	{{pop|Whatever triggers the popover|Popover Title|Popover Content}}

### Create: Bootstrap:Jumbotron
The content of this page will be put on your home page under "Welcome to WikiNameHere!"

### Short Title
If you want a shorter title to appear in your navbar, you can add <code>$wgSitenameshort = 'Short Name';</code> to your LocalSettings.php file.

### Custom CSS
If you want a custom CSS file for overrides or site-specific features,
you can declare <code>$wgSiteCSS = 'bootstrap-mediawiki/custom.css'</code>

### Custom JS
If you want a custom JS file for overrides or site-specific features,
you can declare <code>$wgSiteJS = 'bootstrap-mediawiki/custom.js'</code>
