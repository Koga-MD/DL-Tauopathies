# DL-Tauopathies
This repository contains all python codes used in our manuscript. The codes are provided as JupyterLab script files (.ipynb). There are 2 script files and 9 CSV files as follows:

<div>
<B>1. Training object detection model & Tau quantification & Generating random forest classfier & Hold-out validation study</B> <BR>
With this script, training data (JPG and TXT files) are used to train the YOLO v3 object detection model. After completing the training, the best weight is saved in "drive/" directory. Next, we uploaded a zip file that contains 360 images from 120 cases (RF-1 to RF-120), unzip the file, and applied the object detection model to these images. The quantitative tau lesion burden is obtained and saved in a CSV file.<BR>
The latter part of the script generates decision tree classifiers and random forest classifiers using quantitative tau lesion burden ascertained from the object detection models above. The CSV file generated above (FinalResult.csv) is used to generate these classifiers. For the validation study, we used CSV files that contains quantitative tau lesion buden (CP13 and AT8) of hold-out cases.<BR>
We run this code in the Google Colaboratory. Google Drive is used as a data storage. 
</div><BR>
<div>
<B>2. Data augmentation</B><BR>
With this script, a dataset is split into training and test datasets with a ratio of 4:1 (default). Training dataset can be applied to data augmentation by rotating at 90°, 180°, and 270°. Subsequently, augmented training data and test data are compressed as a zip file, which is uploaded to Google Drive. We run this code in the Jupyter Notebook. Please change the working directory (Line 2: task_name = os.path.join('PUT LOCAL PATH HERE')) when using this code.<BR>
After running the code, "data" folder will contain test dataset, and "train" folder will contain training dataset. "train.txt" will contain file names of original training dataset. "train2.txt" will contain file names of augmented training dataset. "test.txt" and "test2.txt" are the same files and will contain file names of test dataset.
</div><BR>
<div>
<B>3. CSV files</B><BR>  
CSV files for random forest will be downloaded from "Files" directory. After downloading, users put these files in their Google Drive "task1" directory.<BR>
</div><BR>
<div>
<B>4. Other files</B><BR>  
The image data (Data.zip and Test.zip) and tuned models (Model1.weights, Model2.weights, and Model3.weights) used in the paper are available from our Zenodo repository.
</div>
