Acknowledgment 
    I am pleased to acknowledge Prof.Keith O’Hara for his invaluable guidance during the course of this project work. 

   I am grateful to other members of the Bard Computer Science Program, students and faculties, who co-operated with us regarding some issues. 


   Last but not least, we want to thank stemkoski from GitHub who created an awesome example of the application of Three.js in augmented reality that served as an essential building block for my project.

April, May, 2019

Principle
   The program utilizes THREE.js to create a simulated beer pong game in augmented reality. THREE.js allows us to create three-dimensional objects on the canvas which the webcam captures. 

   Players are asked to throw the ball using their keys, “Q” and “P”. With the help of controls displayed on the screen, players can adjust the power and angle of which they throw the ball. The objective is to eliminate all the opponent's cups by aiming the ball into them. 

   This is an important problem as augmented reality could make video games more emerging and engaging. Augmented reality is also becoming the future of game design and is featuring more in mobile applications, this project gave as an excellent opportunity to get immersed in a virtual world. 

   I am confident I could create an augmented game even though I knew it would be a difficult task. Big game studios and developers take years and spend a lot of money trying to create augmented reality games but if I could get a simple yet entertaining beer pong game going then that would be a success. 

   More importantly, it is so fun.

Design
   The game is designed to be played over a flat surface with markers helping place the location of the cups and the ball movement. There will be two sets of four markers, each set with a unique letter and symbol. The cups displayed on one set of markers will be red and the other will be blue. Each side will have three cups in a triangle/pyramid formation. Image 1 shows this setup. As for the ball, the players are controlling the ball based on the power/angle bar on the top right corner of the page. This was done by using Google’s DAT.gui library. 
   THREE.js was an excellent tool to create virtual objects with webcams on a computer screen. Instead of creating our own, I used THREE.js for the display of the cups and the movement of the ball. THREE.js also allowed us to add lighting and texture to the objects helping them look more realistic. Additionally, I employed texture for the ball after the demo on Thursday.

   I used three meshes in total. One for the ball movement, and two for each player’s set of the six cups. By decreasing the number of meshes, I speed up our program. However, the trade-off is that it became harder for us to remove objects from the mesh since in THREE.js what has been drawn on the canvas won’t be removed unless the mesh is removed, resulting in a difficulty presenting a “score” in our game. Once the ball hit the cup, I couldn’t get the cup to disappear. Our solution is that I put on another colored cylinder object on top of the original cup to make the liquid in the cup look like it disappeared. 

Implementation
   I realized our design by using multiple libraries, meshes, GUIs, markers and a locally hosted server. Some of our main methods and variables will be discussed below:

Important methods that I wrote:
parabolicPath(): This method is the main method of the game. It controls the ball movement by returning a three-dimensional vector crucial to the ball movement and triggers a vanishing illusion (adding more to the mesh) once a ball collides with a cup.
I create an cylinder object called “drunk”. Later within the same method, I display “drunk” in if-statements if the ball hit the specific cup, it looks like the cup was emptied.

drawSixA() & drawSixB(): These methods help create meshes that recognize the markers and draws blue and red cups on top of the markers. This, in turn, creates a realistic cup. This method uses two cylinders with varying opacities, sizes and colors to look like cups filled with beer. The code for these methods is presented in the appendix.

Important variables:
sceneGroup: It is a variable that contains virtual objects in it which is essential for our game to display in augmented reality. Red and Blue have different sceneGroups. 
markerRoot: Is a variable that helps assigns different markers (also known as QR code) to be recognized by the camera and perform our desired operations. 
blueArr and redArr: Are boolean arrays which help tell use if the ball has collided with a cup. This is done by assigning different cups unique indices in the array with that have true or false values. 


Evaluation
   As scientists, I normally measure the runtime and the program’s performance. In this game, it is not too important to measure the runtime and check the efficiency of the program. This program can be evaluated on the visual appeal and the usability aspect. 

   This beer pong video game looks like normal beer bong but in augmented reality. In terms of creating a realistic virtual world that displays on a computer screen, this game was successful. Especially after I added the texture for the ball. The ball looks more wholesome in a three dimensional setting, and the ball compliments the realistic cups.

  In terms of the usability, the game is not glitchy as long as the webcam could capture a clear image of the markers. I could potentially even change the angle of the camera while the ball is in the air. The way to play the game is pretty straight forward. The GUI and keyboard controls provide smooth gameplay and is user-friendly. 


Scope for further investigation:

-Making the screen change colors
-Displaying an end game slide
-Playing on your phone
-Using bounding boxes to recognize object collision



