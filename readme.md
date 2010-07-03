## Select boxes suck, so I made jquery.dd.js

It works like this:

1. Takes all attributes of a `<select>` tag and replaces it with a `div` with the same attributes (classes, id's etc).
1. The `<div>` is given certain behaviors to make it act almost like a normal select box.
1. In the div, we add a `<input type="hidden">` so that a name/value will get submitted along with the form as expected.
1. Unlike other select box replacement plugins I've seen, this one is meant to be styled *entirely* in css. The only css property that the plugin sets is the `overflow` property, to control the showing and hiding of the options. This gives you complete freedom to style it however you want.

Basic use:

1. `$('#my_select_box').dd();`
1. You'll also need some basic styles. Or it won't appear to work. Grab what you need from styles.css as a starting point and then tweak it to your heart's desire.

Shortcomings:

1. No keyboard support, yet.
1. No way to tab to it, yet.

Advanced use:

1. It supports `onChange` events by passing a function to the plugin like this:


		$('#test1').dd({
			change_callback: function() {alert(this);}
		});
	
