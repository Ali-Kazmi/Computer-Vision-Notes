# Image Pyramids



##Video 3.7
- represent images as pyramids

  - goal: extract features (such as edges)

  - Also has redundancy reductions

- level k: smallest (1 pixel): 1x1

- as we decrease the level, the image is bigger (level k-2 is bigger than level k) 

  - it could also be thought of as the same sized image but with progressively lower resolution as levels increase 
  - note: if we shrink the size of the image proportionally to the shrinking, our eyes play a trick on us and fill in the detail into the image. When we keep them the same size, we see it is rly the resolution decreasing! (ew this feels like psych again) 

- Also known as: 

  - gaussian pyramid

  - mip map

  - note: this leads in to the state of the art methods in deep learning, and we will see similar things in wavelt transforms (but I haven't got there yet sooo idk)


- To create a smaller and smaller image: shrink the image in half each level by throwing every other pixel away. (In this process, we lose more than just structure or info)
- if we keep the image the same size, its as if we were losing part of the picture. We call this sampling! (for good practice, sample often and wisely. For bad sampling… ew)

  - just a random sampling is not a good idea when sparsely sampling (seems obvious, but its 4: 46 am when i'm typing this at the end of a hackathon, so bear with me possibly existing reader.)! Bad luck plays a role… 

- We can do it by convolving with a gaussian filter before sampling! That way the image is smoothed and there are less intense changes. With less intense changes, the sampling has better luck. 
- filter size should double for each 1/2 size reduction! 
# Video 3.7 
##Image Reduction 
- based on a paper from 1983 (oof) 
- we will construct gaussian pyramids to do this 
- taking it from level 0 to level 1 is a reduction. We basically try to remove some information while keepign the context of the pixel. We use weighted averages (within neighboorhoods) here! (Similar to convolution, but its not). We look at the pixels two pixels left and two pixels right and take a weighted average. 
- Two steps: 
	1) smooth it (gaussian) 
	2) reduce it (using convolution like thing) 
-  i'll spare these notes the mathematics and details lol (formulas are annoying to type). The general idea is it is a convolution process again (think double summations). But instead of using g(i-m,j-n) we use g2(2*(i-m)),2*(j-n)) for the inside. The rest is similar to a normal convolution! 
- the weights we use are arbitrary (that paper used some specific ones, but it doesn't matter) 
- the weight we uses changes the shape of the distribution. when a=0.4, we are approximating a gaussian (the bump shape) 
- higher a (a=0.6) values are spiker distributions. Lower (a=0.3) are smoother with a less high bump 
- Which is better for image analysis????
- 	usually, we want a=0.6 (and all the other formulas they displayed) 

## Image Expansion 
- starting with level two, we can go to level one (level decreases). 
- We could just copy the pixels- but that would not be good. So instead we do a similar thing to reduction, and take a weighed average. 
- i'll spare these notes the mathematics and details lol (formulas are annoying to type). The general idea is it is a convolution process again (think double summations). But instead of using g(i-m,j-n) we use g2((i-m)/2),(j-n)/2)) for the inside. The rest is similar to a normal convolution! We need to multiply it by a constant though to make it bright enough.
- It generates a blurrier version of the og pic from the half size one. 

At this point, I just started the quiz on image pyramids even though I didn't study laplacian pyramids yet. I got all 4 of the gaussian pyramid questions right :). I can return for the laplacian pyramids after the next videos (which i'm actually doing now, but breaking into two notes to keep the github organized)



