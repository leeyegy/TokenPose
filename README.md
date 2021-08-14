# Introduction
Human pose estimation deeply relies on **visual clues** and **constraint clues between parts** to locate keypoints. Most existing CNN-based methods do well in visual representation, however, lacking in the ability to explicitly learn the constraint relationships between keypoints. In this paper, we propose a novel approach based on Token representation for human Pose estimation (TokenPose). 
![image](https://user-images.githubusercontent.com/35657511/129438301-6f0bb355-70cb-4b3f-8ca6-ee6935c5376f.png)

The contributions of this work are summarized as follows:
- We propose to use tokens to represent each keypoint entity. In this way, **visual cue learning** and **constraint cue learning** are explicitly incorporated into a unified framework.

- Both **hybrid** and **pure Transformer-based** architectures are explored in this work. To the best of our knowledge, our proposed TokenPose-T is the first pure Transformer-based model for 2D human pose estimation.

- We conduct experiments over two widely-used benchmark datasets: COCO keypoint detection dataset and MPII Human Pose dataset. TokenPose achieves competitive state-of-the-art performance with much fewer parameters and computation cost compared with existing CNN-based counterparts.

> For more details see [TokenPose: Learning Keypoint Tokens for Human Pose Estimation](https://arxiv.org/pdf/2104.03516.pdf) by Yanjie Li, Shoukui Zhang, Zhicheng Wang, Sen Yang, Wankou Yang, Shu-Tao Xia, Erjin Zhou. ICCV 2021.

# Quick use
## 1. Dependencies installation & data preparation
Please refer to [THIS](https://github.com/leoxiaobin/deep-high-resolution-net.pytorch) to prepare the environment step by step.

## 2. Trainging
### Training on COCO train2017 dataset 
```
python tools/train.py \
    --cfg experiments/coco/tokenpose/tokenpose_L_D24_256_192_patch43_dim192_depth24_heads12.yaml\
```
### Training on MPII dataset 
```
python tools/train.py \
    --cfg experiments/mpii/tokenpose/tokenpose_l_D6_256x256_patch44_dim192_depth6.yaml\
```
## 3. Testing
### Testing on COCO val2017 dataset using TRAINED models
```
python tools/test.py \
    --cfg experiments/coco/tokenpose/tokenpose_L_D24_256_192_patch43_dim192_depth24_heads12.yaml\
    TEST.MODEL_FILE _PATH_TO_CHECKPOINT_ \
    TEST.USE_GT_BBOX False
```

### Testing on MPII dataset using TRAINED models
```
python tools/test.py \
    --cfg experiments/mpii/tokenpose/tokenpose_l_D6_256x256_patch44_dim192_depth6.yaml\
    TEST.MODEL_FILE _PATH_TO_CHECKPOINT_ 
```

# Citations
If you use our code or models in your research, please give it a star or cite with:
```
@inproceedings{li2021tokenpose,
  title={TokenPose: Learning Keypoint Tokens for Human Pose Estimation},
  author={Yanjie Li and Shoukui Zhang and Zhicheng Wang and Sen Yang and Wankou Yang and Shu-Tao Xia and Erjin Zhou},
  booktitle={IEEE/CVF International Conference on Computer Vision (ICCV)},
  year={2021}
}
```
# Acknowledgement
Thanks for the open-source:
> [HRNet](https://github.com/leoxiaobin/deep-high-resolution-net.pytorch/), [timm](https://github.com/rwightman/pytorch-image-models), [DarkPose](https://github.com/ilovepose/DarkPose), [DETR](https://github.com/facebookresearch/detr)
