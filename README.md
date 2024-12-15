## Incremental Object Detection via Meta-Learning



## Installation and setup
- Install the Detectron2 library that is packages along with this code base. See [INSTALL.md](INSTALL.md).
- Download and extract Pascal VOC 2007 to `./datasets/VOC2007/`
- Use the starter script: `run.sh`

## Trained Models and Logs

| Setting | Year |  Achieved mAP  | Commands | Logs |
|:-------:|:----:|:--------------:|:--------:|:---------------:|
|  10+10  | 2024 |      67.3      |  [run.sh](https://github.com/JosephKJ/iOD/blob/main/run.sh#L22-L30)  |  sss   |

Download model weight : [Google Drive](https://drive.google.com/file/d/1LH7OY-uMifl2gwCFEgm6U5h_Xfh1nPcH/view?usp=sharing)


##### Configurations with which the above results were reproduced:
- Python version: 3.6.7
- PyTorch version: 1.3.0
- CUDA version: 11.0
- GPUs: 4 x NVIDIA GTX 1080-ti




## Acknowledgement
The code is build on top of Detectron2 library and Incremental Object Detection via Meta-Learning (TPAMI).

##### DOI 10.1109/TPAMI.2021.3124133

Early access on IEEE Xplore: [https://ieeexplore.ieee.org/document/9599446](https://ieeexplore.ieee.org/document/9599446)

arXiv paper: [https://arxiv.org/abs/2003.08798](https://arxiv.org/abs/2003.08798)


<div align="center">
  <img src="https://user-images.githubusercontent.com/4231550/138396577-bdef2d95-5f00-47c4-bf90-927d7231f090.png"/>
</div>

#### Abstract
In a real-world setting, object instances from new classes can be continuously encountered by object detectors. When existing object detectors are applied to such scenarios, their performance on old classes deteriorates significantly. A few efforts have been reported to address this limitation, all of which apply variants of knowledge distillation to avoid catastrophic forgetting. 

We note that although distillation helps to retain previous learning, it obstructs fast adaptability to new tasks, which is a critical requirement for incremental learning. In this pursuit, we propose a meta-learning approach that learns to reshape model gradients, such that information across incremental tasks is optimally shared. This ensures a seamless information transfer via a meta-learned gradient preconditioning that minimizes forgetting and maximizes knowledge transfer. In comparison to existing meta-learning methods, our approach is task-agnostic, allows incremental addition of new-classes and scales to high-capacity models for object detection. 

We evaluate our approach on a variety of incremental learning settings defined on PASCAL-VOC and MS COCO datasets, where our approach performs favourably well against state-of-the-art methods.

<p align="center" width="100%">
<img src="https://user-images.githubusercontent.com/4231550/145962389-75511c27-3d9f-4dd2-be93-934dcdf4d70c.jpg" width="800" />
</p>

<p align="center" width="80%">
<strong>Figure:</strong> Qualitative results of our incremental object detector trained in a 10+10 setting where the first task contain instances of <i>aeroplane, bicycle, bird, boat, bottle, bus, car, cat, chair and cow</i>, while the second task learns instance from <i>diningtable, dog, horse, motorbike, person, pottedplant, sheep, sofa, train and tvmonitor</i>. Our model is able to detect instances of both tasks alike, without forgetting.
</p>