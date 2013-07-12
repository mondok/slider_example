# Slider Example #

Slider example code that leverages http://refreshless.com/nouislider/

To see this example in action, visit http://htmlpreview.github.io/?https://github.com/mondok/slider_example/blob/master/index.html

### Notes ###
The code is pretty simple.  Simply create a div and two input boxes (for a start and an end). From there, you need to initialize the slider with the following JavaScript:

  	var sliderChanged = function(){
			// [lower, upper]
			var sliderValues = $(this);
			// call Solr index here
			var startValue = sliderValues[0];
			var endValue = sliderValues[1];
		};

  	$(".slider").noUiSlider({
		    range: [0, 100]
		   ,start: [50, 70]
		   ,handles: 2
		   ,serialization: {
		      to: [$("#start"),$("#end")]
		   }
		   ,slide: sliderChanged
		});
    
The most important thing to note is the `sliderChanged` function.  In the scope of something like a backend server where you're changing the UI based on sliding, you'll want to make an async call here to update the page based on the values.

That's it!
