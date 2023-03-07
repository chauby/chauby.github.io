---
layout: post
title: Daily Paper (2023.3.1 - 2023.3.31)
categories: [Updating]
description: Some interesting papers
keywords: 
---

### [31_Learning to Retain while Acquiring: Combating Distribution-Shift in Adversarial Data-Free Knowledge Distillation](https://arxiv.org/pdf/2111.06377.pdf)

- This paper proposes the method called **Learning to Retain while Acquiring**. This method treats the task of Knowledge-Acquisition (learning from newly generated samples) and Knowledge-Retention (retaining knowledge on previously met samples) as meta-train and meta-test, respectively. The propose is to maintain student's performance while updating the generator in the training of Data-free Knowledge Distillation (DFKD). The student update strategies are shown below. It is obvious how the proposes strategy treats the knowledge-acquisition loss and knowledge-retention loss as meta-train and meta-test. The separate strategy is much more helpful for maintain the performance.

![Student Update Strategies](/images/DailyPaper/04/01.png "Student Update Strategies")

- The proposed DFKD is shown below. The structure is similar with the student update strategy shown above. This method may be considered as a kind of attacking strategy as mentioned in the paper because of the meta-train and meta-test. But this strategy can guarantee the performance of student network. This is a kind of trade-off.

![Framework of DFKD](/images/DailyPaper/04/00.png "Framework of DFKD")

### [32_GIVL: Improving Geographical Inclusively of Vision-Language Models with Pre-Training Methods](https://arxiv.org/abs/2301.01893)

- This paper proposes **Geographically Inclusive Vision-and-Language Pre-trained model (GIVL)** to eliminate the cultural difference existed in the culture spread. Besides, **Image-Knowledge Matching (IKM) and Image Edit Checking (IEC)** are designed to pre-train GIVL. IKM is used to learn the alignment between images and corresponding textual knowledge in Wikipedia. IEC is proposed to identify whether a visual concept in input image is replaced by another concept that is visually similar but lies in an irrelevant category.

- IKM is a 3-way classification task: k matches input image I; k mismatches input image I and the visual concept described by k does not fall into a similar category of the visual concept $p_v$ in I; k mismatches input image I but the visual concept described by k falls into a similar category of the visual concept $p_v$ in I. Loss of IKM is a cross-entropy: $L_{IKM} = -\frac{1}{\|D\|}\sum_{i=1}^{\|D\|} log p(y_i^k\|c,k,t,v)$.

- IEC has two types: Input image I remains the same; The visual embedding of the visual concept $p_v$ in input image I is replaced with the embedding of another concept that is visually similar but falls into an irrelevant category with $p_v$. The loss of LEC is $L_{LEC} = -\frac{1}{\|D\|} \sum_{i=1}^{\|D\|}$. The total loss is described as L = $L_{MLM} + L_{ITM} + L_{IKM} + L_{IEC}$. $L_{MLM(Masked Language Modeling)}$ is a loss that describes the average of all cross-entropy loss with respect to the p of predicting the correct masked tokens given a vocabulary. $L_{ITM(Image-Text Matching)}$ enables GIVL to learn the alignment between texts and images. The diagram of GIVL is shown below. This model can actually help the world's culture communicate more efficient and close.

![Framework of GIVL](/images/DailyPaper/04/02.jpeg "Framework of GIVL")

### [33_Network Function Virtualization: State-of-the-Art and Research Challenges](http://ieeexplore.ieee.org/document/7243304/)

- This paper is for the course quiz. This paper introduces **Network Function Virtualization (NFV)**. I will elaborate this paper from promising research directions, key NFV projects, early implementations, use cases, and commercial products. Higher requirements of service provision pushes TSP to develop, and this brings the high cost. If blindly increases the cost, the customers will lost. Therefore, TSPs need to find ways of building more dynamic and service-aware networks. NFV uses the method of leveraging virtualization technology to offer a new way to design, deploy and manage networking services to address these challenges. The main idea of NFV is the decoupling of physical network equipment from the functions that run on them. This allows for the consolidation of many network equipment types onto high volume servers, switches and storage, which could be located in data centers, distributed network nodes and at end user premises. Then Virtual Network Functions(VNFs) can be separated and implemented in the different servers. NFV promises TSPs with more flexibility to further open up their network capabilities and services to users and other services, and the ability to deploy or support new network services faster and cheaper so as to realize better service agility. NFV paves the way to a number of differences in the way network service provisioning is realized in comparison to current practice. (1) Decoupling software from hardware; (2)Flexible network function deployment; (3)Dynamic scaling. Problems contain realization of some of these goals and whether implementation translates to the benefits initially expected. The NFV Architecture is composed of three key elements: Network Function Virtualization Infrastructure (NFVI), VNFs and NFV MANO.

