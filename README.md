# **Finding Lane Lines on the Road** 


**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/yellowChangeTarmacChallenge.jpg  "challengeInput"
[image2]:./test_images_output/yellowChangeTarmacChallenge_gray.jpg "grayscale"
[image3]:./test_images_output/yellowChangeTarmacChallenge_cs.jpg "colorselection"

---

## Reflection

#### Step1: Display and Write images helper function
I defined two new helper functions for the exercise:
1. `display(imlist)` which displays the images on a given image list `imlist`. This will help during testing of each subsequent step of the pipeline applied to all input images. 
2. `write(imlist,output,path,imname_list,suffix)` which writes the images from the given `imlist` to the `output_path` by combining the given names from the `imname_list` with a predefined `suffix`.

#### Step2: Load and display test images
I read all the images from the given path and then use the helper function created above to display them. During the implementation of the exercise when I reached the last `challenge` video I had problems detecting the lanes. This was caused by: 
1. The different resolution compared to the rest of the photos and videos
2. Because of the challenges particular conditions (shades, tarmac difference, steepness of curves)

On my later iterations on the exercise, to have a feeling how my pipeline is handling the last video, I took also two screenshots from the `challenge` video during the testing phase. I tried to take two screenshots that represent the most tricky situations on detection.
As an example on the report I will use a frame taken by the challenge video:

![alt text][image1]

#### Step3: Lane line detection pipeline

#### 1. Grayscale color space

The images contain two different colors of lines **`white`** and **`yellow`**. In order to proceed to a color selection I decided initially to convert the images to grayscale color space suspecting that the **`yellow`** color will be leaning towards the **`white`** so I can extract afterwards by selecting only one color threshold.

![alt text][image2]

#### 2. Color selection

It seemed that also the `yellow` lines came closer to the `white` color, which I want to get from the image, I can try color selection. Using appropriate thresholds to extract only the lines.

![alt text][image3]

#### Evaluation of the result

t first glance the implication of this filtering is that on the *easy* images the result is good. But I had some trouble identifying the lanes on the *challenging* images. On my first exercise iteration I continued until the end and found out that using this color space and color selection can produce decent results on the first two videos.

The problem arouse when I tried to run my pipeline on the `challenge` video though. The pipeline was unable to identify a satifsying number of decent hough lines because the edges were a obscure. I realised that in order to make it work I had to do more than this.

#### Using HLS

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 




### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
