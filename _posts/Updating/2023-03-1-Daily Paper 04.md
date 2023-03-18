---
layout: post
title: Daily Paper (2023.3.1 - 2023.3.31)
categories: [Updating]
description: Some interesting papers
keywords: 
---

### [31_Learning to Retain while Acquiring: Combating Distribution-Shift in Adversarial Data-Free Knowledge Distillation](https://arxiv.org/pdf/2111.06377.pdf)

- This paper proposes the method called **Learning to Retain while Acquiring**. This method treats the task of Knowledge-Acquisition (learning from newly generated samples) and Knowledge-Retention (retaining knowledge on previously met representatives) as meta-train and meta-test, respectively. The purpose is to maintain student performance while updating the generator in the Data-free Knowledge Distillation (DFKD) training. The student update strategies are shown below. It is obvious how the proposed approach treats the knowledge-acquisition loss and knowledge-retention loss as meta-train and meta-test. The separate system is much more helpful for maintaining performance.

![Student Update Strategies](/images/DailyPaper/04/01.png "Student Update Strategies")

- The proposed DFKD is shown below. The structure is similar to the student update strategy shown above. As mentioned in the paper, this method is considered an attacking strategy because of the meta-train and meta-test. But this strategy can guarantee the performance of the student network. This strategy is a trade-off.

![Framework of DFKD](/images/DailyPaper/04/00.png "Framework of DFKD")

### [32_GIVL: Improving Geographical Inclusively of Vision-Language Models with Pre-Training Methods](https://arxiv.org/abs/2301.01893)

- This paper proposes a **Geographically Inclusive Vision-and-Language Pre-trained model (GIVL)** to eliminate cultural differences in the spread of culture. Besides, **Image-Knowledge Matching (IKM) and Image Edit Checking (IEC)** are designed to pre-train GIVL. IKM is used to learn the alignment between images and corresponding textual knowledge in Wikipedia. IEC is proposed to identify whether a visual concept in the input image is replaced by another visually similar idea in an irrelevant category.

- IKM is a 3-way classification task: k matches input image I; k mismatches input image I, and the visual concept described by k does not fall into a similar category of the visual concept $p_v$ in I; k mismatches input image I, but the visual concept described by k falls into a similar category of the visual concept $p_v$ in me. Loss of IKM is a cross-entropy: $L_{IKM} = -\frac{1}{\|D\|}\sum_{i=1}^{\|D\|} log p(y_i^k\|c,k,t,v)$.

- IEC has two types: Input image I remain the same; The visual embedding of the visual concept $p_v$ in input image I am replaced with embedding another concept that is visually similar but falls into an irrelevant category with $p_v$. The loss of LEC is $L_{LEC} = -\frac{1}{\|D\|} \sum_{i=1}^{\|D\|}$. The total loss is described as L = $L_{MLM} + L_{ITM} + L_{IKM} + L_{IEC}$. $L_{MLM(Masked Language Modeling)}$ is a loss that describes the average of all cross-entropy loss concerning the p of predicting the correct masked tokens given a vocabulary. $L_{ITM(Image-Text Matching)}$ enables GIVL to learn the alignment between texts and images. The diagram of GIVL is shown below. This model can help the world's cultures communicate more efficiently and close.

![Framework of GIVL](/images/DailyPaper/04/02.jpeg "Framework of GIVL")

### [33_Network Function Virtualization: State-of-the-Art and Research Challenges](http://ieeexplore.ieee.org/document/7243304/)

