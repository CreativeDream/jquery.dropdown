jquery.dropdown 1.2
================

Simple dropdown menus to nearly anything with this simple plugin.

__<a href="http://creativedream.net/plugins/jquery.dropdown/" target="_blank">Demo Page</a>__

Usage
-------
__Styles:__

Include the jquery.dropdown css file in your html page.
~~~~ html
<link href="jquery.dropdown.css" type="text/css" rel="stylesheet" />
~~~~

__Javascript:__

Include the jQuery library and jquery.dropdown script file in your html page.
~~~~ html
<script src="http://code.jquery.com/jquery-latest.min.js"></script>
<script src="jquery.dropdown.min.js"></script>
~~~~
Create an element.
~~~~ html
<a class="dropdown">Dropdown Menu</a>
~~~~
The plugin is named "dropdown" and can be applied to any element. You will probably also specify some options while applying the plugin.
~~~~ javascript
$(document).ready(function() {
	$(".dropdown").dropdown({
		template: function(r) {
			return "<li><a>" + r.text + "</a></li>";
		},
		buttons: [
			//Button 1
			{
				text: 'Delete', //Inner HTML
				href: '', //<a> href
				addClass: 'custom-button', //<li> Class 
				onClick: function(p, e) {
					alert('Look in console!');
					console.log(p); //Parent (a.dropdown)
					console.log(e); //Clicked button 
					return true; //Return true - will close dropdown, false - will keep dropwdown 
				}
			},
			// Separator
			{},
			//Button 2
			{
				text: 'Options',
				href: '',
				addClass: '',
				onClick: function(p, e) {
					alert('Function return false!');
					return false;
				}
			},
			//Button 3
			{
				text: 'Properties',
				href: '',
				addClass: '',
				onClick: function(p, e) {
					alert(p.attr('rel'));
					return true;
				}
			}
		]
	});
});
~~~~

License
-------
> Licensed under <a href="http://opensource.org/licenses/MIT">MIT license</a>.
