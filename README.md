# Scss Setup

----

## About

Scss setup is a set of Sublime Text snippets for setting up reset and media query breakpoint mixin.

----

## Setup

1. Navigate to `~/Library/Application Support/Sublime Text 2/Packages/User`
2. Clone the project to the directory with `git clone https://github.com/chakler/scss-setup.git`
3. Open your Sublime Text and voila!

----

## Usage

### Basic setup

Open a new scss file then type `setup` and hit `tab`, the reset, group separation, and clearfix class will appear.

### Setup media query breakpoint

Click on the line you want to set up the breakpoint then type `smq` and hit `tab`, the set up for the breakpoints will appear.
Key in the breakpoint widths, you can navigate down the breakpoint list using `tab`

### Using the media query mixin 

Type `mq` then hit `tab`, and this will appear:



	@include breakpoint(pm / lm / t / l / xl) {
	  
	}



Now you can type your screen size configuration.

- `pm` means portrait mobile. it's for mobile phones in portrait mode.
- `lm` means landscape mobile. it's for mobile phones in landscape mode.
- `t` means tablet. it's for tablets in any orientation.
- `l` means large or laptop. it's for desktop or laptop screens.
- `xl` means extra large. it's for desktop or laptop with larger screens. (It's set up for screens larger than 1600px by default.)

Type the size inside `(pm / lm / t / l / xl)` and hit `tab`, then type the properties for the chosen screen size:


	@include breakpoint(t) {
  		width: 30px;
	}


For example, I want the text color of `.description` to become red in tablet instead of the original black. Do:


	.description {
		color: black;
	
		@include breakpoint(t) {
		  color: red;
		}
	}


And this will be compiled into:


	.description {
		color: black;
	}

	@media only screen and (min-width: 768px) and (max-width: 1139px) { 
		.description {
			color: red;
		}
	}


# Acknowledgments

- [Reset CSS](http://meyerweb.com/eric/tools/css/reset/) by Eric Meyer
- [Micro Clearfix Hack](http://nicolasgallagher.com/micro-clearfix-hack/) by Nicolas Gallagher
- [Media query mixin](https://css-tricks.com/media-queries-sass-3-2-and-codekit/) by Chris Coyier
- [Breakpoint Sublime Snippet](https://gist.github.com/jnowland/5151162) by James Nowland