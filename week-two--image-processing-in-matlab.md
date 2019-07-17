#Week Two: Image Processing in MATLAB


## Intro 
As some of you may recall from week 2's theory notes, I am moving along pretty fast in this course. For week two to be done, I not only need the theory (those were the last notes) but also the applications. So here i'll be taking notes on that 

## Updates 
So I moved my notes to markdown to make it easier to take. Hopefully i'll get used to the little techniques so that I can quickly take notes with only my keyboard during college (though I doubt it'll be as detailed as these computer vision ones). 

## Images in matlab
``` matlab
name=imread('filename.tif') 
```
The above function takes an image and stores it into the variable name as an array. 

Grayscale images are stored as matrices. 

To save an image (usually after processing) we will use 
```
imwrite(newName, 'newFileName.png');
```

Images with color have a third dimension, because each pixel has RGB values. 

## Working with Image Data
- pixels have intensity between 0 and 255 (8 bit) 
- the color is a third dimension, and R G B images have 3 color planes 
- to extract a single color plane (red): 
 ```
 Ired=I(:,:,1);   
 ```
  
  For green: 
  ```
 Igreen=I(:,:,2);   
  ```
- we can crop images with cropping functions in matlab (search it up if you want em) 
- we can crop all the red values to zero too: 
``` 
IcropnoRed=Icrop; 
IcropnoRed(:,:,1)=0; 
```

## Spatial Image Filtering 
- We want to enhance the image 
- spatial filtering is an image operation where we change each pixel by a function of the intensities of pixels in its neighborhoods (sound familiar? This is sliding a kernel/mask around the image. This is what we talked about in week 2's theory!) 
- in matlab, common filters are made already: 
```
fspecial('type', parameters)
```
Types that work for fspecial: (I know around 75% of these haha but the key idea is that they are all masks) 
- average (what it sounds like) 
- disk
- gaussian (used for smoothing) 
- laplacian (used to highlight discontinuities and edges)  
- log 
- motion 
- preswift
- sobel 


we use another command to actually USE the filter we made above:
```
imfilter(inputImage, filter)
```
By default, outside of the img is padded with 0's. But we can do other stuff around the edges (see old theory notes for options) 

Show the image with:
```
imshow(newImage)
```

What's also interesting is that we can sharpen images by subtracting images. This is really just matrix subtraction, but it gets cool effects. In matlab: 
```
sharpened=image-newImage; 
``` 
Nothing too complex yet, but this is foundational stuff for later. 

## Converting Image Data Types 
- used when we need to do math on the image but sometimes errors come from data types and automatic compressions 
- after we load in an image (see above) to put it into a form ready for computeation do the following (assuming we made an image I1) 
```
I2=im2double(I1) 
```
- That converted things to floating point doubles. They take more memory to store, but now we can do fancy math on em. Also everything was scaled down to be between 0 and 1. (previously 0 to 255). 
- we can convert it back to what we had before, but most matlab image processing stuff takes either data format so theres no point 