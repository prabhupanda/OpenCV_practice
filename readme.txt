BaggageAI Computer Vision Asignment

First Step:

creating a function transform_mask(img,resize_factor,lowerlim,upperlim)

This function is used to achieve two targets:
1.Resizing the main image of the threat 
2.Create a mask of the resized image to be used in PIL.Image.Image.Paste() function

To create a mask I created a filter using cv.inRange() from openCV2 library,
that stores all values ranging between lowerlimit and upperlimit in a binary image.
Mask is then color-inverted with (255-mask) function.

The mask & threat image are again imported with PIL.Image.open() and then first rotated 45 degrees

The background, threat and mask are pasted with Image.Image.Paste() function which pastes the threat image as per the masking

**for restricting the image to be inside the boundaries, we input tuple of co-ordinates according to the size of background,
  near its centre by co-ordinates of the centre = (bakground.shape[1]//2,background.shape[0]//2)

To apply translucency effects , we use the Image.blend() function to superimpose the pasted image on the background image w/ 
suitable value of alpha generally ranging between (0.5-0.7) for the superimposed image.

  