- Promising Research Directions: (1) With regard to scope, the important aspects of NFV are not considered, such as its relationship with SDN and cloud computing; (2) Limited review and analysis of standardization activities; (3) Incomplete descriptions of ongoing research and state-of-the-art efforts and research challenges.

- Key NFV Projects: (1) Network Architecture and Performance; (2) Security and Resilience; (3) Reliability and Availability; (4) Support for Heterogeneity; (5) Legacy Support; (6) Network Scalability and Automation.

- Use Cases: Customer Premises Equipment (CPE) in Two Structures; Evolved Packet Core in Two Structures

- Commercial Products: Infrastructure Provider (InP); Telecommunications Service Provider (TSP); VNF Providers (VNFPs) and Server Providers (SPs); Brokers; End Users.

### [34_Advances in Computer Vision-Based Civil Infrastructure Inspection and Monitoring](https://linkinghub.elsevier.com/retrieve/pii/S2095809918308130)

- This paper is a overall introduction about how the computer vision technology is applied in civil infrastructure condition assessment. Inspection applications and monitoring applications will be respectively described. Take the inspecting the bridge's structure for example, it is hard and time-consuming to install sensors and the following maintenance will be very expensive. Therefore, use computer vision technology to monitor the bridge's structure is very crucial. Unsupervised learning technology and optical flow techniques are suitable for the monitoring method.

- The inspection applications are made up of two steps: Firstly, utilize UAVs for remote automated data acquisition; Secondly, use computer vision techniques to perform data processing and inspection.  
Automated damage detection has three methods:(1) Heuristic feature extraction methods: Apply a threshold or a machine learning classifier to the output of a hand-crafted filter for the particular damage type (DT) of interest. (2) Deep learning-based damage detection: Using machine learning techniques or relying on a combination of heuristic features together with a classifier. (3) Change detection：Building a baseline representation of the structure and compared against using data from subsequent inspections.  
Structural component recognition mainly has three methods: (1) Heuristic-based structural component recognition using image data which strongly depends on the values of thresholds; (2) Structural component recognition using 3D point-cloud data: 3D point cloud is builded to detect and there are a lot of method about 3D point cloud; (3) Deep learning-based structural component recognition using image data which is based on semantic segmentation.  
Damage detection with structure-level consistency is also one part of inspection application.

- The monitoring technology has two category: Static applications and dynamic applications.  
Measurement of static displacements and strains for civil infrastructure using vision-based techniques is often carried out using **digital image correlation (DIC)**.  
Dynamic method is completed by system identification and modal analysis. For example, detect the optics change in the laboratory and vision-based vibration measurement techniques in the laboratory.

- There are challenge in the vision-based automated inspection and monitoring of civil infrastructure: (1) Automated structural inspections necessitate integral understanding of damage and context: Higher accuracy damage detection and component recognition are still needed; (2) The generality of deep networks depends on the generality of data; (3) Human-like perception for inspections requires an understanding of sequential views: Temporal information should be considered; (4) Displacements are often small and difficult to capture: The accessibility of the structural components of interest is often limited; (5) Lighting and environmental effects; (6) Big data needs big data management: Need to handle and process full-field modal information obtained from video band-passing techniques.

### [35_A Review of Vision-Laser-Based Civil Infrastructure Inspection and Monitoring](https://www.mdpi.com/1424-8220/22/15/5882)

- This paper briefly introduces **an overview of vision-based inspection and vision–laser-based monitoring techniques and applications**. Sensors can be divided into contact and non-contact sensors. Vision based inspection mainly focuses on non-contact sensors but the 3D detection accuracy of the monocular camera is very low under long distances. As mentioned in the paper, 'a single sensor can have a certain role but also has limitations: a monocular camera can perform defect inspection in a 2-dimensional plane, but the lack of depth information makes it impossible to quantify defects; a single-beam laser cannot identify the entire object and locate the defects; LiDAR-based monitoring is accurate, but it is expensive, time-consuming, and lacks color information.' So people take the combination of these sensors into account. The overview of this paper is shown below.

![Overview](/images/DailyPaper/04/03.png "Overview")

