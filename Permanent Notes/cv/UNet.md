---
tags:
  - segmentation
  - ML
  - architecture
---
Q: Does **up-convolution** used in the paper correspond to `Upsample` used in Torch?
![[unet-architecture.png.png]]
Tips for Implementing:
- If implemented as done in the paper, the predicted segmentation map will have a different size than the ground truth segmentation map. There are several fixes:
	- *Preserve* the dimensions during convolution by padding.
	- Crop the GT image. This means segmentation will only predict for a *cropped* section of the image.
- Batch Normalization helps reduce variance
- I found LeakyReLU to be helpful.