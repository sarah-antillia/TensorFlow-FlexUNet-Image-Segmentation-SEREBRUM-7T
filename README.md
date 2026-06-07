<h2>TensorFlow-FlexUNet-Image-Segmentation-SEREBRUM-7T (2026/06/07)</h2>

Sarah T. Arai<br>
Software Laboratory antillia.com<br>
<br>
This is the first experiment of Image Segmentation for <b>SEREBRUM-7T</b>,
 based on our 
TensorFlowFlexUNet (TensorFlow Flexible UNet Image Segmentation Model for Multiclass) 
and a 512x512 pixels PNG 
<a href="https://drive.google.com/file/d/1ovwPweFUWeG1mEiGuzuMG_9nkQo6BJrS/view?usp=sharing">
Augmented-SEREBRUM-7T-ImageMask-Dataset.zip
</a> with colorized masks (CC0), 
which was derived by us from <br><br> 
<a href="https://openneuro.org/datasets/ds003642/versions/1.1.0">
<b>
CEREBRUM-7T: Fast and Fully-volumetric Brain Segmentation of 7 Tesla MR Volume
</b>
</a>
<br>
<hr>
<b>Acutual Image Segmentation for  SEREBRUM-7T Images of 512x512 pixels</b><br>
As shown below, the inferred masks predicted by our segmentation model trained on the 
PNG dataset appear similar to the ground truth masks.<br><br>
<a href="#color-class-mapping-table">SEREBRUM-7T: class-color mapping table</a>
<br>
<table>
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/1002_90.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/1002_90.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/1002_90.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/1003_71.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/1003_71.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/1003_71.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/deformed_alpha_1300_sigmoid_8_1003_63.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/deformed_alpha_1300_sigmoid_8_1003_63.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/deformed_alpha_1300_sigmoid_8_1003_63.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<h3>1. Dataset Citation</h3>
The dataset used here was derived from <br><br> 
<a href="https://openneuro.org/datasets/ds003642/versions/1.1.0">
<b>
CEREBRUM-7T: Fast and Fully-volumetric Brain Segmentation of 7 Tesla MR Volume
</b>
</a>
<br><br>
The following explanation was taken from the above web site.<br><br>
Visit the <a href="https://rocknroll87q.github.io/cerebrum7t/">project website</a> for more.<br><br>
The dataset is composed by 3 subjects, scanned at the Imaging Centre of Excellence (ICE) at the Queen 
Elizabeth University Hospital, Glasgow (UK). <br>
The full database consists of 142 out-of-the-scanner volumes obtained with a MP2RAGE sequence at 0.63 mm3 
isotropic resolution, using a 7-Tesla MRI scanner with 32-channel head coil. 
These data serve as testing dataset for the paper:
<br><br>
Svanera, M., Benini, S., Bontempi, D., & Muckli, L. (2020).<br> 
CEREBRUM-7T: fast and fully-volumetric brain segmentation of out-of-the-scanner 7T MR volumes.<br> 
bioRxiv.<br><br>
For every subject, two folders are provided, containing:<br><br>
anat/<br>
<ul>
<li>INV1</li>
<li>INV2</li>
<li>UNI_Images (T1w)</li>
</ul>
derivatives<br>
<ul>
<li>manual annotations of 8 regions of widely interest in neuroscience
early visual cortex (EVC) high-level visual areas (HVC) motor 
cortex (MCX) cerebellum (CER) hippocampus (HIP) early auditory cortex (EAC) brainstem (BST) 
basal ganglia (BGA)</li>
<li>automatic segmentation by FreeSurfer (v6 and v7)</li>
<li>automatic segmentation by Fracasso16</li>
<li>automatic segmentation by our method (CEREBRUM7T) with probability maps (CEREBRUM7T_probMap)</li>
<li>automatic segmentation by nighres</li>
<li>labels used for training our method</li>
</ul>
<br>
<b>Citation</b><br>
Michele Svanera and Lars Muckli (2021). <br>
CEREBRUM-7T: Fast and Fully-volumetric Brain Segmentation of 7 Tesla MR Volumes. <br>
OpenNeuro. [Dataset] doi: 10.18112/openneuro.ds003642.v1.1.0
<br><br>
<b>License</b><br>
CC0
<br><br>
<h3>
2 SEREBRUM-7T ImageMask Dataset
</h3>
<h4>2.1 Download ImageMask Dataset</h4>
 If you would like to train this SEREBRUM-7T Segmentation model by yourself,
 please download the dataset from the google drive 