- Vision-Based Infrastructure Inspection: The biggest two challenges existed in this process is (1) a single static camera is limited by its field of view; (2) the flight path of camera-equipped drones heavily affects inspection results.  
Image processing algorithms primarily include gray-scale transformation, filtering, morphology, feature detection, and region segmentation.  
Object detection aims to distinguish different objects and accurately estimate the position and concept of the object in the image.  
Semantic segmentation is a high-level task that facilitates complete scene understanding.  

- Vision–Laser-Based Infrastructure Monitoring mainly contains two kinds of technologies: Vision-Based Monitoring and Laser-Vision Fusion.  
Vision-Based Monitoring has two methods:  
(1)DIC: Digital image correlation (DIC) technology is a visual measurement technology. Its principle is to divide the ROI of two digital images before and after deformation into several sub-regions and obtain the displacement of the corresponding sub-regions through correlation calculations. The deformation information of an entire field can be obtained. DIC technology can measure the target deformation and strain, and has the advantages of full-field measurement, strong interference ability, and high measurement accuracy. An important point of the DIC method is that it does not require expensive sensors, and even a mobile phone can use DIC for complete displacement monitoring.  
(2) MVS and SFM: Multi-view stereo photogrammetry (MVS) is a method of infrastructure monitoring that utilizes multiple cameras. MVS must know the camera pose as well as the intrinsic and extrinsic parameters of the camera, and the mapping matrix between multiple cameras must be obtained through camera calibration. The principle of structure from motion (SFM) is to use the SIFT feature to replace the calibration board to estimate the pose of the camera and generate a 3D point cloud.  
DIC is a static measurement technology that requires a strict experimental layout and a measurement environment. MVS must calibrate the camera pose and arrange the control points in advance. SFM mostly completes monitoring and 3D reconstruction through SIFT feature point matching. Although SIFT feature points are effective, they still cause matching errors in complex architectural environments, forming sparse 3D point clouds.

- Laser–Vision Fusion has three kinds of technology:
(1) Laser Range Vision: "Single-point displacement monitoring tasks are often involved in infrastructure monitoring, such as bridge health and slight deformation of foundation pits. This type of problem can be transformed into transformation monitoring of the point to be measured in a 3D space in large-scale space. Because the target to be measured is small, and the monitoring distance is long, a combination of long-distance laser ranging and visual detection technology is required. The image total station is a typical combination of laser ranging and vision, and it has a significant role in the field of infrastructure monitoring."  
(2) Laser Structured Light: "Laser structured light is an active optical measurement technique that projects a laser point or line through an emitter onto the surface of the object to be measured, and the image is acquired by an image sensor. The 3D coordinates of the object are calculated through systematic geometric relationships."  
(3) LiDAR Vision: LiDAR is a measurement technology that emits a pulsed laser beam to a target and then measures the arrival time, strength, and other parameters of the reflected signal to determine the distance, orientation, motion state, and surface optical properties of the target.  

- Challenges: (1)Model Training Requires Large Amounts of Data; (2) Model Transferability; (3) Noise Influence; (4) Expensive Sensors; (5) Decision-Making Problem; (6) Sensor Fusion.
   
### [36_Computer Vision Based Health Monitoring in Railway Infrastructure](https://scholars.cityu.edu.hk/en/theses/theses(175fc3f7-e188-4dd1-bb41-2557fdc56a05).html)

- Surface and track of bridge are checked by the computer vision technology. YOLO v3 is used as the basic algorithm. Since this paper is other's Ph.D. dissertation, I do not want to cite too much.

### [37_Event-based Vision: A Survey](http://arxiv.org/abs/1904.08405)

- 'Event cameras are bio-inspired sensors that differ from conventional frame cameras: Instead of capturing images at a fixed rate, they asynchronously measure **per-pixel brightness changes, and output a stream of events that encode the time, location and sign of the brightness changes**. Event cameras offer attractive properties compared to traditional cameras: high temporal resolution (in the order of μs), very high dynamic range (140 dB vs. 60 dB), low power consumption, and high pixel bandwidth (on the order of kHz) resulting in reduced motion blur.'

- The event is generated via the exceed-threshold log intensity changes. The first silicon retina was developed by Mahowald and Mead at Caltech during the period 1986-1992, in Ph.D. thesis work that was awarded the prestigious Clauser prize. And the DVS (Dynamic Vision Sensor) event camera had its genesis in a frame-based silicon retina design.

