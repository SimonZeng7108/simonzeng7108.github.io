---
# the default layout is 'page'
icon: fas fa-info-circle
order: 4
---

![Desktop View](/images/portfolio/simon_conference.jpeg){: width="800" height="800" .w-50 .right}
I am a Postdoc Research Associate at [*Visual Information Lab (VIL)*](https://vilab.blogs.bristol.ac.uk/), Bristol, supervised by [*Aaron Zhang*](https://fan-aaron-zhang.github.io/). My project is funded by Prime Video Amazon on an exciting deep video quality assessment project.
At the same time, I am a PhD research student at [*Machine Learning and Computer Vision Research Group (MaVi)*](https://uob-mavi.github.io/people/) and [*Visual Information Lab (VIL)*](https://vilab.blogs.bristol.ac.uk/),
University of Bristol, where I am supervised by [*Dr Alberto Gambaruto*](https://research-information.bris.ac.uk/en/persons/alberto-m-gambaruto) and [*Dr Tilo Burghardt*](http://people.cs.bris.ac.uk/~burghard/). We work on the swallowing project [CTAR-SwiFt](https://www.dev.fundingawards.nihr.ac.uk/award/PB-PG-1217-20005). <br/>
My work focuses on Medical Image Processing using Deep Learning and Computational Fluid Dynamics using Meshless method/Physics-Informed Neural Network.
<br/>
<br/>
<br/>
<br/>
<br/>

---
## News
---
- 03/02/2025: I am happy to start a new role as Postdoc Research Associate at **Bristol**, funded by Prime Video, **Amazon**.
- 17/06/2024: I began a six-month internship as an Applied Scientist at **Amazon**, in Studio AI Lab, Prime Video & Amazon MGM Studios, London.
- 18/04/2024: My 3-Minute Thesis "How AI helps doctors diagnose swallowing difficulty" was selected as a **Semi-Finalist** in the 3MT competition at the University of Bristol.
- 03/03/2024: Our “RBF-PINN” paper was **accepted** by the International Conference on Learning Representations (ICLR), AI4DifferentialEquations in Science workshop.
- 19/02/2024: Our research proposal "AI aided diagnosis of Dysphagia in Elderly Population" was chosen as one of the **Finalists** in the TakeAIM competition by the Smith Institute.

---
## Projects
---
![Desktop View](/images/portfolio/vos.gif){: width="150" height="150" .w-10 .left}
[**Multi-Teacher Knowledge Distillation For Efficient Object Segmentation - 2025**](https://arxiv.org/abs/2501.18474) <br/>
Simon Zeng, Gavin Cheung, Valentin Gourmet, Kurt Cutajar, Hanting Xie, Massimo Camplani, Niall Twomey, Richard Tomsett, Jas Kandola <br/>
[*Under Review*]<br/>
Segment Anything Model 2 (SAM2) has demonstrated state-of-
the-art performance in image/video object segmentation across
many domains, but its large encoder makes it challenging for
resource-constrained devices or real-time applications. One
solution to this problem is to carry out knowledge distillation
from the bulky encoder to a lightweight encoder, but this can
result in degraded performance. In this work, we investigate
multi-teacher distillation to mitigate performance degradation
for distilled segmentation models. Using several foundation
teacher models, our multi-teacher distilled models achieve
3.2 times speedup during end-to-end inference compared to
SAM2 while achieving the best results of 74.4 and 71.1 (72.1
and 69.6 for single-teacher distillation) mIoU on the COCO
and LVIS image segmentation datasets, as well as showing
competitive results on video segmentation. Our results show
that multi-teacher distillation offers a powerful solution for
efficient image/video segmentation, while also maintaining
compelling performance.



---
![Desktop View](/images/portfolio/full_seg.gif){: width="150" height="150" .w-10 .left}
[**Tuning Vision Foundation Model via Test-Time Prompt-Guided Training for VFSS Segmentations - 2025**](https://arxiv.org/abs/2501.18474) <br/>
Chengxi Zeng, Tilo Burghardt, Alberto Gambaruto <br/>
[[*arXiv*](https://arxiv.org/abs/2501.18474)]<br/>
Vision foundation models have demonstrated exceptional generalization capabilities in segmentation tasks for both generic and specialized images. However, a performance gap persists between foundation models and task-specific, specialized models. Fine-tuning foundation models on downstream datasets is often necessary to bridge this gap. Unfortunately, obtaining fully annotated ground truth for downstream datasets is both challenging and costly. To address this limitation, we propose a novel test-time training paradigm that enhances the performance of foundation models on downstream datasets without requiring full annotations. Specifically, our method employs simple point prompts to guide a test-time semi-self-supervised training task. The model learns by resolving the ambiguity of the point prompt through various augmentations. This approach directly tackles challenges in the medical imaging field, where acquiring annotations is both time-intensive and expensive. We conducted extensive experiments on our new Videofluoroscopy dataset (VFSS-5k) for the instance segmentation task, achieving an average Dice coefficient of 0.868 across 12 anatomies with a single model.


---
![Desktop View](/images/portfolio/Yorkshiretea.gif){: width="150" height="150" .w-10 .left}
[**Tea Classification - 2024**](https://brewtone.ai/) <br/>
Chengxi Zeng, Ted Littledale, Yorkshire Tea (Bettys & Taylors of Harrogate) <br/>
[[*WEB APP*](https://brewtone.ai/)]<br/>
We developed a tea classification Web App for Yorkshire Tea (Bettys & Taylors of Harrogate). The app is able to classify tea colors from any cups. My main responsibility was to develop image processing code for the tea element and extract the main tone by applying various edge detection and outlier removal techniques. Additionally, I employed the segmentation foundation model [Segment Anything](https://segment-anything.com/)  on a small tea dataset I created. The model accurately segmented the tea element and was converted to an ONNX file that can be deployed to multiple platforms. Prior to UK national tea day, the app successfully attracted thousands of users in a few weeks.

---
![Desktop View](/images/portfolio/ns_fluid.gif){: width="150" height="150" .w-10 .left}
[**RBF-PINN: Non-Fourier Positional Embedding in Physics-Informed Neural Networks - 2024**](https://paperswithcode.com/paper/rbf-pinn-non-fourier-positional-embedding-in) <br/>
International Conference on Learning Representations (**ICLR 2024**) , AI4DifferentialEquations in Science Workshop, **Accepted**  <br/>
Chengxi Zeng, Tilo Burghardt, Alberto Gambaruto <br/>
[[*Github*](https://github.com/SimonZeng7108/RBF-PINN)] 
[[*arXiv*](https://arxiv.org/abs/2402.08367)]<br/>
While many recent Physics-Informed Neural Networks (PINNs) variants have had considerable success in solving Partial Differential Equations, the empirical benefits of feature mapping drawn from the broader Neural Representations research have been largely overlooked. We highlight the limitations of widely used Fourier-based feature mapping in certain situations and suggest the use of the conditionally positive definite Radial Basis Function. The empirical findings demonstrate the effectiveness of our approach across a variety of forward and inverse problem cases. Our method can be seamlessly integrated into coordinate-based input neural networks and contribute to the wider field of PINNs research.

---
![Desktop View](/images/portfolio/lorenz.gif){: width="200" height="200" .w-10 .left}
[**Training dynamics in Physics-Informed Neural Networks with feature mapping - 2024**](https://arxiv.org/abs/2402.06955) <br/>
Preprint, Under Review <br/>
Chengxi Zeng, Tilo Burghardt, Alberto Gambaruto <br/>
[[*Github*](https://github.com/SimonZeng7108/RBF-PINN)] 
[[*arXiv*](https://arxiv.org/abs/2402.06955)]<br/>
Physics-Informed Neural Networks (PINNs) have emerged as an iconic machine learning approach for solving Partial Differential Equations (PDEs). Although its variants have achieved significant progress, the empirical success of utilising feature mapping from the wider Implicit Neural Representations studies has been substantially neglected. We investigate the training dynamics of PINNs with a feature mapping layer via the limiting Conjugate Kernel and Neural Tangent Kernel, which sheds light on the convergence and generalisation of the model. We also show the inadequacy of commonly used Fourier-based feature mapping in some scenarios and propose the conditional positive definite Radial Basis Function as a better alternative. The empirical results reveal the efficacy of our method in diverse forward and inverse problem sets. This simple technique can be easily implemented in coordinate input networks and benefits the broad PINNs research.

---
![Desktop View](/images/portfolio/swin.gif){: width="150" height="150" .w-10 .left}
[**Video-SwinUNet: Spatio-Temporal deep learning framework for VFSS instance segmentation - 2023**](https://paperswithcode.com/paper/video-swinunet-spatio-temporal-deep-learning) <br/>
IEEE International Conference on Image Processing (**ICIP 2023**), **Accepted** <br/>
Chengxi Zeng, Xinyu Yang, David Smithard, Majid Mirmehdi, Alberto Gambaruto, Tilo Burghardt <br/>
[[*Github*](https://github.com/SimonZeng7108/Video-SwinUNet)] 
[[*arXiv*](https://arxiv.org/abs/2302.11325v1)]<br/>
This paper presents a deep learning framework for medical video segmentation. Our proposed framework explicitly extracts features from neighbouring frames across the temporal dimension and incorporates them with a novel temporal feature blender which then tokenises the high-level Spatio-temporal feature to a strong global feature encoder Swin Transformer. Our model outperforms other approaches by a significant margin and improves the segmentation benchmarks on the VFSS2022 dataset, achieving a dice coefficient of 0.8986/0.8186 for Part1/Part2 data. Our studies have also shown the efficacy of the temporal feature blending scheme and the transferability of the framework.

---
![Desktop View](/images/portfolio/arion.gif){: width="128" height="128" .w-10 .left}
[**Lithology Document Analysis - 2022**](https://www.cgg.com/sites/default/files/2022-02/2202_Lun_FB_ML%20Doc%20Extraction_art.pdf) <br/>
Chengxi Zeng, Arion.ai, CGG <br/>
We developed a deep learning pipeline that processes long lithology tracks to multi-page images, a fast bounding box detection algorithm is employed and calibrated. Segmentation models are used to extract the curves and hence the numerical data is restored. The pipeline is tested on 1000+ documents and can process 100+ Page/Sec

---
![Desktop View](/images/portfolio/swallowing.gif){: width="128" height="128" .w-10 .left}
[**Video-TransUNet: Temporally Blended Vision Transformer for CT VFSS Instance Segmentation - 2022**](https://deepai.org/publication/video-transunet-temporally-blended-vision-transformer-for-ct-vfss-instance-segmentation) <br/>
SPIE International Conference on Machine Vision (**ICMV 2022**), **Accepted**, **[Best Oral Presentation](/images/portfolio/ICMV_2022.png)**<br/>
Chengxi Zeng, Xinyu Yang, Majid Mirmehdi, Alberto Gambaruto, Tilo Burghardt <br/>
[[*Github*](https://github.com/SimonZeng7108/Video-TransUNet)] 
[[*arXiv*](https://arxiv.org/abs/2208.08315)]<br/>
We propose Video-TransUNet, a deep architecture for instance segmentation in medical CT videos constructed by integrating temporal feature blending into the TransUNet deep learning framework. In particular, our approach amalgamates strong frame representation via a ResNet CNN backbone, multi-frame feature blending via a Temporal Context Module (TCM), non-local attention via a Vision Transformer, and reconstructive capabilities for multiple targets via a UNet-based convolutional-deconvolutional architecture with multiple heads.

---
![Desktop View](/images/portfolio/drone.gif){: width="128" height="128" .w-10 .left}
[**Portable AED Delivery Emergency Drone (Patented) - 2022**](https://english.cnipa.gov.cn/) <br/>
Chengxi Zeng, Yuhang Ming, Mengxun Bai, Ruobing Li <br/>
We are developing an Emergency drone that delivers medical kits and portable AED which would save lives in jammed cities and remote areas. This project collaborates with Hangzhou Municipal Health Commission and the drone will work with local Emergency Response Unit.

---
![Desktop View](/images/portfolio/haisaimu.gif){: width="128" height="128" .w-10 .left}
[**Elastic Transformation Detection - 2021**](http://www.haytham.com.cn/qichejilingbujian.html) <br/>
Chengxi Zeng, Haytham Technology Ltd <br/>
We utilised CNN and other image processing techniques to non-destructively detect Elastic Transformation on steel/composite materials due to repetitive work load in extreme environments.

---
![Desktop View](/images/portfolio/lake.gif){: width="128" height="80" .w-10 .left}
[**Solving Partial Differential Equations using Radial Basis Functions - 2021**](/images/portfolio/Solving Partial Differential Equations using Radial Basis Function.pdf) <br/>
Chengxi Zeng, Andreas Michael, Celia Tugores-Bonilla, Natasha Moore, Jules Boisser, Alberto Gambaruto <br/>
We discretise standard Partial Differential Equations(PDEs) using Radial Basis Functions, aiming to assess their performance compared to the analytical results and alternative discretisation methods.

---
![Desktop View](/images/portfolio/citycfd.gif){: width="128" height="150" .w-10 .left}
[**Pedestrian Level wind assessment with CFD simulation - 2019**](http://www.bristol.ac.uk/engineering/departments/mecheng/courses/projects/#6) <br/>
Chengxi Zeng, Alberto Gambaruto <br/>
We modelled Bristol city centre area and applied CFD simulation with focus on high wind speed area and presented the advantage of trees to mitigate wind using Porous Media approach.

---
<!-- ## Leadership
![Desktop View](/images/portfolio/bcda.jpg){: width="60" height="60" .w-10 .left}
<h4>Founder & Executive President - 2021</h4><br/>

![Desktop View](/images/portfolio/erdemy.jpg){: width="60" height="60" .w-10 .left}
<h4> Co-Founder & Chief Business Development Manager - 2020</h4><br/>

![Desktop View](/images/portfolio/cssauk.jpg){: width="60" height="60" .w-10 .left}
<h4>Assistant Vice President - 2019</h4><br/>

![Desktop View](/images/portfolio/cssab.png){: width="60" height="60" .w-10 .left}

<h4>President - 2018</h4><br/> -->




<br>
<script type='text/javascript' id='clustrmaps' src='//cdn.clustrmaps.com/map_v2.js?cl=ffffff&w=250&t=n&d=hnXPU8X96e7s6ubaWzFOcgTks4PbHzmsEzYnZoEMVuE'></script>