- This paper is for the course quiz. This paper introduces **Network Function Virtualization (NFV)**. I will elaborate on this paper from promising research directions, key NFV projects, early implementations, use cases, and commercial products. Higher service provision requirements push TSP to develop, bringing the high cost. If blindly increases the cost, the customers will be lost. Therefore, TSPs need to find ways of building more dynamic and service-aware networks. NFV uses virtualization technology to offer a new way to design, deploy and manage networking services to address these challenges. The main idea of NFV is decoupling physical network equipment from the functions that run on them. NFV allows for consolidating many network equipment types onto high-volume servers, switches, and storage in data centers, distributed network nodes, and end-user premises. Then Virtual Network Functions(VNFs) can be separated and implemented in the different servers. NFV promises TSPs more flexibility to further open up their network capabilities and services to users and other services and the ability to deploy or support new network services faster and cheaper to realize better service agility. NFV paves the way for several differences in how network service provisioning is realized compared to current practice. (1) Decoupling software from hardware; (2)Flexible network function deployment; (3)Dynamic scaling. Problems include realizing some of these goals and whether implementation translates to the expected benefits. The NFV Architecture comprises three key elements: Network Function Virtualization Infrastructure (NFVI), VNFs, and NFV MANO.

- Promising Research Directions: (1) Concerning scope, the critical aspects of NFV are not considered, such as its relationship with SDN and cloud computing; (2) Limited review and analysis of standardization activities; (3) Incomplete descriptions of ongoing research and state-of-the-art efforts and research challenges.

- Key NFV Projects: (1) Network Architecture and Performance; (2) Security and Resilience; (3) Reliability and Availability; (4) Support for Heterogeneity; (5) Legacy Support; (6) Network Scalability and Automation.

- Use Cases: Customer Premises Equipment (CPE) in Two Structures; Evolved Packet Core in Two Structures

- Commercial Products: Infrastructure Provider (InP); Telecommunications Service Provider (TSP); VNF Providers (VNFPs) and Server Providers (SPs); Brokers; End Users.

### [34_Advances in Computer Vision-Based Civil Infrastructure Inspection and Monitoring](https://linkinghub.elsevier.com/retrieve/pii/S2095809918308130)

- This paper introduces how computer vision technology is applied to civil infrastructure condition assessment. Inspection applications and monitoring applications will be respectively described. Take inspecting the bridge's structure. For example, installing sensors is complex and time-consuming, and the following maintenance will be costly. Therefore, using computer vision technology to monitor the bridge's structure is crucial. Unsupervised learning technology and optical flow techniques are suitable for the monitoring method.

- The inspection applications comprise two steps: First, utilize UAVs for remote automated data acquisition; Second, use computer vision techniques to perform data processing and inspection.  
Automated damage detection has three methods:(1) Heuristic feature extraction methods: Apply a threshold or a machine learning classifier to the output of a hand-crafted filter for the particular damage type (DT) of interest. (2) Deep learning-based damage detection: Using machine learning techniques or relying on a combination of heuristic features and a classifier. (3) Change detection： Building a baseline representation of the structure and compared against using data from subsequent inspections.  
Structural component recognition mainly has three methods: (1) Heuristic-based structural component recognition using image data which strongly depends on the values of thresholds; (2) Structural component recognition using 3D point-cloud data: 3D point cloud is built to detect, and there are many methods about 3D point cloud; (3) Deep learning-based structural component recognition using image data which is based on semantic segmentation.  
Damage detection with structure-level consistency is also one part of the inspection application.

- The monitoring technology has two categories: Static applications and dynamic applications.  
Measurement of static displacements and strains for civil infrastructure using vision-based techniques is often carried out using **digital image correlation (DIC)**.  
The dynamic method is completed by system identification and modal analysis. For example, detect the optics change in the laboratory and vision-based vibration measurement techniques in the laboratory.

- There are challenges in the vision-based automated inspection and monitoring of civil infrastructure: (1) Automated structural inspections necessitate a critical understanding of damage and context: Higher accuracy damage detection and component recognition are still needed; (2) The generality of deep networks depends on the generality of data; (3) Human-like perception for inspections requires an understanding of sequential views: Temporal information should be considered; (4) Displacements are often small and difficult to capture: The accessibility of the structural components of interest is often limited; (5) Lighting and environmental effects; (6) Big data needs extensive data management: Need to handle and process full-field modal information obtained from video band-passing techniques.

### [35_A Review of Vision-Laser-Based Civil Infrastructure Inspection and Monitoring](https://www.mdpi.com/1424-8220/22/15/5882)