- There are several challenges of designing: (1) Coping with different space-time output: The output of event cameras is fundamentally different from that of standard cameras: events are asynchronous and spatially sparse, whereas images are synchronous and dense. Hence, frame based vision algorithms designed for image sequences are not directly applicable to event data. (2) Coping with different photometric sensing: In contrast to the gray scale information that standard cameras provide, each event contains binary (increase/decrease) brightness change information. Brightness changes depend not only on the scene brightness, but also on the current and past relative motion between the scene and the camera. (3) Coping with noise and dynamic effects: All vision sensors are noisy because of the inherent shot noise in photons and from transistor circuit noise, and they also have non-idealities. This situation is especially true for event cameras, where the process of quantizing temporal contrast is complex and has not been completely characterized. We are far from having a model that can predict event camera noise statistics under arbitrary illumination and biasing conditions. Solving this challenge would lead to better estimation method. One of the key questions of the paradigm shift posed by event cameras is how to extract meaningful information from the event data to fulfill a given task.

### [38_Secrets of Event-Based Optical Flow](https://arxiv.org/pdf/2207.10022.pdf)

- This paper proposes **a multi-reference focus loss function** and **a principled time-aware flow**. All experiments are based on **the brightness constancy assumption**.
 
### [39_Traditional and modern strategies for optical flow_ an investigation](https://link.springer.com/10.1007/s42452-021-04227-x)

- Optical flow is the pattern of the apparent motion of objects in a visual scene caused by the motion of an object or camera or both. When a camera records a scene for a given time, the resulting image sequence can be considered as a function of gray values at image pixel position (x, y) and the time t. There are two methods to estimate optical flow: (1) Traditional methods; (2) Deep learning based or CNN methods. The majority of optical flow methods are based on brightness constancy and smoothness assumptions.

### [310_Event-Based Optical Flow Estimation with Spatio-Temporal Backpropagation Trained Spiking Neural Network](https://www.mdpi.com/2072-666X/14/1/203)

- The spike neural network has spatiotemporal coding characteristics, so it can be compatible with the spatiotemporal data of an event camera. This paper proposes an **end-to-end spike neural network** to predict the optical flow of the discrete spatiotemporal data stream for the event camera. Event cameras are also suitable for optical flow estimation since the precise timestamp at pixel-level intensity changes directly encodes fine-grain motion information. MVSEC is regarded as the dataset to train and test.

### [311_A Novel Dense Full-Field Displacement Monitoring Method Based on Image Sequences and Optical Flow Algorithm](https://www.mdpi.com/2076-3417/10/6/2118)

- This paper obtained the deformation of the bridge structure by tracking a virtual target using the optical flow algorithm. And this paper just uses traditional method of optical flow to calculate the pixels' displacement.

### [312_Computer-Vision-Based Vibration Tracking Using a Digital Camera_A Sparse-Optical-Flow-Based Target Tracking Method](https://arxiv.org/pdf/2207.10022.pdf)

- Structural vibration monitoring is an important topic in object detection existed in the computer vision. In this paper, a new target tracking method based on the sparse optical flow technique is introduced for improving the accuracy in tracking the target, especially when the target has a large displacement. The proposed method utilizes the Oriented FAST and Rotated BRIEF (ORB) technique which is based on FAST (Features from Accelerated Segment Test), a feature detector, and BRIEF (Binary Robust Independent Elementary Features), a binary descriptor. In this study, a novel sparse-optical-flow-based target tracking approach for structural vibration monitoring is proposed, where t**he conventional sparse optical flow algorithm (i.e., LK) is enhanced** to track a set of sparse key-points accurately. The methods used for monitoring vibration are basically four kinds: Sparse Optical Flow, Feature Matching, Dense Optical Flow and Template Matching. The visual sensing system used for structural vibration monitoring consists of two components: (1) Camera calibration and scale conversion; (2) Frame tracking strategies and displacement calculation. This paper proposes a more efficient algorithm to compute the optical algorithm.

### [313_Meta-Learning for Adaptation of Deep Optical Flow Networks](https://ieeexplore.ieee.org/document/10031014/)

- This paper proposes an instance-wise meta-learning algorithm for optical flow domain adaptation. Optical flow defines the apparent 2D motion field between a pair of images. In other words, it indicates pixel correspondences between neighboring frames in videos. Use Pytorch to realize the meta-learning. The test domain adaptation method that enables a neural network to have separate sets of network coefficients for different scenarios can be used to improve the performance of optical flow in the simulated dataset.

### [314_Optical Flows Estimation by Matching Time Surface with Event-Based Cameras](https://www.mdpi.com/1424-8220/21/4/1150)

