# Image-Processing-1
 Image Processing and Image Smoothing

## Execute Code
python GUI_ui.py

## Running Code
![image](https://github.com/Study-boy-dot/Image_Processing_1/assets/80616480/c1aaf3fd-a548-4606-8b03-299a1425fe80)  

## Image Processing
1. **Color Seperation** - Extract 3 channels of the image BGR to 3 separated channels and 	show the result images
2. **Color Transformation** - Transform image to grayscale image
   * Image1 : Perceptually weighted formula: I1 = 0.299 R + 0.587 G + 0.114 B
   * Image2 : Average weighted formula: I2 = (R+G+B)/3
3. **Color Detection** - Filter green & white part in image
   * Convert Image from BGR to HSV format
   * Generate green & white mask
   ```
   lower_green = np.array([40,50,20])
   upper_green = np.array([80,255,255])
   green_mask = cv2.inRange(hsv_img, lower_green, upper_green)

   lower_white = np.array([0,0,200])
   upper_white = np.array([180,20,255])
   white_mask = cv2.inRange(hsv_img, lower_white, upper_white)
   ```
   * Bitwise and green mask and image
   ```
   fil_green_img = cv2.bitwise_and(image, image, mask = green_mask)
   fil_white_img = cv2.bitwise_and(image, image, mask = white_mask)
   ```
4. **Blending** -
  * Combine two images have been loaded
  * Using trackbar changes the weight of images

## Image Smoothing
1. **Gaussian Blur** - Apply gaussian blur to image
2. **Bilateral Blur** - Apply bilateral blur to image (sigmaColor=90, sigmaSpace=90)
3. **Median Blur** - Apply median blur to image