- This paper briefly introduces **an overview of vision-based inspection and vision–laser-based monitoring techniques and applications**. Sensors can be divided into contact and non-contact sensors. Vision-based assessment mainly focuses on non-contact sensors, but the 3D detection accuracy of the monocular camera is very low under long distances. As mentioned in the paper, a single sensor can have a specific role but also has limitations: a monocular camera can perform defect inspection in a 2-dimensional plane, but the lack of depth information makes it impossible to quantify defects; a single-beam laser cannot identify the entire object and locate the faults; LiDAR-based monitoring is accurate, but it is expensive, time-consuming, and lacks color information.' So people take the combination of these sensors into account. The overview of this paper is shown below.

![Overview](/images/DailyPaper/04/03.png "Overview")

- Vision-Based Infrastructure Inspection: The most significant two challenges in this process are (1) a single static camera is limited by its field of view; (2) the flight path of camera-equipped drones heavily affects inspection results.  
Image processing algorithms primarily include grayscale transformation, filtering, morphology, feature detection, and region segmentation.  
Object detection aims to distinguish different objects and accurately estimate the position and concept of the object in the image.  
Semantic segmentation is a high-level task that facilitates complete scene understanding.  

- Vision–Laser-Based Infrastructure Monitoring mainly contains two technologies: Vision-Based Monitoring and Laser-Vision Fusion.  
Vision-Based Monitoring has two methods:  
(1)DIC: Digital image correlation (DIC) technology is an optical measurement technology. Its principle is dividing the ROI of two digital images before and after deformation into several sub-regions and obtaining the corresponding sub-regions displacement through correlation calculations. The deformation information of an entire field can be obtained. DIC technology can measure the target deformation and strain and has the advantages of full-field measurement, strong interference ability, and high measurement accuracy. An essential point of the DIC method is that it does not require expensive sensors, and even a mobile phone can use DIC for complete displacement monitoring.  
(2) MVS and SFM: Multi-view stereo photogrammetry (MVS) is a method of infrastructure monitoring that utilizes multiple cameras. MVS must know the camera pose and the intrinsic and extrinsic parameters of the camera, and the mapping matrix between multiple cameras must be obtained through camera calibration. The principle of structure from motion (SFM) uses the SIFT feature to replace the calibration board to estimate the camera's pose and generate a 3D point cloud.  
DIC is a static measurement technology that requires a strict experimental layout and a measurement environment. MVS must calibrate the camera pose and arrange the control points in advance. SFM mainly completes monitoring and 3D reconstruction through SIFT feature point matching. Although SIFT feature points are effective, they still cause matching errors in complex architectural environments, forming sparse 3D point clouds.

- Laser–Vision Fusion has three kinds of technology:
(1) Laser Range Vision: "Single-point displacement monitoring tasks are often involved in infrastructure monitoring, such as bridge health and slight deformation of foundation pits. This type of problem can be transformed into transformation monitoring of the point to be measured in a 3D space in large-scale space. Because the target to be measured is small and the monitoring distance is long, a combination of long-distance Laser ranging and visual detection technology is required. The total image station is a typical combination of Laser ranging and vision, and it has a significant role in infrastructure monitoring."  
(2) Laser Structured Light: "Laser structured light is an active optical measurement technique that projects a laser point or line through an emitter onto the object's surface to be measured, and an image sensor acquires the image. The 3D coordinates of the object are calculated through systematic geometric relationships."  
(3) LiDAR Vision: LiDAR is a measurement technology that emits a pulsed laser beam to a target and then measures the arrival time, strength, and other parameters of the reflected signal to determine the distance, orientation, motion state, and surface optical properties of the target.  

- Challenges: (1)Model Training Requires Large Amounts of Data; (2) Model Transferability; (3) Noise Influence; (4) Expensive Sensors; (5) Decision-Making Problem; (6) Sensor Fusion.
   
### [36_Computer Vision Based Health Monitoring in Railway Infrastructure](https://scholars.cityu.edu.hk/en/theses/theses(175fc3f7-e188-4dd1-bb41-2557fdc56a05).html)

- Surface and track of the bridge are checked by computer vision technology. YOLO v3 is used as the basic algorithm. Since this paper is another's Ph.D. dissertation, I want to cite only a little.

