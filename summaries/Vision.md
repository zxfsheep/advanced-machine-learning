* [R-CNN](https://arxiv.org/pdf/1311.2524.pdf): Using prior RoI (region of interest) proposer, run CNN on each proposed region.

* [Fast R-CNN](https://arxiv.org/abs/1504.08083): First run a CNN on the entire picture, and then use prior RoI (region of interest) proposer on the resulted feature map.

* [Faster R-CNN](https://arxiv.org/abs/1506.01497): Instead of using an external RoI proposer, run a parallel branch network on top of shared CNN. It slides a fixed size window, and propose region based on a fixed set of anchors (rectangles of different scales and ratios).

  On top of these models, there are heads doing object classification and also bounding box regression, so the cost function is multi-part.

* [Fully Convolutional Networks](https://arxiv.org/pdf/1411.4038.pdf): For semantic segmentation with dense output. This NN has only convolutional layers, which instead of outputing a single prediction, outputs a pixelwise prediction. The output can be very coarse, which can be then upsampled by transposed convolution (deconvolution), and learned as well. The NN can reuse the convolutional part of classification NN such as VGGnet.

* [Mask R-CNN](https://arxiv.org/abs/1703.06870): Compared to Faster R-CNN, also put a FCN along side the previous heads, which is pixel to pixel, and generates a binary mask for instance segmentation.

* [YOLO](https://pjreddie.com/media/files/papers/YOLOv3.pdf): You only look once, which divides picture into a grid, and for each cell implements bounding box regression, objection detection and objection classification, and combine these together. The drawback is difficulty to capture a group of small objects. The improved version borrows techniques from models above I believe.

