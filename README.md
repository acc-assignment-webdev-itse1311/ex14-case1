# NP HTML5, CSS3, and JavaScript 6e Tutorial 14, Case Problem 1


## Introduction
```

1.  Use your editor to open the bu_home_txt.html and bu_bubbles_txt.js files from the html14 > casel folder. Enter your name and the date in the comment section of each file, and save them as bu_home.html and bu_bubbles.js respectively.

2.  Go to the bu_bubbles.html file in your editor. Within the document head, add a script element for the bu_bubbles.js file. Load the file asynchronously.

3.  Scroll down to the section element with the ID "logosection" and insert a div element with the ID "bubbleBox" in which you will display the bubble images.

4.  Save your changes and go to the bu_bubbles.js file in your editor. Directly below the comment section, create an object literal for the box object. Add the following properties to the object: the width property with a value 1024 that defines the width of the box containing the bubbles, and the height property with a value of 500 defining the box's height.

5.  Create an object constructor function for the bubble class of objects. Include two arguments with the function: the size argument specifying the radius of the bubble, and the img property speci¬fying the URL of the image file of the bubble image. Add the following properties to the bubble object class:
    a.  The radius property, setting it to the value of the size argument.
    b.  The imageURL, setting it to the value of the img argument.
    c.  The xvelocity property, storing the horizontal velocity of the bubble and the yvelocity property storing the vertical velocity. Set both values to null.
    d.  The xPos property, storing the horizontal position of the bubble and the yPos property storing the vertical position. Set both values to null.
    e.  The opacity property, storing the bubble's opacity. Set its value to 1.
    f.  The hue property, storing the bubble's hue value. Set its value to 0.
    g.  The rotate property, storing the speed of the bubble's spin. Set its value to 0.
    h.  The rotateDirection property, storing the direction in which the bubble spins. Set its value to 1.

6.  After the bubble constructor function, create the following methods for the bubble prototype:
    a.  The fadeBubble() method that causes the bubble to fade by reducing its opacity. Insert a command to decrease the value of the bubble's opacity property by 0.0005.
    b.  The changecolor() method that changes the hue of the bubble. Insert a command that increases the value of the bubble's hue property by 3 and then calculates the remainder by dividing that sum by 360, storing the result in the hue property. (Hint: Use the % operator described in Figure 9-24 to calculate the remainder.)
    c.  The rotatebubble() that rotates the bubble. Insert a command that increases the value of the rotate property by the value of the rotateDirection property and then calculate the remainder by dividing that sum by 360, storing the result in the rotate property. (Hint: Once again use the % operator.)

7.  Create the movebubble() method for the bubble prototype that moves the bubble across the bubble box, bouncing the bubble off the box's wall if necessary. The method has two arguments: height and width defining the height and width of the box. Insert the following commands into the method:
    a.  Create the following variables to define the extent of the bubble: bubbletop equal to the value of the yPos property, bubblebottom equal to the sum of the yPos and radius properties, bubbleLeft equal to the value of the xPos property, and bubbleRight equal to the sum of the xPos and radius properties.
    b.  If bubbleTop is less than zero or bubbleBottom is greater than the height argument, then the bubble has hit the top or bottom wall; if so, change the direction of the vertical velocity by letting this.yVelocity equal this.yVelocity.
    c.  If bubbleLeft is less than zero or bubbleRight is greater than the width argument, the bubble has hit the left or right wall; if so, change the direction of the horizontal velocity by letting this.xVelocity equal this.xVelocity.
    d.  Move the bubble to its new location by adding the value of the yVelocity property to yPos and adding the value of the xVelocity property to xPos.

8.  Scroll down to the event listener for the load event. Drew has already inserted a setInterval() method that is set up to create a new bubble every half-second as long as there are no more than 20 bubbles already in the box. Drew has also nested the randInt() function within the event handler that returns a random integer within a specified range. You will use the randInt() function to create bubbles of random appearance, velocity, hue, and spin. Within the if condition, add the commands specified in Steps 9 through 15.

9.  Declare the newbubble variable using the new bubble() object constructor to create a bubble. Set the size of the bubble to a random size between 50 and 120 and the image file to "bu_bubbleint.png", where int is a random integer from 1 to 10. (Hint: Use the randInt() function to generate the random integers for both the size and img arguments.)

10. Define the following property values for the newBubble object:
    a.  Set the xPos and yPos properties to half of the box.width and box.height properties respectively, placing the new bubble in the center of the bubble box.
    b.  Set the xVelocity and yVelocity properties to a random integer between 5 and 5.
    c.  Set the rotate and hue properties to a random integer between 0 and 360.
    d.  Set the rotateDirection property to a random integer between 2 and 2.

11.  Next, you will create an inline image displaying the bubble image within the bubble box. Add the following commands to create the bubble image:
     a.  Create an img element named bubblelmg with its position property set to absolute.
     b.  Set the src property of bubblelmg to the value of the imageURL property of the newBubble object.
     c.  Set the width style of bubblelmg to radiuspx, where radius is the value of the radius property of newBubble.
     d.  Set the left and top styles of bubblelmg to xPospx and yPospx respectively, where xPos and yPos are the values of the xPos and yPos properties of newBubble.
     e.  Append bubblelmg to the bubbleBox element.

12.  Now, that you've created the bubble image, you will insert commands to animate its appearance. Within the if statement, add a setinterval() method that repeats an anonymous function every 25 milliseconds, storing the ID of the setInterval() method in the bubblelnterval variable. Add the commands specified in Steps 13 through 15 to the anonymous function.

13.  Apply the fadeBubble() method to the newBubble object to decrease the bubble's opacity.

14.  lf the opacity property of newBubble is less than 0, remove the bubble by
     a.  Removing bubblelmg element from bubbleBox.
     b.  Applying the clearInterval() method to stop the animation effects for the bubble, using bubblelnterval as the lD of the repeated command.

15.  Otherwise, animate the bubble by adding the following the commands:
     a.  Set the value of the opacity style of bubblelmg to the value of the opacity property of the newBubble object.
     b.  Change the hue of the bubble by applying the changeColor() method to the newBubble object and applying the filter style hue-rotate(huedeg) to bubblelmg where hue is the value of the newBubble's hue property.
     c.  Spin the bubble by applying the rotateBubble() method to the newBubble object and applying the transform style rotate(rotatedeg) to bubblelmg, where rotate is the value of the newBubble's rotate property.
     d.  Move the bubble by applying the moveBubble() method with box.height and box.width as the argument values. Set the top and left styles of bubblelmg to the values of the yPos and xPos properties of the newBubble object.

16.  Document your work by commenting your code throughout the file.

17.  Save your changes to the file and then load bu_home.html in your browser. Verify that the animated bubbles are displayed in the company logo that spin, move, bounce off the wall, and change colors in random fashion. Verify that the bubbles eventually fade out, to be replaced by new bubbles of varying sizes and shapes.
```