<a href="https://drive.google.com/file/d/1ovwPweFUWeG1mEiGuzuMG_9nkQo6BJrS/view?usp=sharing">
Augmented-SEREBRUM-7T-ImageMask-Dataset.zip
</a> (CC0), 
which was derived by us from <br><br> , 
expand the downloaded dataset, and put it under <b>./dataset</b> folder to be:
<pre>
./dataset
└─SEREBRUM-7T
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
        ├─images
        └─masks
</pre>
<br>
<b>SEREBRUM-7T Statistics</b><br>
<img src ="./projects/TensorFlowFlexUNet/SEREBRUM-7T/SEREBRUM-7T_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images of train and valid datasets is large enough to use for a training set of our segmentation model.
<br>
<br>
<h4>2.2 ImageMask Dataset Derivation</h4>
The folder structure of <b>synapse dataset</b> is the following.<br>
<pre>
./SEREBRUM-7T
  ├─derivatives
  │   ├─sub-025
  │   │    └─sub-025_ses-003_training_labels.nii.gz
.. 
  │   └─sub-075
  │         └─sub-075_ses-003_training_labels.nii.gz
...
  └─images_dir
       ├─sub-025
       │    └─ses-003
       │         └─anat
                       └─sub-045_ses-002_T1w.nii.gz
...
       └─sub-075
             └─ses-001
                  └─anat
.                      └─sub-075_ses-003_T1w.nii.gz
</pre>
<b>Step 1</b><br>
We used a simple Python script and the following color-class-mapping table to generatea a 512x512 pixels PNG master dataset 
with colorized masks from all pairs of <b>*_T1w.nii.gz</b> file under <b>images_dir</b> folder and 
their corresponding <b>*_training_labels.nii.gz</b> file under <b>derivatives</b> folder.<br><br>
<a id="color-class-mapping-table"><b>SEREBRUM-7T color class mapping table</b></a>
<br> 
<table border=1 style='border-collapse:collapse;' cellpadding='5'>
<tr><th>Indexed Color</th><th>Color</th><th>RGB</th><th>Class</th></tr>
<tr><td>0</td><td with='80' height='auto'><img src='./color_class_mapping/Background.png' widith='40' height='25'></td><td>(0, 0, 0)</td><td>Background</td></tr>
<tr><td>1</td><td with='80' height='auto'><img src='./color_class_mapping/Early Visual Cortex (EVC).png' widith='40' height='25'></td><td>(255, 0, 0)</td><td>Early Visual Cortex (EVC)</td></tr>
<tr><td>2</td><td with='80' height='auto'><img src='./color_class_mapping/High-level Visual Areas (HVC).png' widith='40' height='25'></td><td>(0, 255, 0)</td><td>High-level Visual Areas (HVC)</td></tr>
<tr><td>3</td><td with='80' height='auto'><img src='./color_class_mapping/Motor Cortex (MCX).png' widith='40' height='25'></td><td>(0, 0, 255)</td><td>Motor Cortex (MCX)</td></tr>
<tr><td>4</td><td with='80' height='auto'><img src='./color_class_mapping/Cerebellum (CER).png' widith='40' height='25'></td><td>(255, 255, 0)</td><td>Cerebellum (CER)</td></tr>
<tr><td>5</td><td with='80' height='auto'><img src='./color_class_mapping/Hippocampus (HIP).png' widith='40' height='25'></td><td>(0, 255, 255)</td><td>Hippocampus (HIP)</td></tr>
<tr><td>6</td><td with='80' height='auto'><img src='./color_class_mapping/Early Auditory Cortex (EAC).png' widith='40' height='25'></td><td>(255, 0, 255)</td><td>Early Auditory Cortex (EAC)</td></tr>
<tr><td>7</td><td with='80' height='auto'><img src='./color_class_mapping/Brainstem (BST).png' widith='40' height='25'></td><td>(128, 128, 0)</td><td>Brainstem (BST)</td></tr>
<tr><td>8</td><td with='80' height='auto'><img src='./color_class_mapping/Basal Ganglia (BGA).png' widith='40' height='25'></td><td>(0, 128, 128)</td><td>Basal Ganglia (BGA)</td></tr>
</table>
<br>
For simplicity, we excluded all empty black label slices and their corresponding image slices to generate the PNG master, 
because they were irrelevant to training our segmentation model.
<br><br>
<b>Step 2</b><br>
We generated our augmented dataset from the PNG master by using the following image deformation and distortion tools.<br>
<a href="https://github.com/sarah-antillia/Image-Deformation-Tool">Image-Deformation-Tool</a><br>
<a href="https://github.com/sarah-antillia/Image-Distortion-Tool">Image-Distortion-Tool</a> <br>
<br>
<h4>2.3 Image and Mask samples</h4>
<b>Train sample images</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train sample masks</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/train_masks_sample.png" width="1024" height="auto">
<br>
<br>
<h3>
3 Train TensorFlowFlexUNet Model
</h3>
 We trained SEREBRUM-7T TensorFlowFlexUNet Model by using the following
