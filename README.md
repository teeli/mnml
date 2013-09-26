# mnml

**mnml** (pronounced *"minimal"*) is a tiny grid system for SASS (LESS and Stylus are coming soon).

> 
“Perfection is achieved, not when there is nothing more to add, but when there is nothing left to take away.” 
-Antoine de Saint-Exupéry

## Why another grid system?

Sure, there are a lot of grid systems around ranging from large frameworks to small components. The goal of **mnml** is to make the smallest possible "grid system" with just the bare essentials.

This is not a comprehensive grid framework á la [**960.gs**](http://960.gs/ "**960.gs**") and others. Instead, **mnml** uses simple mixins that helps the author to define their grid with as little overhead as possible.

In it's core, **mnml** is completely responsive and adapts perfectly to any container and screen size. Everything in the resulting CSS will be defined as percents.

**But isn't this just a couple of simple mixins and nothing more? Why release it in public?** 

This is based on a couple of SCSS mixins that I've used in several projects with very little changes. I've found it quite useful and timesaving, so I thought maybe someone else might as well.

## Examples

Below are some simple examples about setting up **mnml**. Examples directory in repository contains more examples that are a bit more in depth. All of the examples below assume an HTML structure like this:

	<!DOCTYPE html>
	<html>
		<head>
		</head>
		<body>
			<div class="row">
				<div class="col">
					This column has a width of 1 grid units
				</div>
				<div class="col-2">
					This column has a width of 2 grid units
				</div>
				<div class="col-9">
					This column has a width of 9 grid units
				</div>
			</div>
		</body>
	</html>


### SCSS

	// import grid system
    @import "mnml-gs"

    .row {
		// set up grid with width of 960px and gutter of 10px between each column
		@include grid-row(960px, 10px);
		.col {
			// define a column with a width of 1 column out of 12 
			@include grid-column(1, 12, 960px, 10px);
		}
		.col-2 {
			// define a column with a width of 2 columns out of 12 
			@include grid-column(2, 12, 960px, 10px);
		}
		.col-9 {
			// define a column with a width of 9 columns out of 12 
			@include grid-column(9, 12, 960px, 10px);
		}
	}

### LESS

	// import grid system
    @import "mnml-gs.less"

    .row {
		// set up grid with width of 960px and gutter of 10px between each column
		.grid-row(960px, 10px);
		.col {
			// define a column with a width of 1 column out of 12
			.grid-column(1, 12, 960px, 10px);
		}
		.col-2 {
			// define a column with a width of 2 columns out of 12
			.grid-column(2, 12, 960px, 10px);
		}
		.col-9 {
			// define a column with a width of 9 columns out of 12
			.grid-column(9, 12, 960px, 10px);
		}
	}

### Stylus

	// import grid system
    @import "mnml-gs.styl"

    .row
		// set up grid with width of 960px and gutter of 10px between each column
		grid-row(960px, 10px)
		.col
			// define a column with a width of 1 column out of 12
			grid-column(1, 12, 960px, 10px)

		.col-2
			// define a column with a width of 2 columns out of 12
			grid-column(2, 12, 960px, 10px)

		.col-9
			// define a column with a width of 9 columns out of 12
			grid-column(9, 12, 960px, 10px)



## Notes

Please note that all parameters passed to the mixins must use the same unit and you can't mix for example **px** and **em** values. Safest way is to always use **px** or **em** units, even with responsive grids (don't worry, **mnml** will only use those as a base for the calculation and the output will *always* be a responsive percentage based grid)

## License

**mnml** is licensed under [MIT License](LICENSE).