- In this work, a novel method of estimating optical flow from event-based cameras is proposed by **matching the time surface of events**. The proposed loss function measures the timestamp consistency between the time surface formed by the latest timestamp of each pixel and the one that is slightly shifted in time. This makes it possible to estimate dense optical flows with high accuracy without restoring luminance or additional sensor information. It is possible to estimate a dense optical flow from only the events without restoring the luminance.

### [315_EV-FlowNet: Self-Supervised Optical Flow Estimation for Event-based Cameras](https://arxiv.org/pdf/1802.06898.pdf)

- This paper proposes **EV-FlowNet**, a novel self-supervised deep learning pipeline for optical flow estimation for event based cameras. An image based representation of a given event stream is introduced, which is fed into a self-supervised neural network as the sole input. The corresponding gray-scale images captured from the same camera at the same time as the events are then used as a supervisory signal to provide a loss function at training time, given the estimated flow from the network. The framework of EV-FlowNet is shown below.

![EV-FlowNet](/images/DailyPaper/04/04.png "EV-FlowNet")

### [316_Event-Based Visual Flow](https://www.neuromorphic-vision.com/public/publications/3/publication.pdf)

- This paper introduces a new methodology to compute dense visual flow using the precise timings of spikes from an asynchronous event-based retina.

### [317_Spike-FlowNet_Event-based Optical Flow Estimation with Energy-Efficient Hybrid Neural Networks](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123740358.pdf)

- This paper proposes **Spike-FlowNet** which is a deep hybrid neural network architecture integrating SNNs and ANNs for efficiently estimating optical flow from sparse event camera outputs without sacrificing the performance. The dataset used to test is MVSEC. Typically, the number of synaptic operations is used as a metric for benchmarking the computational energy of neuromorphic hardware. This paper use LK algorithm to calculate the optical flow.

### [318_Self-Supervised Learning of Event-Based Optical Flow with Spiking Neural Networks](https://arxiv.org/pdf/2106.01862.pdf)

- This paper focuses on the complex task of learning to estimate optical flow from event-based camera inputs in a self-supervised manner **(SSL)**, and modifies the state-of-the-art ANN training pipeline to encode minimal temporal information in its inputs. Moreover, we reformulate the self-supervised loss function for event-based optical flow to improve its **convexity**. The ANNs proposes in this paper have the similar ability with SNNs. This paper shows a method to transfer ANNs to SNNs. I need to cite the three papers mentioned here. ‘Concerning depth and/or optical flow regression, two datasets have currently established themselves as the goto choices: the **MVSEC** Dataset by [8], and the **DSEC** Dataset by [9]. While all of these datasets have proven invaluable to develop event-based computer vision algorithms, there is still an enormous gap between event-based and image-based publicly available datasets, and many authors are still forced to develop their own.’ this is meaningful for my idea of building my own dataset. Because of the lack of overall temporal context, the network by using short frames is unable to extract longer-term dependencies, and therefore to accurately predict optical flow. Exploiting the intrinsic memory of spiking neurons is indeed a potentially useful approach, but the increased computational power linked to unrolling a stateful computational graph makes the task challenging.

### [319_Optical Flow estimation with Event-based Cameras and Spiking Neural Networks](https://arxiv.org/pdf/2302.06492.pdf)

- This paper proposes **a U-Net-like SNN** which is able to make dense optical flow estimations after supervised training. Besides, a new angular loss is adopted. And 3d encoding of input event over a temporal dimension is utilized to increase the accuracy.

### [320_SpikeMS_Deep Spiking Neural Network for Motion Segmentation.pdf](https://arxiv.org/pdf/2105.06562.pdf)

- This paper proposes **SpikeMS**, the first deep encoder-decoder SNN architecture for the real-world large-scale problem of motion segmentation using the event-based DVS camera as input. To accomplish this, a novel spatiotemporal loss formulation that includes both spike counts and classification labels in conjunction with the use of new techniques for SNN back-propagation is introduced. In SNNs, the neurons output pulses that are non-differentiable, rendering attempts at directly applying the backpropagation algorithm non-trivial.

### [321_A Review of Computer Vision-Based Structural Deformation Monitoring in Field Environments.pdf](https://www.mdpi.com/1424-8220/22/10/3789)

### [322_ESIM_an Open Event Camera Simulator.pdf](http://proceedings.mlr.press/v87/rebecq18a/rebecq18a.pdf)

- Since the event-based camera is expensive, this paper introduces a **simulator** of event camera! Thanks! The key component of this simulator is a theoretically sound, adaptive rendering scheme that only samples frames when necessary, through a tight coupling between the rendering engine and the event simulator. [This simulator can be found here.](http://rpg.ifi.uzh.ch/esim).
