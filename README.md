# BrickBreaker
This a brick breaker app
<div align="center"> <img src="assets/brickbreaker.png"></div>

This is a free and fun interactive game that takes you back to your childhood. Specifically those days when you arnt sure what to play and cool math had your back.

I decided to make a Brick Breaker because as I was going through a list of examples it really popped out at me. All of the other ones seemed to have a boring outcome to me, however breaking things always seems fun to me.


To start out making the game I first made my header and established the title and the stylesheet.

<div align="center"> <img src="assets/Part1.png"></div>

After that i initiated my canvas along with the radius of the ball that i am going to use and how fast i want the ball to move. 


<div align="center"> <img src="assets/Part2.png"></div>
After i declaired the radius of the ball i then had to declare the path of the ball as well as the math of how the ball moved, the color of the ball, paint the ball that color and then to end the path that the ball went. 

Then we must actually draw the ball by calling the drawball() into the draw(). And since we do not want there to be a trail behind the ball we need to clearRect() to clear the canvas.
<div align="center"> <img src="assets/Part3.png"></div>

We are also going to call requestAnimationFrame(draw) in order to call the draw function repeatedly. Both of these combined clears the canvas and repeatedly redraws the ball so you can see it moving across the canvas. I did originally set the canvase to redraw every 10 milliseconds but after some research found that this was more efficient to the program. 
<div align="center"> <img src="assets/Part4.png"></div>

We also need to update the X, Y, Xd,yd variables so the ball will be painted in its new position. 
<div align="center"> <img src="assets/Part0.png"></div>

Next i added the paddle that the ball would eventually bounce off of. 
You need to initialize the paddle height, width,and placement
<div align="center"> <img src="assets/Part5.png"></div>
The placement math is done byy subtracting the paddles with from the canvas and dividing by 2. Similarly how you would ang a picture on the center of the wall. It tells you how far in from the edge the first edge should be.  

We then need to Draw the Paddle.
<div align="center"> <img src="assets/Part6.png"></div>
In this function we get the beginning path establish, the starting point, the color, fill in the shape of the color we have chosen and the closepath().

Then add the drawPaddle() to draw().

We need to establish are colision course now that we have the paddle. We need the ball to bounce off the walls in order to even think about using the paddle. 
First we need to make sure the program recognizes when the outside of the ball hits the wall not the center of the ball. 
<div align="center"> <img src="assets/Part7.png"></div>
For the step above it is only demonstrated for the right and top wall, you have to repeat for the bottom wall and the left wall. 
The bottom wall will be edited later which is why I did not include it here. 

Our Next step is to etablish the moving of the paddle especially if you want to hit the ball. 
Here we set them as false since nothing has been touched yet. 
<div align="center"> <img src="assets/Part8.png"></div>

Then we have to establish keyDownHandler() and KeyUpHandler().

The keyDownHandler() detects if either the right arrow key or the left arrow key is pressed down and sets the corresponding variable to true. 

The keyUpHandler() detects once the button has been released and sets the corresponding variable back to false so the paddle will not continue to sliding all over the bottom of the screen. 
<div align="center"> <img src="assets/Part9.png"></div>


Now we implement the paddle moving in the Draw()

With the following code in the draw method it repaints the paddle moveing as you press the arrows either left or right. All the wile maintaining the paddle on the canvas and with in the boarder. 

<div align="center"> <img src="assets/Part10.png"></div>

Next Is to Install the Bricks on the canvas, the fun part. You first have to declair the row, colums, width, height, padding, and offset of the bricks. 

<div align="center"> <img src="assets/Part11.png"></div>

However just declairing the bricks wont actually form the brick field. You need to set up an array for the bricks to form. Here we also set the score and the lives variables. 

<div align="center"> <img src="assets/Part12.png"></div>

The for statment in the code above allows us the create the table of bricks, we also set the status to 1 which we will address later when it comes to the removal of blocks.

Now that we have established the order and placement of the bricks we need to draw them with drawBricks(). 

<div align="center"> <img src="assets/Part13.png"></div>

The code above draws the bricks in the canvas.  It also sees if the status is equal to one. If the status is equal to one then the brick will be drawn however once the ball hits the brick it will see if the  the brick to 0 and the brick will no longer be painted. The status does not get reset until the game restarts. 

We must not implement drawBricks() into Draw().

Now that the bricks are drawn we need to colid into them. 

<div align="center"> <img src="assets/Part14.png"></div>

In the code above we will change the direction of the ball of the if the coordinates of the ball is inside the coordinates of the brick. Once the ball has hit the brick and changes the direction then the status of the brick will be set to 0. Once the brick is set to 0 then the block disapears and will not return. Earlier we set the lives variables, now we will incriment it upword once the status of the block has been decrimented. The score holds through out the entire game. It the score is equal to the amount of blocks on the canvas then a congradulations alert will send.  

You must then include collisionDetection() in the Draw().

Displaying the score.

<div align="center"> <img src="assets/Part15.png"></div>

We want to displat the score, so we must include font, the coloring, and where we would like it to be placed.
Then we must include the drawScore() in the draw().

Now that we have a scoring system set up, i took away the collision for the bottom wall and gave a penalty for if you missed the ball with the paddle. 

<div align="center"> <img src="assets/Part16.png"></div>

This picture above has some code that we did earlier, i am now showing you the removal of the bottom wall and once the bottom wall is hit, then you loose a life (which we declaired earlier). If the amount of lives are none then a Game over alerts is displayed and the game will reload once you hit okay. 

The code above also shows that if there are lives left then the paddle resets to its original postioning. This is displayed in draw().

Last but not least the we have to implement the drawLives() so we can display how many lives we have left. 

<div align="center"> <img src="assets/Part17.png"></div>

This is similar to how we implemented the drawScore() however we are placing it on the oposite side of the canvas. 

Now to spice it up a little i added buttons to Easy, Medium, and Hard levels. Where the only diffence in code is the speed in which the ball moves. 

<div align="center"> <img src="assets/Part18.png"></div>

















  


