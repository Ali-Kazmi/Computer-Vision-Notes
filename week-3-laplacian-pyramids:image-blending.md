#Laplacian Pyramids 
Now that we have reduction and expansion, we want to make a laplacian pyramid from the gaussian pyramid. Video 3.8

- the goal is an image that 
- the laplacian approximates the second derivative (note: this is not from the video. I got confused, so I did some good old fashioned googling)
	-this stuff is useful for image compression, and is used in JPEG 
	
- laplacian pyramids make image reconstruction possible, This stuff will also be used to stitch images together later! Ok, now that i'm interested again im gonna go back to the video 


- we take the og image and then compute the difference between the smootehd image. The dif between an image and the smoothed image is the laplacian image! 
- We create a sequence of em. We construct a difference of the image and the image after an expand operation (see the image pyramid notes). 
- The laplacian level L= gl-expand[gl+1]
(so the lowest level is level 1 of a laplacian pyramid) 


Now I realize what this is for: enhances the way we see shapes, crucial for object recognition! (they showed a cool example that helped us see!) 

#Constructing laplacian pyramids

Now we get to the gory details of what we got the idea behind above. Yay! After this is the quiz too, so stay tuned (if anyone ever reads this). 
- a laplacian pyramid is just a sequence of laplacian images 
- we smooth each pixel with a gaussian process then susbsample by a factor of 2. [and then there is more abt condensing and expanding, but im not writing down all the details] 
- We use the smoothed version because it is easier to reverse and extract the og gaussian image pyramid! We can now have lossless reconstruction! (wow this feels like ap csp again). 
- at the lowest level, a blurred version of the img at the lowest resolution is stored 



#image blending 
- if we have two separate pictures and want to put em together, we do image blending. 
- first, we make a 4 layer laplacian pyramid of the both images (LA, LB)
- then we make the background image of the second image on the second laplacian level 
- we make a mask (a gaussian pyramid) saying where we want img 1 on image 2. (we essentially remove whats on img 2 and replace it with img 1). This is different from just overlaying pictures! We are combining the edges with the edges of the second pic. we just set down edges. Then we do that for all the levels
	- At level 4 (the top) guassian pyramid and laplcaian pyr. are the same! 
- then we make a combined pyrtamid (using a fancy formula) 
- combined pyr(i,j)=mask(i,j)*LA(i,j)+(1-MASK(i,j))*LB(i,j) 
- to finish, we collapse the combined pyramid to get the final blended image 
- now the first pic is seamlessly on the second (shading, etc. is all handled!!! WOW) 
- they showed an example of an eye image on a hand that was cool, used in horror movies!!! This was a cool section. 
- I got a 100% (8/8) on this sections quiz :) I was rly into it, so I kinda saw it coming... the programming challenges are gonna be tough though so lets seeee 