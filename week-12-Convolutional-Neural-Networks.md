# week 12: Convolutional Neural Networks

Ok, I'm skipping a little bit. This may even be a way to procrastinate on taking this classes midterm. I tried to work on project two recently, and made good progress- then forgot to save and lost it all. I'm going to do it again, but before that I wanted to learn something cool and make some progress, so i'm jumping to week 12. It's been awhile since I last posted notes (as college has been busy, with 3 clubs, a full time school, and a 20 hour a week internship- on top of a social life). But i'm back and gonna try to get week 12 done in one day (a sunday :) )




CNN: 

- made of a sequence of convolutional layers
- weights! 
- similar to the brain 
- used many places in the real world 

## 12.1 

- this stuff has changed computer vision research and industry standards- so pay attention! 
- recognition could be thought of as a big table look up 
- many possible pictures in the world ( each pixel has 256 possible values by RGB. Even for a small image thats 3x18 pixels, there is 256 raised to the 54 possible images. Thats 1.1*10^130 possible images.  MASSIVE, especially for such a small space)
  - we haven't seen anything yet of all possible pictures… as a species! 
- this shows us that the pictures we care about are not just random. The ones that are interesting have structure. 
  - ex: face image has parts of a face (eyes, nose, etc)



- Early deep learning instance: designed by Fukushima in the 1970's. It was a network structure using a deep architecture (input layer, contrast extraction, edge extraction, etc… all the way to the recognition layer)



Current state of the art: 

Goal: input an image, output a set of classifiers (weighted, so it tells us how likely each thing is)

We are building the black box. 

Between the input and output, we have a CNN. This is a sequence of convolution mappings from input img to hidden layer. Preserves topology but reduces size and expands dimensions. Each layer focuses on one particular component (ex: edges). Every time we expand the layers, we shrink resolution. 



- we want shift invariance bc we don;t care where stuff is 



key operations in CNN's: 

- convolution layers: 2d conv
- fully connected layers: matrix multiplication
- Sigmoid layer: sigmoid function
- pooling layers: subsampling (shrinks resolution)



REVIEW: 

### convolutional layers

- 2d convolution maps image to an image using a convolution kernel. Basically takes weighted sum in a region (designing the kernal was an active area of research)
  - a CNN makes the kernel for us based on the data! That way we don't have to make the filters ourself and choose which to use. This is why we need the labeled training data- to make the kernals. 

### fully connected layers

- Each pixel has connection to every pixel in the next layer
- weighted average process again (by a matrix)
- template matching again! 



### max pooling layer

- the orocess of reducing image or subsampling image
- max pooling: sliding window is applied on a grid of calues. The maximum is computed using the max value in the current window. 
- this gives some spatial invariance, as we only care about one pixel 





### sigmoid layer

- takes an input 0-1 and maps to another 0-1, based on a function. Its trying to pull info closer to one closer to one and info closer to 0 back to 0. 

(got a 4/4 on this videos quiz)

(It was a pretty long video...)

# Video 12.2: 

- now we look at a simple CNN

- 2 conv layers, 2 pooling layers, 2 fully connected layers, 3 sigmoid layers. A "simple" example 

- theres some notation here: 

  - Conv layer output is a square
  - fully connected later is a vertical rectangle
  - blue vertical line is pooling layer
  - pink line=sigmoid function 
  - greenline is softmax function 

  

  - W matrix is made of rows, which stores template they want to match with data (this will be learned)

  

  Key question: HOW DO WE LEARN PARAMETERS FROM THE DATA (painful by hand)

  

  - Answer: BACKPROPAGATION 
  - assume we are given a labeled dataset
  - we want to adjust paramaters so that the predictions will be as close to true labels as possible
    - this is tough: highly nonlinear 
    - could have billions of variables if we randomly guessed: basically impossible
  - we need clever ways to adjust the g's and w's so that the process converges quickly 
  - standard method: GRADIENT DESCENT 
  - we minimize a loss function, basically (lots of iteration!!!)

  - the goal is to converge to a local minima (usually good enough; but sometimes we wnat better, and there are methods for that)

- after we get the gradient of the cost function, we propogate it back to the last layer (if we adjust the values, what happens?) 
  - essentially we run through each layer doing this backpropagation using gradients 
- we're just messing with knobs essentially :) 
- this whole thing is a template matching process (kind of)
- backpropagation was trying to figure out the hidden layer variables, basically. It could be massive. It basically takes feedback one step at a time (as we said above)

(got a 3/3 on this videos quiz :) ). 



## Video 12.3 

- another long video lol. 
- designing a loss function: 
  - he showed an example (it was pretty in depth. THen he took the gradient of it, of course)
  - we use gradient to get the most change we can in the direction we want 
- decreasing the score of other classes also decreases the loss 

(got a 2/3 on this quiz)

# Video 12.4 

(was review. I watched it, but it was all noted down above)

note: there is no learning done in the pooling layer. The error that is propograted to the pooling layer is sent back to the node it came from 

(got a 2/3 on this section again- was kinda skipping through the video so I guess its expected. I just missed a small thing in a formula identifying question, which was my bad but if I need the formulas I can look it up- got the theory questions correct :) )



# video 12.5

- this is an end to end CNN example 
- mnist example 
- it learns the representations itself, which is cool 
- it can deal with shifts and twists and still match it to what it is. 
- hidden layers had to be computed (backpropogation)



got a 2/3 on the last quiz. That took me to an average of 81% on these quizzes. 