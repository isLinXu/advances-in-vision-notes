这份PPT是关于计算机视觉领域中的运动估计（Motion Estimation）的课程讲义，由Vincent Sitzmann, Mina Konaković Luković, 和Bill Freeman等人制作，并由Google的Deqing Sun进行讲授。课程内容主要分为两个部分：传统的运动估计方法和基于深度学习的运动估计方法，以及它们的应用。

### 1. 传统方法（Classical Approach）

#### 1.1 光流（Optical Flow）
- 光流是描述每个像素在二维图像中的运动。
- 光流的基本假设是亮度恒定性（Brightness Constancy），即物体的亮度在连续的图像帧中保持不变。

#### 1.2 匹配基础的运动估计
- 通过比较图像1中的像素与图像2中像素的相似性来估计运动。
- 通过最小化颜色差异来找到最佳匹配。

#### 1.3 卢卡斯-卡诺德算法（Lucas-Kanade）
- 该算法通过比较图像块（patch）之间的相似性来解决运动估计中的歧义问题。
- 通过构建成本体积（cost volume）来评估不同运动向量的相似性。

#### 1.4 粗到细的迭代估计（Coarse-to-Fine Iterative Estimation）
- 该方法从低分辨率的图像开始估计，逐步提高分辨率，以减少计算量。
- 通过使用从上层估计得到的信息来改进下层的估计。

#### 1.5 经典方法的挑战
- 经典方法面临的挑战包括大运动估计、运动模糊、遮挡、光照变化、噪声等。
- 经典方法加上非局部平滑（Non-Local Smoothness）的EpicFlow算法可以改善这些问题。

### 2. 基于深度学习的方法（Deep Learning-Based Approach）

#### 2.1 监督学习光流
- 使用深度学习模型进行光流估计，其中FlyingChairs数据集被用作训练数据。

#### 2.2 光流网络（FlowNet）
- FlowNetS和FlowNetC是两种基于深度学习的光流估计网络架构。
- FlowNetS使用U-Net架构直接从图像映射到光流。
- FlowNetC通过比较特征来进行光流估计。

#### 2.3 FlowNet2
- FlowNet2通过堆叠FlowNetS和FlowNetC来提高性能。
- 该网络在准确性和运行时间之间做出了权衡。

#### 2.4 金字塔可学习特征（Pyramid of Learnable Features）
- 通过构建金字塔结构的可学习特征来提高模型的感受野。

#### 2.5 RAFT
- RAFT（Recurrent All-pairs Field Transforms）通过递归更新和成本体积金字塔来提高光流估计的准确性。

#### 2.6 注意力/变换器架构（Attention/Transformer）
- 介绍了基于变换器架构的光流估计方法，如Flowformer和GM-Flow。

### 3. 应用（Applications）

#### 3.1 视频超分辨率（Video Super-Resolution）
- 使用光流技术提高视频的分辨率。

#### 3.2 视频帧插值（Video Frame Interpolation）
- 通过光流合成新的帧来创建慢动作视频。

#### 3.3 面部去模糊（Face Unblur）
- 在移动设备上实时进行密集准确的光流估计，用于去除模糊。

### 4. 总结和未来方向

- 课程最后讨论了光流估计的未来方向，包括如何更好地模拟训练数据、如何设计更有效的网络架构以及如何公平地评估不同架构的性能。
- 强调了训练细节的重要性，以及如何通过现代训练技术显著提高性能。
- 提出了一些未解决的重要问题，例如如何使渲染更真实、如何处理真实世界视频中的运动等。

这份课程讲义提供了对运动估计领域的深入理解，包括传统方法和基于深度学习的方法，以及它们在实际应用中的潜力和挑战。通过这些内容，学生可以更好地理解计算机视觉中运动估计的基本原理和最新进展。