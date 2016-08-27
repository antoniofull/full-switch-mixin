Sass Switch Mixin.
==============

HTML
----

The Html is composed by :

- 1  A container. It can be any element you want, div, p, a, span.
- 2  A checkbox input with data-type=switch
- 3  The label

Example: 

	<p class="switch ios rounded">
		<input type="checkbox" name="my-switch" data-type="switch">
		<label for="my-switch"></label>
	</p>

The use of classes depends on what type of css implementation is done, sass or css.

You can use the switch with Sass or as standalone css file.

CSS
------
### You need to import the file switch.css or switch.min.css

There are 3 ways of importing it :

- 1 Via import. But this will fire a new http request
- 2 Copy and paste the styles in you main css file, possibly at the end of the file.(recommended)
- 3 Using a preprocessor or minifier or concat system.

Once you have imported the css file you can create a switch just adding classes to your HTML code(For the HTML Code refer to the  [html part](#html)).

Possible classes:

	switch -> Creates a basic switch button in ios style.
	switch ios -> Specify the type IOS
	switch ios rounded -> Rounded Button
	switch ios square -> Square Button
	switch material -> Material Design style Button

### Full Examples :
	<link rel="stylesheet" href="switch.css">

	<p class="switch">
		<input type="checkbox" name="my-switch" data-type="switch">
		<label for="my-switch"></label>
	</p>
	<p class="switch ios rounded">
		<input type="checkbox" name="my-switch" data-type="switch">
		<label for="my-switch"></label>
	</p>

	<p class="switch ios square">
		<input type="checkbox" name="my-switch" data-type="switch">
		<label for="my-switch"></label>
	</p>

	<p class="switch material">
		<input type="checkbox" name="my-switch" data-type="switch">
		<label for="my-switch"></label>
	</p>


SASS
------

To use the mixin with sass.

### import the mixin in your sass file

	@import "switch";

include the mixin, possibly at the top of the declaration:

	.switch {
		@include switch();	
	}
Parameters : 

	$type - String - It can be either "ios" or "material". Default value is "ios". 
	$width: Number - Any number (with no unit) to define the width. Default value is 50	
	$subtype: String - Must be declared if the type is 'ios'. Can be 'rounded' or 'square'. Default value null or 'rounded'.
	$materialBackground - Hex Value - Must be declared if type is 'material'. Defines the background color. Default value: #8BC34A.
	$toggleBackground - Hex value - Defines the background for the toggle button. Default value is #ffffff.

If no parameters are defined, these are the default values: 

	$type: 'ios', 
	$width: 50,
	$subtype: 'rounded'
	$materialBackground: #8BC34A
	$toggleBackground: #ffffff

###Full Example: 

	.switch {
		@include switch($type: 'material', $width: 100, $materialBackground: '#7B1FA2',$toggleBackground: #f9f9f9);
	}


EXAMPLES
-------------

[On my Website](http://antoniofullone.com/switch/)



	.switch{
		@include switch();
	}
	.switch.ios.rounded {
		@include switch('ios', $subtype: 'rounded');	
	}
	.switch.ios.square {
		@include switch('ios', $subtype: 'square');	
	}
	.switch.material {
		@include switch('material', $materialBackground: '#9C27B0');
	}

	<p class="switch"><input type="text" data-type="switch"><label for=""></label></p>
	<p class="switch ios rounded"><input type="text" data-type="switch"><label for=""></label></p>
	<p class="switch ios square"><input type="text" data-type="switch"><label for=""></label></p>
	<p class="switch material"><input type="text" data-type="switch"><label for=""></label></p>