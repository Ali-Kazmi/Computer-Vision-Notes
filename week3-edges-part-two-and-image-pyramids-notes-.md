# Week 3: Image Convolution and Edge Detection Part 2


## Personal updates 
I'm starting week 3 before finishing week two's labs. Bad, I know. I'll do them tomorrow then post notes on what I learnt from them here (not the code, as that is against course policy). I also have a career fair and some SQL statements I need to do for a project of mine so that my partner and I can continue, so tomorrow will be a lot of work! I also have a hackathon thursday and friday, so it's unlikely i'll be able to resume until after. 

As far as the course goes, week 3 is split into a few big parts and my notes will reflect that. The first part is this one. The next is Image Pyramids. Then there is a lab (multipart) and the first PROJECT of the course. Now things are ramping up! I'll be spending a lot of time on those this week instead of writing notes, so bear with me if these temporarily become kind of rough. 

## Image Convolution and Edge Detection Part 2
- In this week we will be learning about OBJECT RECOGNITION
- This will build on what we did before but cover a lot of new ground (esp in the theory!) 
- Up until now, we found edge pixels. (and a bunch of other relevant info) 
- instead of maximum surpession , we want to compute the next edge point (so there is a lot of math behind that). This is edge linking! We check that the gradient is big enough, and link the edge
- Edge Linking: **Hysteresis**: this allows us to adaptively change the edge threshold 
	- 	use a high threshold to start edges, and a low threshold to continue them (essentially tracing them). 
	- 	essentially, if we know something is an edge make it easier for points around it to be edges. This detects more edges (even sometimes ones we don't want...) 
- 	 review the 5 step canny edge detection from week two's notes! Thats the key here. The details we have here are parts of that 

I got a 66% on this quiz :( (2 out of 3). I missed a question that I cannot describe due to the course honor policy but lets just say I learnt my lesson and that to anyone taking the course pay close attention to the videos when studying. 



## Video 3.2: full matlab example of canny edge detection 

- we first read the images into matlab, and converted it to grayscale. Then we make everything doubles 
- we then set a low threashold and high threshold and created a gaussian filter definition 
- after that, we filtered for horizontal and vertical direction derivitives (Ix and Iy from week two) (derivative filters shown below 
	- dx=[1 -1] 
	- dy=[1; -1] 
- then we convolved image with gaussian (smoothing) on both the x direction and y direction derivative images
- then we convolve the image with the derivative of the gaussian to get the final Ix and Iy 
- we then add those two images to get the gradient image. Then we take the magnitude of the gradient and convert the colors to get a rough edge detection image. 
- we also made a (suppppper colorful) gradient angle map (used for detecting edge orientation) 
- we then do local non maximum supression by looking in the region and comparing stuff to our thresholds. Edge hysterisis happens now! This is some fancy edge detection. We computer more edges w this. 
- Yellow is edges, blue is nothing. It's as if we traced it, which is super cool 
- in the future we can fine tune it to pickup some edges we missed (below threshold). We might change scale of filter or do other things. Now it's a reasoning issue not a math thing! 



Ok, its past midnight here and I have to wake up early tmr so I will leave the next hour worth of videos to another day (it's funny, I already finished the quiz for this section so i was debating watching them, but they are cool so i'll probably just skim them as review. I'm under time pressure so I need to focus on the core ideas and getting the most weeks completed by August 15! I don't think I'll be able to (or want to) handle this on top of 16 credit hours in college
