# 2019-Pixel-Privacy-Task

This task develops image enhancement technology that helps to protect user privacy. Specifically, it is dedicated to creating new approaches that invisibly change or visibly enhance images in such a way that it is no longer possible to automatically infer privacy-sensitive information.

This page contains information on participating in the task.

For more information contact Martha Larson (m.a.larson at tudelft.nl)

## Instructions
The 2019 edition of the task focuses on privacy-sensitive information that is related to scene categories.
A scene category can be understood to be the identity of the setting in which a photo was taken.
The task data is a subset of the Places365-Standard data set.
The task provides:
* a list of 60 privacy-sensitive categories chosen from the original 365 scene categories.
* a list of the Places365-Standard data set images to use as a *development set* to develop your approach(es).

To participate in the task, you must submit versions of the test images to which your protective transformation has been applied. The task organizers will then evaluate your transformation and return the results to you. Then, you write up your findings in a 2-page paper to submit to the MediaEval 2019 working notes proceedings. We are especially interested in identifying highly creative promising approaches, but also in negative results that provide information on what does not work.

## Updates for Pixel Privacy 2019
In this Pixel Privacy Task 2019, the same *development set* (MEPP18val) will be used again. For the test set, we use a subset of MEPP18test this year. This test set has in total 600 images. Due to the reason that wrongly classified images do not need to be enahnced again to achieve privacy protection, all of these 600 images can be properly classified by the attack model (i.e., ResNet50).

## Task schedule
* **Friday 20 September 2019:** Upload your images (see submission instructions below)
* Begin writing your 2-page working notes paper, see information at http://multimediaeval.org/files/2019workingnotes.html for format and instructions.
* **Monday 23 September 2019:** Results are returned to you
* Add the results to your working notes paper, and complete writing the discussion and outlook sections
* **Monday 30 September 2019:** Finalize your working notes paper and submit it to: https://easychair.org/conferences/?conf=mediaeval19
* **27-29 October 2019:** Join the MediaEval 2019 Workshop in France near Nice, information at http://multimediaeval.org/files/2019workshopregistration.html 

## Necessary resources
* The dataset (`MEPP18val`) used for the MediaEval 2019 Pixel Privacy task is a subset of the validation images from the Places365-Standard data set, which can be downloaded here: http://data.csail.mit.edu/places/places365/val_256.tar. The link for the of `MEPP18val` list can be found [here](https://github.com/multimediaeval/2018-Pixel-Privacy Task/blob/82b3352c75c3e3bba736fc837864bbead83138b1/MEPP18labels/MEPP18val.csv).
* `MEPP19test` is a subset of `MEPP18test` used last year, and all the selected images are ensured to be correctly classified by the attack model (ResNet50-places). There are in total 600 images, **around** 10 for each of the 60 privacy-sensitive scene categories. The list of images in test set can be found [here](https://github.com/multimediaeval/2019-Pixel-Privacy-Task/tree/master/MEPP19labels)
  * `MEPP19test_manual.csv`: A list of one image per category from the test set. If `MEPP19test.csv` is alphabetized, this is the first image in every category. Focus on these images if you are applying protective transformations by manually manipulating the images (instead of using an automatic filter).
* [ResNet50-places365](http://places2.csail.mit.edu/models_places365/resnet50_places365.pth.tar) (Pytorch) will be used as the attack model to evaluate the performance of protection. For image preprocessing, only normalization is applied without resizing and cropping. You can use this model to develop your protection approach.
* The overview paper is under work now, you can refer to it later on.

## How to submit
* Make sure that you have signed up to participate in the task and have returned your usage agreement: http://multimediaeval.org/files/usageagreement2019.html. Confirm with Martha Larson (m.a.larson at tudelft.nl) that you would like to participate in the task if you signed up but did not receive an email.
* You will then receive a Google docs folder in which to submit your runs. 
  * A "run" is a single image transformation algorithm, or type of image transformation, which you apply to the images in the test set.
  * For each run, please invent a unique run code that includes your team name (i.e., the team name is the one that you used to register). For example, `rteam_base`. 
  * When you carry out the run, append the unique run code to each image filename, e.g., `rteam_base_Places365_val_00014191.jpg`
  * Create a .zip file for each run that contains the transformed test set images. Use the unique run code as the .zip file filename. 
* You can submit maximally five runs. If you have more than five approaches, you need to decide which of them are most promising and submit only those. This helps you focus on quality rather than quantity (and to fit your entire description into a 2-page paper).

## Information on the privacy-sensitive scene categories
As stated above, the MediaEval 2019 Pixel Privacy task uses 60 privacy-sensitive scene categories.
These categories are a subset of the original 365 categories of the Places365-Standard data set, and can be found here
https://github.com/multimediaeval/2019-Pixel-Privacy-Task/blob/master/MEPP18senscats.txt

The format of this list reflects the format used in the original list of 365 categories, which is here: https://github.com/metalbubble/places_devkit/blob/master/categories_places365.txt and includes the original index numbers.

The 60 categories were chosen on the basis of a discussion among the task organizers, who considered which of the original 365 categories could be best considered to contain privacy-sensitive information. It was informed, in part, of what is considered to be sensitive data in many countries, cf. e.g., https://teachprivacy.com/sensitive-data-different-definitions-privacy-law/ and also by the original cybercasing use scenario cf. e.g., https://www.nytimes.com/2010/08/12/technology/personaltech/12basics.html 

The 60 privacy-sensitive scene categories are consistent with one or more of the following privacy criteria. 

* Places in the home.
* Places far away from the home (typical vacation places).
* Places typical for children.
* Places related to religion.
* Places related to people's health.
* Places related to alcohol consumption.
* Places in which people do not typically wear street clothes.
* Places related to people's living conditions/income.
* Places related to security.
* Places related to military.

This list is not intended to be the final word on the types of scene categories that can be considered privacy-sensitive, but instead is supposed to provide clear criteria for the Pixel Privacy 2019 task, and a good basis for future work.

## Motivation and larger objectives
The objective of the MediaEval Pixel Privacy task is to promote the innovation of protective technologies that make it safer to share social multimedia online. Here, we briefly sketch two motivations for the task.

First, recently, we are becoming better aware of how easy it is for social network data to be misappropriated (cf. https://www.theguardian.com/commentisfree/2018/mar/19/facebook-data-cambridge-analytica-privacy-breach) or how quickly companies and citizens can diverge in their idea of what constitutes appropriate use of social network data (cf. https://www.theguardian.com/technology/2017/may/01/facebook-advertising-data-insecure-teens)
It is clearly important to be able to trust social networks.
However, these examples underline that users *also* need technologies that they can apply locally before sharing images, so that it is not necessary to place their trust completely in the hands of social networks.

Second, as computer vision and artificial intelligence advances, it will be increasingly difficult for individual users to estimate the danger of sharing any particular image online.
Even if they do understand the capabilities of modern technology to infer information from their images, it is difficult to stay focused on this danger during the act of image sharing.
Specifically, when users take images to share online, they are focused on the specific subject matter that they have chosen for the image, and may not be paying attention to background detail.
It is exactly this background that can leak private information, for example, revealing that a user is traveling.
The aim of Pixel Privacy is to develop fun-to-use technologies, so that users protect their privacy in the act of enhancing their images, without having to think separately about privacy risks.
As users *dress up* their images, they are automatically contributing to their privacy without having to pay attention to background detail, or to understand the capabilities of artificial intelligence approaches to infer sensitive information about individuals using large quantities of data.
