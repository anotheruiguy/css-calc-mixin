# CSS Calc Mixin

This mixin makes it easer to use the CSS calc function and pass in values that need to be processed by Sass, mainly `em()` functions.

#### This mixin takes some simple arguments:
* `$attr` = the attribute you want to calc
* `$value` = the calculated value in the expression
* `$tb-property` and `$tb-property` = setting these values to `0` will set either the Top and Bottom, or Left and Right to `0`
* `$base` = the core width that is the base of the expression
* `$operator` = use either `-`, `+`, `*` or `/`


### Example Sass

	.block {
	  @include calc(width, em(220));
	}
	
	.block {
	  @include calc(margin, em(220), 0);
	}
	
	.block {
	  @include calc(width, em(220), true, 0);
	}
	
	.block {
	  @include calc(width, em(220), true, 0, 50%, '+');
	}



### Example output CSS

	.block {
	  width: calc(100% - 13.75em); }
	
	.block {
	  margin: 0 calc(100% - 13.75em); }
	
	.block {
	  width: calc(100% - 13.75em) 0; }
	
	.block {
	  width: calc(50% + 13.75em) 0; } 
	  
	  
## To install

A few choices, you could simple copy and paste the code into your project or Bower all the things! 

	$ bower install css-calc-mixin --save
	
In your Grunt file (using Grunt-Sass):

	sass: {
      dist: {
        files: {
          'application.css': 'sass/application.scss'
        },
        options: {
          includePaths: [
            './bower_components/css-calc-mixin'
          ]
        }
      }
    }
    
In your Sass manifest:

	@import "css-calc-mixin";
