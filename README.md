# DL-Tauopathies
<B>About this repository</B>  
<div>
This repository contains all python code used in our manuscript (Koga et al. <I>Under Revision</I>). The code is provided as JupyterLab script files (.ipynb). The image data (Data.zip and Test.zip), tuned models (Model1.weights, Model2.weights, and Model3.weights), and 9 CSV files used in the paper are available from our Zenodo repository (https://zenodo.org/record/5083997). Data.zip contains 2522 of each image and text file for training models. Test.zip contains 12 images from 4 patients, which are a part of the hold-out dataset images used in the paper.
</div><BR><BR>

<B>QuickStart Guide</B>
1. Prepare Google account and Google Drive.
2. Make the "task1" folder on your Google Drive.
3. Download our tuned models (e.g., Model1.weights), image datasets (Test.zip), and CSV files (e.g., RF-Model1.csv) from our repository on Zenodo (https://zenodo.org/record/5083997).　
  *As a starter, we recommend downloading 3 files as follows: <B>Model1.weights</B>, <B>Test.zip</B>, and <B>RF-Model1.csv</B>.
4. Upload these files to the "task1" folder on Google Drive.
5. Click 0_QuickStart.ipynb file on GitHub.
6. Click the "Open in Colab" tab.
7. Click Cell 1 to mount your Google Drive.
8. Click Cell 2 to download and setup the YOLOv3 model.
9. Click Cell 3 to copy files from your Google Drive "task1" folder. Image files are unzipped and renamed. Model 1 will be used as the default. If you want to use other models, edit Line 2 (Model1.weights will be replaced with Model2.weights or Model3.weights).
10. Click Cell 4 to start the analysis. It may take up to one hour to complete 12 images. 
11. Results are provided as a CSV file and saved in your Google Drive "task1" folder.
12. Click Cell 5 to analyze the results. Predicted diagnoses will be shown below the Cell. In this dataset, predicted diagnoses are CBD (Case 1), AD (Case 2), PSP (Case 3), and PiD (Case 4), respectively.
13. You can see analyzed images with bounding boxes at "/content/darknet/drive/result2"
  
<BR>
<B>Other files for our manuscript</B><BR>
<div>
<B>1. Training object detection model & Tau quantification & Generating random forest classfier & validation study</B> <BR>
With this script, training data (JPG and TXT files) are used to train the YOLO v3 object detection model. After completing the training, the best weight is saved in "drive/" directory. Next, we uploaded a zip file that contains 360 images from 120 cases (RF-1 to RF-120), unzip the file, and applied the object detection model to these images. The quantitative tau lesion burden is obtained and saved in a CSV file.<BR>
The latter part of the script generates decision tree classifiers and random forest classifiers using quantitative tau lesion burden ascertained from the object detection models above. The CSV file generated above (FinalResult.csv) is used to generate these classifiers. For the validation study, we used CSV files that contains quantitative tau lesion buden (CP13 and AT8) of hold-out cases.<BR>
We run this code in the Google Colaboratory. Google Drive is used as a data storage. 
</div><BR>
<div>
<B>2. Data augmentation</B><BR>
With this script, a dataset is split into training and test datasets with a ratio of 4:1 (default). Training dataset can be applied to data augmentation by rotating at 90°, 180°, and 270°. Subsequently, augmented training data and test data are compressed as a zip file, which is uploaded to Google Drive. We run this code in the Jupyter Notebook. Please change the working directory (Line 2: task_name = os.path.join('PUT LOCAL PATH HERE')) when using this code.<BR>
After running the code, "data" folder will contain test dataset, and "train" folder will contain training dataset. "train.txt" will contain file names of original training dataset. "train2.txt" will contain file names of augmented training dataset. "test.txt" and "test2.txt" are the same files and will contain file names of test dataset.
</div>
