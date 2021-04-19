# Introduction
Human pose estimation deeply relies on **visual clues** and **anatomical constraints between parts** to locate keypoints. Most existing CNN-based methods do well in visual representation, however, lacking in the ability to explicitly learn the constraint relationships between keypoints. In this paper, we propose a novel approach based on Token representation for human Pose estimation (TokenPose). 

![image](https://user-images.githubusercontent.com/35657511/115193992-6b3ab600-a11f-11eb-8cfc-8f4e7185237a.png)

The contributions of this work are summarized as follows:
• We propose to use tokens to represent each keypoint entity. In this way, **visual cue learning** and **constraint cue learning** are explicitly incorporated into a unified framework.
• Both **hybrid** and **pure Transformer-based** architectures are explored in this work. To the best of our knowledge, our proposed TokenPose-T is the first pure Transformer-based model for 2D human pose estimation.
• We conduct experiments over two widely-used benchmark datasets: COCO keypoint detection dataset and MPII Human Pose dataset. TokenPose achieves competitive state-of-the-art performance with much fewer parameters and computation cost compared with existing CNN-based counterparts.

![image](https://user-images.githubusercontent.com/35657511/115194279-d2586a80-a11f-11eb-8c07-4b9f718da135.png)
