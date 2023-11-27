//# Processing-Basics-Tutorial
//A beginners guide to programming in processing with very basic examples and comments to explain in most simple way. This is to avoid overexplaining which tends to //confuse beginners.


////// EXPLANATIONS OF 6 MAIN THINGS USING COMMENTS /////

// use // to make comments, if something doesnt work then sometimes useful to comment it out rather than delete
// usually when declaring a variable or performing an action/function, end with a ;

// 1) variables - local (only exists within a funtion in which it is declared)
//                global ( put on top of project above setup and exists for all functions)

// 2) function () - {does smth}
//               - lots of functional ready on processing - Setup, draw, print are functions

// 3) print ("Well this seems to be working") - good for debugging

// 4) array [] - {list of stuff}

// 5) if statement - (if something happens) {do something}

// 6) for loop - do stuff multiple times


/// DECLARE GLOBAL VARIABLES THAT WILL BE USED LATER //
int x = 1; // global int variable, an int is a whole number
float f = 1.2345; // global float variable, an float can be a decimal number
int[] array = {0, 1, 2}; // global int array variable
int squarey = 150; // for moving red box later



// ACTUAL PROJECT USUALLY MADE UP OF BUNCH OF FUNCTIONS ALL INTERACTING WITH EACH OTHER //

//Setup happens/runs once at the beggining
void setup () {
  
  size(400, 400); // size screen

  
  // Self Made functions that will run once at setup, scroll down to see what they do, they will run in order from top to bottom

  arrayStuff();
  myPrint();
  doManyTimes();
  
}


// draw runs after setup and Happens/runs every frame (for 60fps is 60 times per sec), useful for animations/movement etc
void draw () {
  background(150); // draws background, 0 = black, 255 = white, useful to have background in draw if having moving shapes
  
  squarey++; // ++ means add 1, since its in draw will add 1 every frame and therefore make the box move down
  //println(squarey);
  drawStuff();
  
}


// functions can be called anything and do anything but printing something is a basic example, this one starts with void
void myPrint() {
  
  //int x = 1; //local variable, use this if you only want this variable to exist in this function only, typically beginners just use global functions
  //println(x);
  
  println("this is my function");
  
}


// some functions like keyPressed already exist within processing, controls input of keys, there are other functions, google processing functions to explore
void keyPressed() {
  
  if (key == 'T' || key == 't') {
    println("t");
  }
  
}


// this is a for loop which states: do something this many times (10 in this example)
void doManyTimes () {
  
  // for loop (start = 0 , end = 10, increase i by 1 (index / counter))
  for (int i = 0; i < 10; i = i+1) { // dont worry about how this works too much just know that the 10 in the middle means run this 10 times
    print (i); // this is the counter ( i) which keeps track of how many times the function has run, goes from 0-9 making 10 times
  }
  
}


void drawStuff(){
  
  fill(255); // white
  ellipse(30,30,30,30); // small circle ( x,y,height,width)
  
  fill(50); // fill in whatever is after this as dark
  ellipse(100,100,100,150); // dark large ellipse
  
  fill(250,0,0); // fill red
  rect(150, squarey, 30, 40); // squarey increases every frame in draw function
  
}


void arrayStuff(){
  
  println (array[0]); // prints the 1st number in the array which is 0, I know its confusing but just remember that processing counts from 0 not 1 usually
  array = append (array, 3); // makes the array longer and adds a 3 
  println (array[3]); // prints the now added 3
  
}
