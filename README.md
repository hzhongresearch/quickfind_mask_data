# Description of QuickFind mask data

This data was used to test the QuickFind algorithm. An algorithm for fast segmentation and object detect for depth maps. Depth maps are typically produced by Kinect or similar depth sensors. This data is to be used in conjunction with the original RGB-D scenes dataset. This can be found at [link](https://rgbd-dataset.cs.washington.edu/dataset.html). Credit goes to Lai et al. for the original dataset. Please visit their site and credit their paper as well if you use their data along with my amended ground truth data.

The ground truth in the original RGB-D scenes dataset had many errors so I manually traced out the location of each object. For example in the RGB-D scenes datset there is an image called: table_small_2_67.png, depth map called: table_small_2_67_depth.png. There is a corresponding image called: table_small_2_67_mask.png in this dataset to show the location of all detectable objects.

QuickFind was created during my PhD. The research paper "Quickfind: Fast and contact-free object detection using a depth sensor" was presented at PerCom Workshops 2016. My research is in Ubiquitous Computing and Computer Vision. If you use this work please consider citing our paper.

```
@inproceedings{zhong2016quickfind,
  title={Quickfind: Fast and contact-free object detection using a depth sensor},
  author={Zhong, Henry and Kanhere, Salil S and Chou, Chun Tung},
  booktitle={Pervasive Computing and Communication Workshops (PerCom Workshops), 2016 IEEE International Conference on},
  pages={1--6},
  year={2016},
  organization={IEEE}
}
```

The code, data and paper can be downloaded at the following link.

```
https://hzhongresearch.github.io/
```


### License
Copyright 2016 HENRY ZHONG. The data is released under Creative Commons Attribution 3.0 Unported License. See LICENSE.CC-BY for details.

### Description of data
Each file is 24 bit, 3 channel PNG format. It is possible to read the data using C++ with OpenCV. 

```
Mat image = imread("table_small_2_67_mask.png", CV_LOAD_IMAGE_COLOR);
for (int a = 0; a < image.rows; ++a)
{
    for (int b = 0; b < image.cols; ++b)
    {
       Vec3b pixel = image.at<Vec3b>( a, b );
       uchar red = pixel[2];
       uchar green = pixel[1];
       uchar blue = pixel[0];
    }
}
```

The RGB values for each object class:

| Object class | Object instance | R   | G   | B   |
|:-------------|:----------------|:----|:----|:----|
| Bowl         | bowl_2          | 255 | 0   | 0   |
| Bowl         | bowl_3          | 255 | 255 | 0   |
| Bowl         | bowl_4          | 0   | 255 | 0   |
| Cap          | cap_1           | 0   | 255 | 255 |
| Cap          | cap_3           | 0   | 0   | 255 |
| Cap          | cap_4           | 255 | 0   | 255 |
| Cereal       | cereal_1        | 192 | 0   | 0   |
| Cereal       | cereal_2        | 192 | 192 | 0   |
| Cereal       | cereal_4        | 0   | 192 | 0   |
| Coffee       | coffee_mug_1    | 128 | 0   | 0   |
| Coffee       | coffee_mug_4    | 128 | 128 | 0   |
| Coffee       | coffee_mug_5    | 0   | 128 | 0   |
| Coffee       | coffee_mug_6    | 0   | 128 | 128 |
| Flashlight   | flashlight_1    | 64  | 0   | 0   |
| Flashlight   | flashlight_2    | 64  | 64  | 0   |
| Flashlight   | flashlight_3    | 0   | 64  | 0   |
| Flashlight   | flashlight_5    | 0   | 64  | 64  |
| Soda         | soda_can_1      | 0   | 0   | 192 |
| Soda         | soda_can_3      | 192 | 0   | 192 |
| Soda         | soda_can_4      | 64  | 64  | 64  |
| Soda         | soda_can_5      | 192 | 192 | 192 |
| Soda         | soda_can_6      | 128 | 128 | 128 |