### [37_Event-based Vision: A Survey](http://arxiv.org/abs/1904.08405)

- 'Event cameras are bio-inspired sensors that differ from conventional frame cameras: Instead of capturing images at a fixed rate, they asynchronously measure **per-pixel brightness changes and output a stream of events that encode the time, location, and sign of the brightness changes**. Event cameras offer attractive properties compared to traditional cameras: high temporal resolution (in the order of μs), very high dynamic range (140 dB vs. 60 dB), low power consumption, and high pixel bandwidth (on the order of kHz), resulting in reduced motion blur.'

- The event is generated via the exceed-threshold log intensity changes. The first silicon retina was developed by Mahowald and Mead at Caltech during the period 1986-1992, in Ph.D. thesis work that was awarded the prestigious Clauser prize. And the DVS (Dynamic Vision Sensor) event camera had its genesis in a frame-based silicon retina design.

- There are several challenges of designing: (1) Coping with different space-time output: The output of event cameras is fundamentally different from that of standard cameras: events are asynchronous and spatially sparse, whereas images are synchronous and dense. Hence, frame-based vision algorithms designed for image sequences are not directly applicable to event data. (2) Coping with different photometric sensing: In contrast to the grayscale information that standard cameras provide, each event contains binary (increase/decrease) brightness change information. Brightness changes depend not only on the scene brightness but also on the current and past relative motion between the scene and the camera. (3) Coping with noise and dynamic effects: All vision sensors are noisy because of the inherent shot noise in photons and from transistor circuit noise, and they also have non-idealities. This situation is especially actual for event cameras, where the process of quantizing temporal contrast is complex and must be thoroughly characterized. We need a model to predict event camera noise statistics under arbitrary illumination and biasing conditions. Solving this challenge would lead to better estimation methods. One of the critical questions of the paradigm shift posed by event cameras is how to extract meaningful information from the event data to fulfill a given task.

### [37_Secrets of Event-Based Optical Flow](https://arxiv.org/pdf/2207.10022.pdf)

- This paper proposes **a multi-reference focus loss function** and **a principled time-aware flow**. All experiments are based on **the brightness constancy assumption**.
 
### [37_Traditional and modern strategies for optical flow_ an investigation](https://link.springer.com/10.1007/s42452-021-04227-x)

- Optical flow is the pattern of the apparent motion of objects in a visual scene caused by the movement of an object or camera or both. When a camera records a location for a given time, the resulting image sequence can be considered a function of gray values at the image pixel position (x, y) and the time t. There are two methods to estimate optical flow: (1) Traditional methods; (2) Deep learning-based or CNN methods. Most optical flow methods are based on brightness constancy and smoothness assumptions.

### [38_Event-Based Optical Flow Estimation with Spatio-Temporal Backpropagation Trained Spiking Neural Network](https://www.mdpi.com/2072-666X/14/1/203)

- The spike neural network has spatiotemporal coding characteristics so that it can be compatible with the spatiotemporal data of an event camera. This paper proposes an **end-to-end spike neural network** to predict the optical flow of the discrete spatiotemporal data stream for the event camera. Event cameras are also suitable for optical flow estimation since the precise timestamp at pixel-level intensity changes directly encodes fine-grain motion information. MVSEC is regarded as the dataset to train and test.

### [38_A Novel Dense Full-Field Displacement Monitoring Method Based on Image Sequences and Optical Flow Algorithm](https://www.mdpi.com/2076-3417/10/6/2118)

- This paper obtained the deformation of the bridge structure by tracking a virtual target using the optical flow algorithm. And this paper uses the traditional visual flow method to calculate the pixels' displacement.

### [39_Meta-Learning for Adaptation of Deep Optical Flow Networks](https://ieeexplore.ieee.org/document/10031014/)

- This paper proposes an instance-wise meta-learning algorithm for optical flow domain adaptation. Optical flow defines the apparent 2D motion field between a pair of images. In other words, it indicates pixel correspondences between neighboring frames in videos. Use PyTorch to realize the meta-learning. The test domain adaptation method that enables a neural network to have separate sets of network coefficients for different scenarios can be used to improve the performance of optical flow in the simulated dataset.

