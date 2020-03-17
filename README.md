# FisheyeDistanceNet: Self-Supervised Scale-Aware Distance Estimation using Monocular Fisheye Camera for Autonomous Driving

**Varun Ravi Kumar**, Sandesh Athni Hiremath, Markus Bach, Stefan Milz, Christian Witt, Clément Pinard, Senthil Yogamani and Patrick Mäder

## [Accepted to ICRA 2020](https://arxiv.org/abs/1910.04076)

## Abstract
 Fisheye cameras are commonly used in applications like autonomous driving and surveillance to provide a large field of view (> 180◦). However, they come at the cost of strong non-linear distortions which require more complex algorithms. In this paper, we explore Euclidean distance estimation on fisheye cameras for automotive scenes. Obtaining accurate and dense depth supervision is difficult in practice, but self-supervised learning approaches show promising results and could potentially overcome the problem. We present a novel self-supervised scale-aware framework for learning Euclidean distance and ego-motion from raw monocular fisheye videos without applying rectification. While it is possible to perform piece-wise linear approximation of fisheye projection surface and apply standard rectilinear models, it has its own set of issues like resampling distortion and discontinuities in transition regions. To encourage further research in this area, we will release our dataset as part of the WoodScape project. We further evaluated the proposed algorithm on the KITTI dataset and obtained state-of-the-art results comparable to other self-supervised monocular methods. Qualitative results on an unseen fisheye video demonstrate impressive performance.

## Method
![Selection_137](https://user-images.githubusercontent.com/21110541/76306079-928d4580-62c6-11ea-8c3d-ff74cfb68db9.png)

The first row represents our ego masks as described in Section Masking Static Pixels and Ego Mask, <img src="svgs/37c38070df3426163447c76d233d0215.svg?sanitize=true invert_in_darkmode" align=middle width=59.604105pt height=22.46574pt/>, <img src="svgs/e3677cb6bb8960d818e0b9e9890e7711.svg?sanitize=true invert_in_darkmode" align=middle width=59.42145000000001pt height=22.46574pt/> indicate which pixel coordinates are valid when constructing <img src="svgs/965ad5bb9b3aed20e6c528948c7e3749.svg?sanitize=true invert_in_darkmode" align=middle width=47.08935pt height=31.14176999999998pt/> from <img src="svgs/278db88976f9ee7348b4fa6384f5364a.svg?sanitize=true invert_in_darkmode" align=middle width=29.018550000000005pt height=22.46574pt/> and <img src="svgs/eb31eb64abeba5e8c8397cd44e56b2bf.svg?sanitize=true invert_in_darkmode" align=middle width=46.906695pt height=31.14176999999998pt/> from <img src="svgs/1fa090c919706a5742f79edaca8bdb26.svg?sanitize=true invert_in_darkmode" align=middle width=28.835895pt height=22.46574pt/> respectively. The second row indicates the masking of static pixels computed after 2 epochs, where black pixels are filtered from the photometric loss (i.e. <img src="svgs/61ea779bfc8b3d237aad81b6c425be84.svg?sanitize=true invert_in_darkmode" align=middle width=40.958775pt height=21.18732pt/>). It prevents dynamic objects at similar speed as the ego car and low texture regions from contaminating the loss. The masks are computed for forward and backward sequences from the input sequence <img src="svgs/e257acd1ccbe7fcb654708f1a866bfe9.svg?sanitize=true invert_in_darkmode" align=middle width=11.027445000000004pt height=22.46574pt/> and reconstructed images using Eq. 11 in our paper as described in Section Masking Static Pixels and Ego Mask. The third row represents the distance estimates corresponding to their input frames. Finally, the vehicle's odometry data is used to resolve the scale factor issue.

[**[Full paper]**](https://arxiv.org/abs/1910.04076) [**[YouTube]**](https://www.youtube.com/watch?v=Sgq1WzoOmXg)

## Demo
[![](https://user-images.githubusercontent.com/21110541/76318392-ebb4a380-62dd-11ea-8ee9-d9cb0945b285.png)](https://www.youtube.com/watch?v=Sgq1WzoOmXg "")

## Quantitaive Results
![Selection_138](https://user-images.githubusercontent.com/21110541/76316370-c96d5680-62da-11ea-942f-30cf2462f3ec.png)

## Citation
Please use the following citation when referencing our work:
```
@article{kumar2019fisheyedistancenet,
  title={FisheyeDistanceNet: Self-Supervised Scale-Aware Distance Estimation using Monocular Fisheye Camera for Autonomous Driving},
  author={Kumar, Varun Ravi and Hiremath, Sandesh Athni and Milz, Stefan and Witt, Christian and Pinnard, Clement and Yogamani, Senthil and Mader, Patrick},
  journal={arXiv preprint arXiv:1910.04076},
  year={2019}
}
```
