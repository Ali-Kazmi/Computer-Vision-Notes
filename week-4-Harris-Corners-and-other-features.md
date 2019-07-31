# Week 4 Harris Corners and other features

Ok, theres 3 pretty long videos but it's all on this stuff so i'm gonna put it here

We want features for applications such as: 

- matching two images (and then stitching two images)
- panorama's 
- AR 
- 3d models
- visual odometry (ROBOT PATHS) 
- video tracking 



A good feature: 

- can still get matched when the image is deformed (geometrically- shifts, photometrically- light/color/blurring changes, or intra-class changes like different models of cars)
- Should still be distinctive (so that its low storage and computes reasonably) (don't match everything lol)

Next: 

- detector: outputs location (and possibly scale, orientation, and if it's undergone deformations (like affine for ex.))
- descriptor: outputs a vector describing the neighborhood (ex: sift) (ex2: histogram)



Geometric Deformations: equivariance- a feature must be equivariant to deformations and warping (ex: if we can find the head of a cat in one pic, we should be able to find the head of a cat when the image is rotated and scaled)

- equivariance is commutative (we could detect then warp OR warp then detect)



Geometric deformations: invariance

- invariant- the descriptor remains the same after warping (it's a predictable change)
- if the feature is equivariant, then invariance can be achielved with normalization 





## Harris Corner

- now we're at the good stuff: one of the earliest features (proposed in 1988)
- basic idea: we want features detected where when we move them around they have maximum change across the edge and minimal change along the edge (a corner!)
  - we want a feature in place so that when we move it, the content moves the most
- he did a full slide of mathematics (expressed it as variation of intensity, expressed as a weighted sum of squared distances for a shift around a fixed point) (uses taylor expansion!)
- we essentially are looking at gradient with respect to x and gradient with respect to y. If both are high, we have a corner! But thats not enough- what if the image is rotated? So we add math that basically looks for eigenvalues and eigenvectors and shifts the image
  - we also add an autocorrelation matrix, in order to capture variation of gradients within a local neighboorhodd
- 





- R=det(A)-k*trace(A)=lambda1*lamda2-k*(lambada1+labda 2)
  - excsue my horrible spelling but i dont want to go back lol 
- if lambda 1<lamda 2, edge (same for if 2>1)
- if they are both large, corner
- if they are both small, nothing 

This is an equivarient feature! 

I got a 100% (6/6) on this sections quiz :) 

Also saw a video on youtube where this was used to detect edges on a chessboard. 











For small deformations, harris corners are good. 

But for big deformations, there is a paper in 2001 that improves on this. MSER: maximally stable extremal regions 

- THIS DETECTS BLOBS 
- we normalize the blods to make it easier to visualize (16x16 pixels)

The basic idea is to look at the intensity image as a f(x,y)

- imagine taking this 3d surface and filling it with water, measuring the volume. When this hits the threshold so that filling it more or less doesn't change the volume much, its done. 

1) computer connected binary regions

2) computer area a(i) at each threshold value i 

3) analyse for each potential region to determine the ones that persist with similar values OVER MULTIPLE THRESHOLDS 



This is useful for matching pictures. 



One more feature: The histogram of gradients (useful for detecting pedestrians, TESLA am i rite)

I already passed the test on this one so i'm gonna just watch and not take notes (this will come back in the labs tho)





VLFeat Library in matlab: lets you try out a bunch of features and try em! Everything we talked about and more. 

He recommended a paper: "A comparison of Affine Region Detectors". I am gonna take notes on it at some point then put it into papers. This is so cool, i'm reading research papers! :)

