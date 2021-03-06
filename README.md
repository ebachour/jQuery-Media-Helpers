jQuery Media Helper Utilities from jQuery Mobile: 
==
resolution and CSS media query related helpers and behavior

Dual licensed under the MIT (MIT-LICENSE.txt) and GPL (GPL-LICENSE.txt) licenses.

Demo page:
==
<a href="http://filamentgroup.com/examples/jquery-media-helpers/sample.html">http://filamentgroup.com/examples/jquery-media-helpers/sample.html</a>


Exposed utilities:
=====
- orientationchange event from jQuery Mobile

	Handler automatically falls back to resize event in browsers that don't natively support it
	
	The event object contains an "orientation" property, which will equal either "portrait" or "landscape"
	
	Examples:
	
		$(window).bind('orientationchange', function(event){
			//alert( event.orientation );
		});
			
			
- $.mh.media method: pass a CSS media type or query and get a bool return

	Note: this feature relies on actual media query support for media queries, though types will work most anywhere
	
	Examples:
	
		$.mh.media('screen') //>> tests for screen media type
		$.mh.media('screen and (min-width: 480px)') //>> tests for screen media type with window width > 480px
		$.mh.media('@media screen and (-webkit-min-device-pixel-ratio: 2)') //>> tests for webkit 2x pixel ratio (iPhone 4)
		
			
- Cross-browser media-query width and orientation breakpoint classes

	This script automatically adds classes to the HTML element:
	
		- "portrait" or "landscape" for orientation
		
		- Min/Max width breakpoint classes for the following widths (by default):
		
			320px, 480px, 768px, 1024px
			
			...which translate to classes that correspond to media query sytnax:
			
			.min-width-480px, .max-width-1024px, etc
			
	You can add breakpoints by number or array, like so:
	
		$.mh.addResolutionBreakpoints( 500 );
		$.mh.addResolutionBreakpoints( [500, 1200] );	