# Week 4: Feature Detection- Gabor 



- we want filters and using them to select frequency (similar to the goal of fourier transforms!)
- in images, we have signals. Images have fourier domains. 
- we will convolve with a mask to eliminate certain frequencies 
- the sinc function does this (sin(x)/x)
- we can draw box functions that eliminate certain frequencies. 
- frequency selectivity is inversely proportional to location sensitivity (THE UNCERTAINTY PRINCIPLE OF SIGNAL PROCESSING)
- we can alleviate the uncertainty principle by replacing our rectangular boxes with the gaussian! (but a sampled one) [we skip proof]
- we make the filter by making two copies of the gaussian (using a cosine to modulate and a comb function of dirac impulses to choose where we want the copy)
  - we do this mathematically too, but im gonna skip that (not essential for this course, the ideas are what matter)
  - we get a modulated gaussian that looks kinda weird. Hard to explain w words, search up a pic
  - the modulated cosine filters the frequency. It's not phase independent :( 
  - so we need quadrature! The real component and the imaginary component each squared add up to one. 
- The Gabor Function! It's a whole math thing. but it is useful! 
- from gabor filter we get a real part and an imaginary part. Both of these depend on the frequency. 
  - the magnitude only depends on the frq matters! This is phase independent 
  - this helps when we have edge signals and ridge signals  and we want response to be the same 
- then he went to two dimensional gabor function, and its a whole mess of math… im not even gonna write it. 

I got a 100% on the gabor quiz (8/8, which was a lot of questions compared to the other quizzes in the class)!!!! Wow this felt kinda easy, I really get the concepts now. At first I was struggling, but I think this stuff is kinda cool. 