### [310_Optical Flows Estimation by Matching Time Surface with Event-Based Cameras](https://www.mdpi.com/1424-8220/21/4/1150)

- This work proposes a novel method of estimating optical flow from event-based cameras by **matching the time surface of events**. The proposed loss function measures the timestamp consistency between the time surface formed by each pixel's latest timestamp and the one slightly shifted in time. This loss function makes it possible to estimate dense optical flows with high accuracy without restoring luminance or additional sensor information. Estimating a dense optical flow from only the events without correcting the illumination is possible.

### [310_EV-FlowNet: Self-Supervised Optical Flow Estimation for Event-based Cameras](https://arxiv.org/pdf/1802.06898.pdf)

- This paper proposes **EV-FlowNet**, a novel self-supervised deep learning pipeline for optical flow estimation for event-based cameras. An image-based representation of a given event stream is introduced and fed into a self-supervised neural network as the sole input. The corresponding grayscale images captured from the same camera at the same time as the events are then used as a supervisory signal to provide a loss function at training time, given the estimated flow from the network. The framework of EV-FlowNet is shown below.

![EV-FlowNet](/images/DailyPaper/04/04.png "EV-FlowNet")

### [311_Event-Based Visual Flow](https://www.neuromorphic-vision.com/public/publications/3/publication.pdf)

- This paper introduces a new methodology to compute the dense visual flow using the precise timings of spikes from an asynchronous event-based retina.

### [311_Spike-FlowNet_Event-based Optical Flow Estimation with Energy-Efficient Hybrid Neural Networks](https://www.ecva.net/papers/eccv_2020/papers_ECCV/papers/123740358.pdf)

- This paper proposes **Spike-FlowNet**, a deep hybrid neural network architecture integrating SNNs and ANNs for efficiently estimating optical flow from sparse event camera outputs without sacrificing performance. The dataset used to test is MVSEC. Typically, the number of synaptic operations is used to benchmark the computational energy of neuromorphic hardware. This paper uses the LK algorithm to calculate the optical flow.

### [312_Self-Supervised Learning of Event-Based Optical Flow with Spiking Neural Networks](https://arxiv.org/pdf/2106.01862.pdf)

- This paper focuses on learning to estimate optical flow from event-based camera inputs in a self-supervised manner **(SSL)**and modifies the state-of-the-art ANN training pipeline to encode minimal temporal information in its inputs. Moreover, we reformulate the self-supervised loss function for event-based optical flow to improve its **convexity**. The ANNs propose in this paper have a similar ability to SNNs. This paper shows a method to transfer ANNs to SNNs. I need to cite the three articles mentioned here. 

### [312_Optical Flow estimation with Event-based Cameras and Spiking Neural Networks](https://arxiv.org/pdf/2302.06492.pdf)

- This paper proposes **a U-Net-like SNN**, which can make dense optical flow estimations after supervised training. Besides, a new angular loss is adopted. And 3d encoding of input events over a temporal dimension is utilized to increase the accuracy. 'Concerning depth and optical flow regression, two datasets have established themselves as the go-to choices: the **MVSEC** Dataset by [8] and the **DSEC** Dataset by [9]. While all of these datasets have proven invaluable to developing event-based computer vision algorithms, there is still an enormous gap between event-based and image-based publicly available datasets, and many authors are still forced to develop their own.' this is meaningful for my idea of building my dataset. Because of the lack of overall temporal context, the network, using short frames, cannot extract longer-term dependencies and, therefore, accurately predict the optical flow. Exploiting the intrinsic memory of spiking neurons is potentially helpful, but the increased computational power linked to unrolling a stateful computational graph makes the task challenging.

### [313_SpikeMS_Deep Spiking Neural Network for Motion Segmentation](https://arxiv.org/pdf/2105.06562.pdf)