<a href="./projects/TensorFlowFlexUNet/SEREBRUM-7T/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to ./projects/TensorFlowFlexUNet/SEREBRUM-7T and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
, which simply runs the following command.<br>
<pre>
>python ../../../src/TensorFlowFlexUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>

<b>Model parameters</b><br>
Defined a small <b>base_filters = 16 </b> and large <b>base_kernels = (11,11)</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet.py</a> 
and a large <b>num_layers = 8</b> (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
;You may specify your own UNet class derived from our TensorFlowFlexModel
model         = "TensorFlowFlexUNet"
generator     =  False
image_width    = 512
image_height   = 512
image_channels = 3
num_classes    = 9
base_filters   = 16
base_kernels   = (11,11)
num_layers     = 8
dropout_rate   = 0.05
dilation       = (1,1)
</pre>
<b>Learning rate</b><br>
Defined a very small learning rate.  
<pre>
[model]
learning_rate  = 0.00007
</pre>
<b>Loss and metrics functions</b><br>
Specified "categorical_crossentropy" and <a href="./src/dice_coef_multiclass.py">"dice_coef_multiclass"</a>.<br>
<pre>
[model]
loss           = "categorical_crossentropy"
metrics        = ["dice_coef_multiclass"]
</pre>
<b>Dataset class</b><br>
Specifed <a href="./src/ImageCategorizedMaskDataset.py">ImageCategorizedMaskDataset</a> class.<br>
<pre>
[dataset]
class_name    = "ImageCategorizedMaskDataset"
</pre>
<br>
<b>Learning rate reducer callback</b><br>
Enabled learing_rate_reducer callback, and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.5
reducer_patience   = 4
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with patience parameter.
<pre>
[train]
patience      = 10
</pre>

<b>RGB Color map</b><br>
rgb color map dict for SEREBRUM-7T 1+8 classes.<br>
<pre>
[mask]
mask_datatyoe    = "categorized"
mask_file_format = ".png"
; SEREBRUM-7T 1+8 classes
;       
rgb_map = {(0,0,0):0, (255,0,0,):1, (0,255,0):2, (0,0,255):3, (255, 255, 0):4, \
          (0,255,255):5, (255,0,255):6, (128,128,0):7, (0,128,128):8}
                       
  </pre>

<b>Epoch change inference callback</b><br>
Enabled <a href="./src/EpochChangeInfereuncer.py">epoch_change_infer callback</a></b>.<br>
<pre>
[train]
epoch_change_infer       = True
epoch_change_infer_dir   =  "./epoch_change_infer"
num_infer_images         = 6
</pre>

By using this callback, on every epoch_change, the inference procedure can be called
 for 6 images in <b>mini_test</b> folder. This will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> <br> 

<b>Epoch_change_inference output at starting (epoch 1,2,3)</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/epoch_change_infer_at_start.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at middlepoint (epoch 23,24,25)</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/epoch_change_infer_at_middlepoint.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at ending (epoch 48,49,50)</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/epoch_change_infer_at_end.png" width="1024" height="auto"><br>
<br>
In this experiment, the training process was terminated at epoch 50.<br><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/train_console_output_at_epoch50.png" width="1024" height="auto"><br>
<br>

<a href="./projects/TensorFlowFlexUNet/SEREBRUM-7T/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/eval/train_metrics.png" width="520" height="auto"><br>

<br>
<a href="./projects/TensorFlowFlexUNet/SEREBRUM-7T/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/eval/train_losses.png" width="520" height="auto"><br>
<br>
<h3>
4 Evaluation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/SEREBRUM-7T</b> folder,<br>
and run the following bat file to evaluate TensorFlowFlexUNet model for SEREBRUM-7T.<br>
<pre>
./2.evaluate.bat
</pre>
This bat file simply runs the following command.
<pre>
python ../../../src/TensorFlowFlexUNetEvaluator.py ./train_eval_infer.config
</pre>

Evaluation console output:<br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/evaluate_console_output_at_epoch50.png" width="1024" height="auto">
<br><br>

<a href="./projects/TensorFlowFlexUNet/SEREBRUM-7T/evaluation.csv">evaluation.csv</a><br>
The loss (categorical_crossentropy) to this SEREBRUM-7T/test was not low, and dice_coef_multiclass not high as shown below.
<br>
<pre>
categorical_crossentropy,0.0986
dice_coef_multiclass,0.9446
</pre>
<br>

<h3>
5 Inference
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/SEREBRUM-7T</b> folder<br>
,and run the following bat file to infer segmentation regions for images by the Trained-TensorFlowFlexUNet model for SEREBRUM-7T.<br>
<pre>
>./3.infer.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetInferencer.py ./train_eval_infer.config
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/mini_test_masks.png" width="1024" height="auto"><br>

<hr>
<b>Inferred test masks</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks for  SEREBRUM-7T Images of 512x512 pixels</b><br>
As shown below, the inferred masks predicted by our segmentation model trained on the 
PNG dataset appear similar to the ground truth masks.<br><br>
<a href="#color-class-mapping-table">SEREBRUM-7T: class-color mapping table</a>
<table>
<tr>
<th>Image</th>
<th>Mask (ground_truth)</th>
<th>Inferred-mask</th>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/1001_22.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/1001_22.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/1001_22.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/1002_90.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/1002_90.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/1002_90.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/deformed_alpha_1300_sigmoid_7_1001_63.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/deformed_alpha_1300_sigmoid_7_1001_63.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/deformed_alpha_1300_sigmoid_7_1001_63.png" width="320" height="auto"></td>
</tr>


<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/deformed_alpha_1300_sigmoid_7_1002_58.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/deformed_alpha_1300_sigmoid_7_1002_58.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/deformed_alpha_1300_sigmoid_7_1002_58.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/deformed_alpha_1300_sigmoid_8_1003_63.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/deformed_alpha_1300_sigmoid_8_1003_63.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/deformed_alpha_1300_sigmoid_8_1003_63.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/images/deformed_alpha_1300_sigmoid_8_1003_108.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test/masks/deformed_alpha_1300_sigmoid_8_1003_108.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_output/deformed_alpha_1300_sigmoid_8_1003_108.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>

<h3>
6 3D Volume Segmentation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/SEREBRUM-7T</b> folder<br>
,and run the following bat file to infer images segmentation for 2D slices of 3D volume NIfTI files
 by the Trained-TensorFlowFlexUNet model for SEREBRUM-7T.<br>
<pre>
>./5.infer3d.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNet3DInferencer.py ./train_eval_infer.config
</pre>
<b>infer3d section </b> in <a href="./projects/TensorFlowFlexUNet/SEREBRUM-7T/train_eval_infer.config">
train_eval_infer.config
<a></b>
<pre>
[infer3d] 
;Specify an images_dir which contains NIfTI or NPY files
images_dir    = "./mini_test_3d/images/"
output_dir    = "./mini_test_3d_output/"
slice_shape_order = "hwd"
slice_normalize = True
slice_resize   = (512,512)
;Specify a cv2.rotation code as a string.
slice_rotation = "cv2.ROTATE_90_CLOCKWISE" 
</pre>
<hr>
<b>Acutual Image Segmentation for 2D Slices of a SEREBRUM-7T NIfTI</b><br>
Some Slices, Inferred Masks and Mask overlays for a 3D volume <b>sub-045_ses-002_T1w.nii.gz</b> file in <b>images_dir/sub-045</b> folder.
 folder.<br>
<br>
<a href="#color-class-mapping-table">SEREBRUM-7T: class-color mapping table</a>
<br>
<table>
<tr>
<th>Image</th>
<th>Inferred-mask</th>
<th>Mask overlay</th>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/slices/10037.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/masks/10037.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/overlays/10037.png" width="320" height="auto"></td>
</tr>

<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/slices/10049.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/masks/10049.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/overlays/10049.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/slices/10061.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/masks/10061.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/overlays/10061.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/slices/10073.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/masks/10073.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/overlays/10073.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/slices/10085.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/masks/10085.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/overlays/10085.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/slices/10097.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/masks/10097.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/mini_test_3d_output/sub-045_ses-002_T1w.nii.gz/overlays/10097.png" width="320" height="auto"></td>
</tr>

</table>
<hr>
<br>
<h3>
7 MaskOverlay Video of 3D Volume Segmentation
</h3>
Please move to <b>./projects/TensorFlowFlexUNet/SEREBRUM-7T</b> folder, and run the following bat file 
to generate <b>overlays.mp4</b> or <b>overlay.gif</b> for MaskOverlays of 3D Volume Segmentation. <br>
<pre>
>./6.video3d.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/MaskOverlayVideoGenerator.py ./train_eval_infer.config
</pre>
<br>
<b>infer3d section </b> in <a href="./projects/TensorFlowFlexUNet/SEREBRUM-7T/train_eval_infer.config">
train_eval_infer.config
<a></b>
<pre>
[infer3d] 
mask_overlay  = True
;Specify ".mp4" or ".gif".
;video_fileformat  = ".mp4"
video_fileformat  = ".gif"
</pre>
<br>
<b>overlays.gif</b><br>
<img src="./projects/TensorFlowFlexUNet/SEREBRUM-7T/video_3d/overlays.gif">
<br>
<br>
<h3>
References
</h3>
<b>1. CEREBRUM-7T: Fast and Fully Volumetric Brain Segmentation of 7 Tesla MR Volumes</b><br>
Michele Svanera, Sergio Benini, Dennis Bontempi, Lars Muckli <br>
<a href="https://pmc.ncbi.nlm.nih.gov/articles/PMC8559470/">https://pmc.ncbi.nlm.nih.gov/articles/PMC8559470/</a>
<br><br>
<b>2. CEREBRUM 7T</b><br>
<b>Fast and Fully-volumetric Brain Segmentation of 7 Tesla MR Volumes</b><br>
rocknroll87q<br>
<a href="https://rocknroll87q.github.io/cerebrum7t/">https://rocknroll87q.github.io/cerebrum7t/</a>
<br><br>
<b>3. TensorFlow-FlexUNet-Image-Segmentation-Model</b><br>
Toshiyuki Arai<br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model
</a>

