# Description of QuickFind mask data

QuickFind is a fast segmentation and object detection algorithm using only depth maps. Depth maps are images captured from depth sensors like Kinect. The idea is in the future depth sensors will be common so such an algorithm will be useful. This project was created during my PhD. The associated research paper was presented at PerCom Workshops 2016.

The data contains amended ground truth of the RGB-D Scenes dataset used in the QuickFind paper. The ground truth in the original RGB-D scenes dataset had many errors so I manually traced out the location of each object. Credit for RGB-D Scenes goes to Lai et al. Please visit their [site](https://rgbd-dataset.cs.washington.edu/dataset.html) and credit them if you use my amended data in conjunction with their RGB-D Scenes dataset.

This is the dataset for QuickFind.

If you use this work please cite our paper.

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

The code, data and paper can be downloaded from the following page.

```
https://hzhongresearch.github.io/
```


### Licence
Copyright 2016 HENRY ZHONG. The data is released under Creative Commons Attribution 4.0 International Licence. See LICENCE.txt for details.

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
