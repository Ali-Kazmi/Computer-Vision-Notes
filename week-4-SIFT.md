# Week 4: Feature detection: Sift

- goal: build a system that detects edges/features regardless of size (scale)
- the fourier transform of the gaussian derivative is a gaussian! 
- response maximum is when filter scale matches incoming scale 
- as sigma increases, the peaks at the edges weaken! (lower ampliturde)
- we need scale normalization 
  - scaling then convolving w scaled gaussian= applying gaussian then scaling (but this doesn't work with the first derivative)
  - we want a normalization of the first derivative! That way we can get an intrinsic image scale
- in the next video we're gonna use this to design scale invariant features 
  - note: I started the quiz here and got 5/5. Need to finish it after watching the next video. The notes for that are below (I kept em together because it's all SIFT). 



- the scale space is built using the 2d gaussian 

  - we can subsample it, like we did with the image pyramids

  

  - laplacian of gaussian: The Mexican Hat operator (looks like an upside down sombrero)
    - approximated by difference of two gaussians (when they have different sigma's)
    - detects BLOBS

- a sift keypoint: maximum in the 3x3x3 (x,y,sigma) region of a point 

- the descriptor is ROTATION INVARIENT AND SCALE INVARIANT (this is cool, this means we can detect things when its moving around between images)

- The descriptor is a grid of histogram of gradient orientations on a region normalized by scale and rotation 

## Applications of SIFT 

- SIFT allows image mergeing (and stitching when we apply it to multiple images)
- It also allows us to find locations! (ex: feed it an image and it will look thru similar images to find the matching feature, then find the locations)
- wow 



Got a 8/9 on this quiz (oof I missed one question because I thought it was the same as the question before it, but it wasn't; it said descriptor instead of detector…. OOPS my bad)

Total course progress: 16% 