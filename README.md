# CS181-Fall26-Notebook #1
## Image Filtering: cross-correlation, convolution, and whitening transformation

<b>Due</b>: Monday, September 7th, 2026

## How this is going to work: 

I've provided some starter code for you. Before you go any further, click on the `notebook1_convolving_gaussian_filter_starter.ipynb` and `notebook1_whiteing_starter.ipynb` links in the repository, and then, at the top of the notebook, you will see a button that says `Open in Colab`. Click on this and it will open the starter code in Google Colaboratory.

## The Images
For this notebook, you will need the following two images:
- **Image#1**: [this link](https://github.com/alimoorreza/CS181-Fall26-Notebook-1/blob/main/data/da_vinci_lowres.png). *Use this for Task#1*
- **Image#2**: [this link](https://github.com/alimoorreza/CS181-Fall26-Notebook-1/blob/main/data/first_photograph.png). *Use this for Task#2*

 
First things first: upload the images to your Google Drive and then mount your Drive to the notebook. I aim to help everyone get familiar with the programming environment and comfortable working with pixel values in images. There will be two tasks: you'll perform various per-pixel transformations on images and observe the results.
# **Task#2**: Whitening Transformation
You will be adjusting the contrast of the image. Your goal is to transform the image so that the resulting image has a zero mean and unit variance. Denote the image as $I(.)$ which is a 2D array of pixel values. Its width and height are $N$ and $M$ pixels respectively. Also $I(x,y)$ denotes the pixel value at 2D location $(x,y)$.

## **Step 1:** 
You can compute the mean and variance of the gray-scale image $I(.)$ as follows:

<!--$\mu$ = $\frac{\sum_{x=1}^{N}\sum_{y=1}^{M}I(x,y)}{N \times M}$
\sigma^{2} = \frac{\sum_{x=1}^{N}\sum_{y=1}^{M}(I(x,y)-\mu)^2}{N*M}-->
![mean and variance equations](https://github.com/alimoorreza/CS181-Fall26-Notebook-1/blob/main/etc/whitening_eq1.png)

## **Step 2:** 
Now, you can transform each pixel value separately using the above two computed statistics $\mu$ (mean) and $\sigma$ (standard deviation) as follows:
    <!--I^{'}(x,y) = \frac{I(x,y)-\mu}{\sigma}-->
    
![whitening transformation](https://github.com/alimoorreza/CS181-Fall26-Notebook-1/blob/main/etc/whitening_eq2.png)


Apply this *Whitening Transformation* on the provided input image to see how it affects. The following figures show the effect of applying *Whitening Transformation* on the first-ever photograph -- **Image#1**: [this link](https://github.com/alimoorreza/CS181-Fall26-Notebook-1/blob/main/data/first_photograph.png). The result should something like below:

![Result task#1](https://github.com/alimoorreza/CS181-Fall26-Notebook-1/blob/main/etc/task1_result.png)


## :white_check_mark: Grading: 
I will update the following rubric with your grade after you have completed the assignment.

### Rubric:
> *This assignment is worth 5 points.*

>

| Exercise #  | Points Awarded (out of 5)  | Notes |
| --------- | ------------------- | --------- |
| 1:  convolution with Gaussian filter                      |    -/2.5    |            |
| 3:  whitening transformation         |    -/2.5    |            |
| <b>Total                             |    -/5      |     </b>   |
