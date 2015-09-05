P4 Website Performance Optimization portfolio project README 9-5-2015
Aaron Wright
aaronfwright@gmail.com

To run the project:

-Clone the Git Repository from https://github.com/AFWrightOnDude/FEWD-Project-4-Web-Optimization.git to your computer.

-Use terminal or the command line to navigate to the main project folder

-Start a server using Python by running "python -m SimpleHTTPServer 8080"

-In your web browser, navigate to http://localhost:8080/ to view the project pages


=========================================================================
Changelog
=========================================================================
17:55PM Eastern 9-5-2015
-Made the following updates to the changePizzaSizes function in main.js
	-replaced document.querySelector with document.getElementsByClassName for speed
	-created a variable to store the length (number) randomPizzaContainer so the for loop can run
	using a constant
	-added container variable so that DOM is not touched as the for loop is ran

-Movded the variable pizzasDiv outside of for loop to prevent multple touches to DOM

-Revised updatePositions function in main.js
	-used document.getElementsByClassName() insteadof document.querySelectorAll for speed
	-moved Math.sin back inside of the for loop so that the pizzas move individually.

-Moved declaration for variable elem outside of the for loop in the block for document.addEventListener('DOMContentLoaded', function() section
-Created local variable movingPizzas so document.getElementById is not called while running
for loop in document.addEventListener('DOMContentLoaded', function() section

=========================================================================
Optimizations for the inxex.html page to receive a 90+ page speed score:
=========================================================================
-Resized and compressed pizzeria.jpg to reduce file size and loading time (seperate large size made for pizzeria page)
-Minified and inlined CSS to be included in the index.html file so there is not a seperate
download for the CSS code.
-Added "async" property to the script tag that calls Google Analytics to stop blocking.
-Added media="print" to the line linking to the print.css file.
-Unlinked the Webfont that was originally used.


=========================================================================
Optimizations for the pizza.html page
=========================================================================
-On line 533, I changed the number of small scrolling pizzas from 200 to 32.
-For the functions that move the small pizzas around the page, I moved variables
that only need to be recalculted once to outside of the for loops to prevent redundant
calculations:
	-In function updatePositions(), I added variable scrollAmount so that the for loop can access
	 the variable as a constant instead of recaclulating each time.
	-In function changePizzaSizes(), I moved the variables dx and newwidth from inside of the for loop to
	before the for loop to prevent redundant calculation and cut processing time.

I do not have seperate folders for my production code or deployment code- the major difference is that I inline the CSS so for
development the CSS file is updated, minified, then inlined for index.html.

