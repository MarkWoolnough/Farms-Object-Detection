# Farms-Object-Detection
A repository to build a basic segmentation model in PowerAI Vision, train, deploy, test, auto label and build a new model to get better results

This repository contains materials to demonstrate PowerAI Vision Auto-ml to create a basic vision model to segment images with:
 * trees
 * buildings
 * tankers (silos)
 
Once deployed, the model can also simulate a drone inspection by using the video preview platform and the enclosed mp4 test file that shows aerial footage from a drone flying over a farm.  The model should do a basic job of detecting the above objects.

The next step is to upload some new files with tankers (silos) in - the base model does not detect these very well as illustrated by the initial mp4 test.  Once uploaded, the autolabel service can label these new images and they can then be augmented by an operator to complete and demonstrate time saving techniques for labelling in PowerAI Vision.

The final step is to train a new model with the data including autolabelled files, test the test images then test the mp4 again.  Whilst not perfect, it should show an improvement in performance.

Steps:
1.  In PowerAI Vision, navigate to the data tab and create a new dataset.
2.  Upload the zip file for the baseline model in "Baseline Model" repository folder.
3.  Launch a training job, select object detection and the Segmentation (Detectron) option.  Should take around 15 minutes to train.
4.  Deploy and Test the model.  Its pretty basic, so reports an accuracy of 16% initially.  This is probably due to the complexity of some of the objects like trees in clusters.
5.  Go to the Deployed Models Page and test the model with the supplied sample images in "Test Files for Model" repository folder.
6.  Launch the Video API endpoint and test with the videoplayback.mp4 file.  Upload and Detect.  If the model doesn't play back, download it and open it in a browser.  Chrome is ideal.  Review the playback.  See how Silos are labelled as buildings.
7.  Go back to the Data Sets page and go into your farms dataset.  Upload the new images for the next iteration from "Files to build new model" repository folder.
8.  Select the new images using the checkboxes and select the Auto Label function.
9.  Once the autolabel has finished, open up the new images and add any extra objects that were missed.  It did a fairly good job of picking up Silos (tankers) and trees, but add any that are missing using the Label Objects and polygons function.
10. Now train a new version of the model.  Object detection and Segmentation (Detectron) again.
11. Deploy and Test again with new images - you should see a slight improvement.
12. Go the API Video test and repeat the upload of the videplayback.mp4 file.  You should see an improvement in the quality of detection for Silos (tankers).

This illustrates the end to end process of building models and iterating to get better with autolabelling to save time and effort.

I have included two reference movies of the initial model object detection results and the improved model object detection for reference.

Hope you have fun!
Mark
