<h1 align="left">Trash Sorting</h1>
<p align="left">--- Semantic Segmentation of Multi/Single-object Images with Auto Data Annotation</p>


<h2 align="left"><a href="https://www.biendata.xyz/competition/haihua_wastesorting_task2/">Data Source</a></p>
<p>characteristics: 4000 multiobject images, 1000000 single object images. 204 unique categories</p>

<h2 align="left">Prerequisite</p>
<p>install all required packages as defined in <a href="https://github.com/mdhmz1/Auto-Annotate">Auto Annotation</a>, <a href="https://github.com/RizwanMunawar/yolov7-segmentation">Yolo-v7 for Segmentation</a></p>
<p>install  <a href="https://github.com/wkentaro/labelme">labelme</a><pre>cd labelme-main</pre><pre>pip install .</pre></p>

<h2 align="left">Methods</p>

<p>Step 1: use <a href="https://app.roboflow.com">roboflow</a>, a online data annotation tool to manually annotation 200-250 multi-object images. To get better result, use build-in data augmentation tool.</p>
<p>Step 2: train <a href="https://github.com/mdhmz1/Auto-Annotate">Auto Annotation</a> to fit the manually labeled data. <pre>python3 customTrain.py train --dataset=YourDatasetDir</pre></p>
<p>Step 3: Use <a href="https://github.com/mdhmz1/Auto-Annotate">Auto Annotation</a> to annotate data. <pre>python3 annotate.py annotateCustom --image_directory=DatasetDirMissingLabel --label=CustomLabel --weights=XXX.h5 --displayMaskedImages=False</pre></p>
<p>Step 4: Clean the data. Use the modified labelme to delete annotation files with obvious errors or fix it.</p>
<p>Step 5: With the new data, repeat Step 2-4 until you get satisfactory segmentation results.</p>
<p>Step 5.5: Download Pretrained Model <a href="https://drive.google.com/file/d/19EvKk3qSsPFSM2g1x6drpsTI2_PtJxB5/view?usp=sharing">here</a>.</p>
<p>Step 6: Run data format conversion script in haihua_data_format_conversion.ipynb, which also automatically assign a classification label to each object according to ground truth label provided in Haihua dataset.</p>
<p>Step 6.1: Optionally, you are encouraged to manually assign a classification label using the provided labelme. Labels for some objects are missing in Haihua dataset for unknown reason</p>
<p>Step 8: Train your yolo-v7-segmentation model</p>

<h2 align="left">Results</p>
<p align="center"><a href="https://github.com/mdhmz1/Auto-Annotate#mdhmz1"><img src="https://github.com/mdhmz1/Auto-Annotate/blob/main/asset/logos/auto-annotate-logo-transparent.png" alt="Auto-Annotate Logo" height="240"></a></p>
