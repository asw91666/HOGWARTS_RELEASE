# Datasets

## ARKitFace

You can download the ARKitFace dataset from the following link: [ARKitFace dataset](https://github.com/cbsropenproject/6dof_face).
Follow the instructions in the `Download Dataset` section on the linked page. 
You will be able to obtain both the dataset and the preprocessed files. 
We used the files downloaded from ARKitFace without any modifications.

To run our code, you need the flip index file for training. You can download this file from [here](https://drive.google.com/drive/folders/1Qdj62asVBpj-cGM2mnymD1bqNEBhf6RZ?usp=sharing).

Place the file in the following location: `dataset/ARKitFace/flip_index.npy`.

```
${ROOT}  
|-- dataset  
|   |-- 300W_LP
|   |-- BIWI
|   |-- ARKitFace
|   |   |-- ARKitFace_info_test
|   |   |-- ARKitFace_info_train
|   |   |-- ARKitFace_list
|   |   |-- ARKitFace_resources
|   |   |-- ARKitFace_image_test
|   |   |-- ARKitFace_image_train
|   |   |-- flip_index.npy
|-- ... 
|-- ... 
```


## BIWI

You can download the BIWI dataset from the following link: [BIWI](https://www.kaggle.com/datasets/kmader/biwi-kinect-head-pose-database).
To run our code, you need the file for the predicted bounding box. You can download this file from [here](https://drive.google.com/drive/folders/1Qdj62asVBpj-cGM2mnymD1bqNEBhf6RZ?usp=sharing).

Place the downloaded bounding box file in the following location: `dataset/BIWI/download_from_official_site/kinect_head_pose_db/hpdb/annot_mtcnn_fan.pkl`.

```
${ROOT}  
|-- dataset  
|   |-- ARKitFace
|   |-- 300W_LP
|   |-- BIWI
|   |   |-- download_from_official_site
|   |   |   |-- db_annotations
|   |   |   |-- head_pose_masks
|   |   |   |-- kinect_head_pose_db
|   |   |   |   |-- hpdb
|   |   |   |   |   |-- annot_mtcnn_fan.pkl
|   |   |   |   |   |-- 01
|   |   |   |   |   |-- 02
|   |   |   |   |   |-- 03
|   |   |   |   |   |-- ...
|   |   |   |   |   |-- ...
|-- ... 
|-- ... 

```

# Reference Alignment System (PR'26)

In addition to the data mentioned above, `arkit_biwi_align_matrix_250507.pkl` is required for a fair evaluation on BIWI of models trained on ARKitFace. 
For details, please refer to [TRGv2 (PR'26)](https://www.sciencedirect.com/science/article/pii/S0031320326005510) and its [Github repository](https://github.com/asw91666/TRGv2_PR26_Released). Place the downloaded file at `data/arkit_biwi_align_matrix_250507.pkl`.

# Pretrained weights
| Model        | Train Dataset | Link        |
| ------------ | ------------- | ----------- |
| r18_hogwarts | ARKitFace     | Coming Soon |


```
${ROOT}  
|-- checkpoint
|   |-- r18_hogwarts
|   |   |-- checkpoint-30/
|-- ... 
|-- ... 
```
