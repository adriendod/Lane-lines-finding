# **Finding Lane Lines on the Road** 

## Writeup Template

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then used the canny method to detect gradiants.
I then masked the image and did a hough transorm.

In order to draw a single line on the left and right lanes, I first tried to average the slopes and interesct of the lines but it gave bad result on the line where it was not a continuious lines. Some very small lines were messing with the method.

So i finally tried to fit the points with the polyfit method of numpy, it gaves better result after fine tuning and cleaning up the detection.

I included images of the pipeline in the jupyter notebook directly.



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there is no line detected at all or detecting a curve. It would also not work in a city environnement where turns are sharpest and car are blocking the view.





### 3. Suggest possible improvements to your pipeline

It's pretty shaky right now, I would need to find a way to smooth it out. Also, I didnt find better parameters for the Canny, so i do not know if there is a way to do it better.