- This paper proposes **SpikeMS**, the first deep encoder-decoder SNN architecture for the real-world, large-scale problem of motion segmentation using the event-based DVS camera as input. To accomplish this, a novel spatiotemporal loss formulation that includes both spike counts and classification labels in conjunction with the use of new techniques for SNN backpropagation is introduced. In SNNs, the neurons output pulses that are non-differentiable, rendering attempts at directly applying the backpropagation algorithm non-trivial.

### [313_A Review of Computer Vision-Based Structural Deformation Monitoring in Field Environments](https://www.mdpi.com/1424-8220/22/10/3789)

- This paper analyzes the influence mechanism of the measuring accuracy of computer vision-based deformation monitoring systems from two perspectives, the physical impact and target tracking algorithm impact, and provide the existing solutions. I learned a lot from this paper; many methods can be cited.

### [314_ESIM_an Open Event Camera Simulator.pdf](http://proceedings.mlr.press/v87/rebecq18a/rebecq18a.pdf)

- Since the event-based camera is expensive, this paper introduces a **simulator** for event cameras! Thanks! The key component of this simulator is a theoretically sound, adaptive rendering scheme that only samples frames when necessary through a tight coupling between the rendering engine and the event simulator. [This simulator can be found here.](http://rpg.ifi.uzh.ch/esim)

- Event camera is expensive, rare, and with practical limitations. Vision sensors measure some function of the radiant flux (or intensity) of light falling per unit area of the sensor, which is referred to as the irradiance E. Event cameras operate in the log domain, which allows them to achieve a high dynamic range: instead of measuring changes of irradiance E, they measure changes of log-irradiance log E. Instead of choosing an arbitrary rendering frame rate, and sampling frames uniformly across time at the selected framerate in the previous work, this paper proposes to **sample frames adaptively, adapting the sampling rate based on the predicted dynamics of the visual signal**. The comparison and the method of adaptive sampling frames are shown below.

![Comparison & Adaptive Sampling](/images/DailyPaper/04/05.png "Comparison & Adaptive Sampling")

### [315_Computer-Vision-Based Vibration Tracking Using a Digital Camera_A Sparse-Optical-Flow-Based Target Tracking Method](https://arxiv.org/pdf/2207.10022.pdf)

- Structural vibration monitoring is an essential topic in object detection in computer vision. This paper introduces a new target-tracking method based on the sparse optical flow technique to improve the accuracy in tracking the target, especially when the target has a large displacement. The proposed method utilizes the Oriented FAST and Rotated BRIEF (ORB) technique is based on FAST (Features from Accelerated Segment Test), a feature detector, and BRIEF (Binary Robust Independent Elementary Features), a binary descriptor. This study proposes a novel sparse-optical-flow-based target tracking approach for structural vibration monitoring, where **the conventional sparse optical flow algorithm (i.e., LK) is enhanced** to track a set of sparse key points accurately. The methods used for monitoring vibration are four kinds: Sparse Optical Flow, Feature Matching, Dense Optical Flow, and Template Matching. The visual sensing system for structural vibration monitoring consists of (1) Camera calibration and scale conversion; (2) Frame tracking strategies and displacement calculation. This paper proposes a more efficient algorithm to compute the optical algorithm.

### [316_Performance Oriented DSP for Flexible Long Haul Coherent Transmission](https://ieeexplore-ieee-org.lib.ezproxy.hkust.edu.hk/document/9645315)

- This is the paper for the course quiz.

- To handle the bandwidth problem in the long haul optical fiber communication networks, this paper discussed digital signal processing(DSP) techniques. The target application scene decides the coherent transceivers. Two extreme scenarios include short-reach transmission systems and long-haul communication systems. Light wave propagation in optical fiber is determined by the Manakov Equation, which describes nonlinearity, chromatic dispersion, and attenuation of optical fiber transmission. Amplification always adds noise to a signal through amplified spontaneous emission (ASE). State of Polarization, Polarization-Mode Dispersion, and Polarization-Dependent Loss will induce polarization-dependent impairments.

- There are three key converter specifications: (1) Analog Bandwidth; (2)Signal-to-noise-plus Distortion Ratio (SNDR), and (3) Effective Number of Bits (ENOB).

- Two critical specifications for the MZMD and the TIA are small-signal gain and the 3dB bandwidth. The gain of the MZMD is determined based on the DAC swing, losses in the RF chain between DAC, MZMD, and MZM, as well as the effectiveness of the MZM in converting input RF signal into optical field modulation that is often measured by the half-wave voltage (Vπ) of the MZM. In addition to gain and bandwidth, the linearity of the MZMD and TIA will influence signal integrity. Finally, the last remaining aspect of an amplifier is related to its linear noise.

- The timing recovery phase-locked-loop (PLL) comprises three main blocks: (1) Phase Detector (PD), (2) Loop Filter, and (3) Voltage-controlled Oscillator (VCO) or Numerically Controlled Oscillator (NCO).

### [317_Real-time 2D Multi-Person Pose Estimation on CPU: Lightweight OpenPose](http://arxiv.org/abs/1811.12004)

- This paper proposes **Lightweight OpenPose**, a lightweight version of OpenPose. Similarly, this lightweight version adopts the **Bottom-up** approach like OpenPose. The Top-down applies a person detector and then runs a pose estimation algorithm for every detected person. In contrast, the Bottom-up detects all key points and groups them by human instances. The pipeline of OpenPose is shown below. Search key points and use affinity to find the best pair for each keypoints. MobileNet v1 replaces the VGG net and uses dilated convolution in a 3 x 3 layer to increase the receptive field. Besides, the residual connection is added to make the deeper network more compact because 1x1+3x3+3x3(dilated) layers are used to replace the 7x7 layer. Moreover, the step with upsampling feature maps should be kept.

![OpenPose Pipeline](/images/DailyPaper/04/06.png "OpenPose Pipeline")

### [317_Realtime Multi-Person 2D Pose Estimation using Part Affinity Fields](https://openaccess.thecvf.com/content_cvpr_2017/papers/Cao_Realtime_Multi-Person_2D_CVPR_2017_paper.pdf)

- This paper introduces **OpenPose**, which I realized I just went through the GitHub repository of OpenPose rather than read this paper. The approach uses a non-parametric representation, which we refer to as **Part Affinity
Fields (PAFs)**is a set of 2D vector fields that encode the location and orientation of limbs over the image domain. The backbone of OpenPose is the first ten layers of VGG-19. The architecture of the two-branch multi-stage CNN is shown below. The loss function of OpenPose contains two parts: the loss for part maps and the affinity fields.

![Architecture of the Two-branch Multi-stage CNN](/images/DailyPaper/04/07.png "Architecture of the Two-branch Multi-stage CNN")

### [318_Spiking Deep Convolutional Neural Networks for Energy-Efficient Object Recognition](http://link.springer.com/10.1007/s11263-014-0788-3)

- This paper introduces a method to **convert a deep CNN to a SNN**. There are two general methods to convert: (1) Directly train a spiking network with CNN-like architecture; (2) Train the original CNN and then apply the learned weights to a SNN with a similar architecture as the trained CNN. To overcome some challenges, this paper first tailor the CNN and converts the tailor CNN into SNN: (1) Make output values in all layers positive; (2) Remove biases from all convolution and the fully connected layers; (3) Use spatial linear sub-sampling instead of spatial max-pooling. The original CNN is shown below:

![Original CNN Model](/images/DailyPaper/04/08.png "Original CNN Model")

The tailor CNN model is shown below:

![The Tailor CNN Model](/images/DailyPaper/04/09.png "The Tailor CNN Model")

The converted SNN model is shown below:

![The Converted SNN Model](/images/DailyPaper/04/10.png "The Converted SNN Model")

### [319_Fast-Classifying, High-Accuracy Spiking Deep Networks Through Weight and Threshold Balancing](http://ieeexplore.ieee.org/document/7280696/)

### [320_Going Deeper in Spiking Neural Networks: VGG and Residual Architectures](http://arxiv.org/abs/1802.02627)

### [321_Spiking-YOLO: Spiking Neural Network for Energy-Efficient Object Detection](http://arxiv.org/abs/1903.06530)
