
# AwesomeGasssian


## High Frequency Details



#### <summary>FreGS: 3D Gaussian Splatting with Progressive Frequency Regularization</summary>
Authors: Jiahui Zhang, Fangneng Zhan, Muyu Xu, Shijian Lu, Eric Xing
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian splatting has achieved very impressive performance in real-time novel view synthesis. However, it often suffers from over-reconstruction during Gaussian densification where high-variance image regions are covered by a few large Gaussians only, leading to blur and artifacts in the rendered images. We design a progressive frequency regularization (FreGS) technique to tackle the over-reconstruction issue within the frequency space. Specifically, FreGS performs coarse-to-fine Gaussian densification by exploiting low-to-high frequency components that can be easily extracted with low-pass and high-pass filters in the Fourier space. By minimizing the discrepancy between the frequency spectrum of the rendered image and the corresponding ground truth, it achieves high-quality Gaussian densification and alleviates the over-reconstruction of Gaussian splatting effectively. Experiments over multiple widely adopted benchmarks (e.g., Mip-NeRF360, Tanks-and-Temples and Deep Blending) show that FreGS achieves superior novel view synthesis and outperforms the state-of-the-art consistently.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/1789b70e-4fb7-4be6-8c53-0d164b1c977b)

 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.06908.pdf) | [⌨️ Code](https://rogeraigc.github.io/FreGS-Page/) | [🌐 Project Page](https://rogeraigc.github.io/FreGS-Page/)




#### <summary>AbsGS: Recovering Fine Details for 3D Gaussian Splatting
Authors: Zongxin Ye, Wenyu Li, Sidun Liu, Peng Qiao, Yong Dou
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3D-GS) technique couples 3D Gaussian primitives with differentiable rasterization to achieve high-quality novel view synthesis results while providing advanced real-time rendering performance. However, due to the flaw of its adaptive density control strategy in 3D-GS, it frequently suffers from over-reconstruction issue in intricate scenes containing high-frequency details, leading to blurry rendered images. The underlying reason for the flaw has still been under-explored. In this work, we present a comprehensive analysis of the cause of aforementioned artifacts, namely gradient collision, which prevents large Gaussians in over-reconstructed regions from splitting. To address this issue, we propose the novel homodirectional view-space positional gradient as the criterion for densification. Our strategy efficiently identifies large Gaussians in over-reconstructed regions, and recovers fine details by splitting. We evaluate our proposed method on various challenging datasets. The experimental results indicate that our approach achieves the best rendering quality with reduced or similar memory consumption. Our method is easy to implement and can be incorporated into a wide variety of most recent Gaussian Splatting-based methods. We will open source our codes upon formal publication.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/2195a2a1-1557-4d79-9ea8-77bc55e953db)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.10484.pdf) | [⌨️ Code](https://ty424.github.io/AbsGS.github.io) | [🌐 Project Page]



<br>
<br>


## Surface

#### <summary>GS-IR: 3D Gaussian Splatting for Inverse Rendering
Authors: Zhihao Liang, Qi Zhang, Ying Feng, Ying Shan, Kui Jia
<details span>
<summary><b>Abstract</b></summary>
We propose GS-IR, a novel inverse rendering approach based on 3D Gaussian Splatting (GS) that leverages forward mapping volume rendering to achieve photorealistic novel view synthesis and relighting results. Unlike previous works that use implicit neural representations and volume rendering (e.g. NeRF), which suffer from low expressive power and high computational complexity, we extend GS, a top-performance representation for novel view synthesis, to estimate scene geometry, surface material, and environment illumination from multi-view images captured under unknown lighting conditions. There are two main problems when introducing GS to inverse rendering: 1) GS does not support producing plausible normal natively; 2) forward mapping (e.g. rasterization and splatting) cannot trace the occlusion like backward mapping (e.g. ray tracing). To address these challenges, our GS-IR proposes an efficient optimization scheme that incorporates a depth-derivation-based regularization for normal estimation and a baking-based occlusion to model indirect lighting. The flexible and expressive GS representation allows us to achieve fast and compact geometry reconstruction, photorealistic novel view synthesis, and effective physically-based rendering. We demonstrate the superiority of our method over baseline methods through qualitative and quantitative evaluations on various challenging scenes.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/b1901133-6909-467f-921d-89f113218b06)


</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.16473.pdf) | [⌨️ Code](https://github.com/lzhnb/GS-IR) | [🌐 Project Page](https://lzhnb.github.io/project-pages/gs-ir.html)



#### <summary>SuGaR: Surface-Aligned Gaussian Splatting for Efficient 3D Mesh Reconstruction and High-Quality Mesh Rendering
Authors: Xiaoyang Lyu, Yang-Tian Sun, Yi-Hua Huang, Xiuzhe Wu, Ziyi Yang, Yilun Chen, Jiangmiao Pang, Xiaojuan Qi
<details span>
<summary><b>Abstract</b></summary>
Existing neural implicit surface reconstruction methods have achieved impressive performance in multi-view 3D reconstruction by leveraging explicit geometry priors such as depth maps or point clouds as regularization. However, the reconstruction results still lack fine details because of the over-smoothed depth map or sparse point cloud. In this work, we propose a neural implicit surface reconstruction pipeline with guidance from 3D Gaussian Splatting to recover highly detailed surfaces. The advantage of 3D Gaussian Splatting is that it can generate dense point clouds with detailed structure. Nonetheless, a naive adoption of 3D Gaussian Splatting can fail since the generated points are the centers of 3D Gaussians that do not necessarily lie on the surface. We thus introduce a scale regularizer to pull the centers close to the surface by enforcing the 3D Gaussians to be extremely thin. Moreover, we propose to refine the point cloud from 3D Gaussians Splatting with the normal priors from the surface predicted by neural implicit models instead of using a fixed set of points as guidance. Consequently, the quality of surface reconstruction improves from the guidance of the more accurate 3D Gaussian splatting. By jointly optimizing the 3D Gaussian Splatting and the neural implicit model, our approach benefits from both representations and generates complete surfaces with intricate details. Experiments on Tanks and Temples verify the effectiveness of our proposed method.

![1713851280545](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/65393e79-6192-4c91-866b-122b29503f7e)


</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.12775.pdf) | [⌨️ Code](https://github.com/Anttwo/SuGaR?tab=readme-ov-file) | [🌐 Project Page](https://anttwo.github.io/sugar/)


#### <summary>NeuSG: Neural Implicit Surface Reconstruction with 3D Gaussian Splatting Guidance
Authors: Hanlin Chen, Chen Li, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
Existing neural implicit surface reconstruction methods have achieved impressive performance in multi-view 3D reconstruction by leveraging explicit geometry priors such as depth maps or point clouds as regularization. However, the reconstruction results still lack fine details because of the over-smoothed depth map or sparse point cloud. In this work, we propose a neural implicit surface reconstruction pipeline with guidance from 3D Gaussian Splatting to recover highly detailed surfaces. The advantage of 3D Gaussian Splatting is that it can generate dense point clouds with detailed structure. Nonetheless, a naive adoption of 3D Gaussian Splatting can fail since the generated points are the centers of 3D Gaussians that do not necessarily lie on the surface. We thus introduce a scale regularizer to pull the centers close to the surface by enforcing the 3D Gaussians to be extremely thin. Moreover, we propose to refine the point cloud from 3D Gaussians Splatting with the normal priors from the surface predicted by neural implicit models instead of using a fixed set of points as guidance. Consequently, the quality of surface reconstruction improves from the guidance of the more accurate 3D Gaussian splatting. By jointly optimizing the 3D Gaussian Splatting and the neural implicit model, our approach benefits from both representations and generates complete surfaces with intricate details. Experiments on Tanks and Temples verify the effectiveness of our proposed method.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/1de18275-365a-42cb-b42d-abdab5f9aa29)

 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.00846.pdf) | [⌨️ Code] | [🌐 Project Page]


#### <summary>2D Gaussian Splatting for Geometrically Accurate Radiance Fields
Authors: Binbin Huang, Zehao Yu, Anpei Chen, Andreas Geiger, Shenghua Gao
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has recently revolutionized radiance field reconstruction, achieving high quality novel view synthesis and fast rendering speed. However, 3DGS fails to accurately represent surfaces due to the multi-view inconsistent nature of 3D Gaussians. We present 2D Gaussian Splatting (2DGS), a novel approach to model and reconstruct geometrically accurate radiance fields from multi-view images. Our key idea is to collapse the 3D volume into a set of 2D oriented planar Gaussian disks. Unlike 3D Gaussians, 2D Gaussians provide view-consistent geometry while modeling surfaces intrinsically. To accurately recover thin surfaces and achieve stable optimization, we introduce a perspective-accurate 2D splatting process utilizing ray-splat intersection and rasterization. Additionally, we incorporate depth distortion and normal consistency terms to further enhance the quality of the reconstructions. We demonstrate that our differentiable renderer allows for noise-free and detailed geometry reconstruction while maintaining competitive appearance quality, fast training speed, and real-time rendering. Our code will be made publicly available.


</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.17888.pdf) | [⌨️ Code] | [🌐 Project Page](https://surfsplatting.github.io/)


#### <summary>GaussianPro: 3D Gaussian Splatting with Progressive Propagation
Authors: Kai Cheng, Xiaoxiao Long, Kaizhi Yang, Yao Yao, Wei Yin, Yuexin Ma, Wenping Wang, Xuejin Chen
<details span>
<summary><b>Abstract</b></summary>
The advent of 3D Gaussian Splatting (3DGS) has recently brought about a revolution in the field of neural rendering, facilitating high-quality renderings at real-time speed. However, 3DGS heavily depends on the initialized point cloud produced by Structure-from-Motion (SfM) techniques. When tackling with large-scale scenes that unavoidably contain texture-less surfaces, the SfM techniques always fail to produce enough points in these surfaces and cannot provide good initialization for 3DGS. As a result, 3DGS suffers from difficult optimization and low-quality renderings. In this paper, inspired by classical multi-view stereo (MVS) techniques, we propose GaussianPro, a novel method that applies a progressive propagation strategy to guide the densification of the 3D Gaussians. Compared to the simple split and clone strategies used in 3DGS, our method leverages the priors of the existing reconstructed geometries of the scene and patch matching techniques to produce new Gaussians with accurate positions and orientations. Experiments on both large-scale and small-scale scenes validate the effectiveness of our method, where our method significantly surpasses 3DGS on the Waymo dataset, exhibiting an improvement of 1.15dB in terms of PSNR.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/82401777-304d-4586-a0f8-6468b760b99b)


</details>


[📃 arXiv:2402](https://arxiv.org/pdf/2402.14650.pdf) | [⌨️ Code](https://github.com/flyingGH/GaussianPro/tree/main?tab=readme-ov-file) | [🌐 Project Page](https://kcheng1021.github.io/gaussianpro.github.io/)




#### <summary>DN-Splatter: Depth and Normal Priors for Gaussian Splatting and Meshing
Authors: Matias Turkulainen, Xuqian Ren, Iaroslav Melekhov, Otto Seiskari, Esa Rahtu, Juho Kannala
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian splatting, a novel differentiable rendering technique, has achieved state-of-the-art novel view synthesis results with high rendering speeds and relatively low training times. However, its performance on scenes commonly seen in indoor datasets is poor due to the lack of geometric constraints during optimization. We extend 3D Gaussian splatting with depth and normal cues to tackle challenging indoor datasets and showcase techniques for efficient mesh extraction, an important downstream application. Specifically, we regularize the optimization procedure with depth information, enforce local smoothness of nearby Gaussians, and use the geometry of the 3D Gaussians supervised by normal cues to achieve better alignment with the true scene geometry. We improve depth estimation and novel view synthesis results over baselines and show how this simple yet effective regularization technique can be used to directly extract meshes from the Gaussian representation yielding more physically accurate reconstructions on indoor scenes.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/ca652582-2e4c-4346-8024-9295a6e9a476)


</details>


[📃 arXiv:2403](https://arxiv.org/pdf/2403.17822.pdf) | [⌨️ Code](https://github.com/maturk/dn-splatter?tab=readme-ov-file) | [🌐 Project Page](https://maturk.github.io/dn-splatter/)



#### <summary>Gaussian Opacity Fields: Efficient and Compact Surface Reconstruction in Unbounded Scenes
Authors: ZEHAO YU, TORSTEN SATTLER, ANDREAS GEIGER
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has demonstrated impressive novel view synthesis results, while allowing the rendering of high-resolution images in real-time. However, leveraging 3D Gaussians for surface reconstruction poses significant challenges due to the explicit and disconnected nature of 3D Gaussians. In this work, we present Gaussian Opacity Fields (GOF), a novel approach for efficient, high-quality, and compact surface reconstruction in unbounded scenes. Our GOF is derived from ray-tracing-based volume rendering of 3D Gaussians, enabling direct geometry extraction from 3D Gaussians by identifying its levelset, without resorting to Poisson reconstruction or TSDF fusion as in previous work. We approximate the surface normal of Gaussians as the normal of the ray-Gaussian intersection plane, enabling the application of regularization that significantly enhances geometry. Furthermore, we develop an efficient geometry extraction method utilizing marching tetrahedra, where the tetrahedral grids are induced from 3D Gaussians and thus adapt to the scene’s complexity. Our evaluations reveal that GOF surpasses existing 3DGS-based methods in surface reconstruction and novel view synthesis. Further, it compares favorably to, or even outperforms, neural implicit methods in both quality and speed.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/807bab14-ac13-42ce-a340-c15df705752d)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.10772.pdf) | [⌨️ Code](https://github.com/autonomousvision/gaussian-opacity-fields) | [🌐 Project Page](https://niujinshuchong.github.io/gaussian-opacity-fields/)

 
#### <summary>3DGSR: Implicit Surface Reconstruction with 3D Gaussian Splatting
Authors: Xiaoyang Lyu, Yang-Tian Sun, Yi-Hua Huang, Xiuzhe Wu, Ziyi Yang, Yilun Chen, Jiangmiao Pang, Xiaojuan Qi
<details span>
<summary><b>Abstract</b></summary>
Existing neural implicit surface reconstruction methods have achieved impressive performance in multi-view 3D reconstruction by leveraging explicit geometry priors such as depth maps or point clouds as regularization. However, the reconstruction results still lack fine details because of the over-smoothed depth map or sparse point cloud. In this work, we propose a neural implicit surface reconstruction pipeline with guidance from 3D Gaussian Splatting to recover highly detailed surfaces. The advantage of 3D Gaussian Splatting is that it can generate dense point clouds with detailed structure. Nonetheless, a naive adoption of 3D Gaussian Splatting can fail since the generated points are the centers of 3D Gaussians that do not necessarily lie on the surface. We thus introduce a scale regularizer to pull the centers close to the surface by enforcing the 3D Gaussians to be extremely thin. Moreover, we propose to refine the point cloud from 3D Gaussians Splatting with the normal priors from the surface predicted by neural implicit models instead of using a fixed set of points as guidance. Consequently, the quality of surface reconstruction improves from the guidance of the more accurate 3D Gaussian splatting. By jointly optimizing the 3D Gaussian Splatting and the neural implicit model, our approach benefits from both representations and generates complete surfaces with intricate details. Experiments on Tanks and Temples verify the effectiveness of our proposed method.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/fe979d36-c651-42ea-8b51-59a0173fc47e)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.00409.pdf) | [⌨️ Code] | [🌐 Project Page]


<br>
<br>

## Others

#### <summary>On the Error Analysis of 3D Gaussian Splatting and an Optimal Projection Strategy
Authors: Letian Huang, Jiayang Bai, Jie Guo, Yuanqi Li, Yanwen Guo
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting has garnered extensive attention and application in real-time neural rendering. Concurrently, concerns have been raised about the limitations of this technology in aspects such as point cloud storage, performance, and robustness in sparse viewpoints, leading to various improvements. However, there has been a notable lack of attention to the fundamental problem of projection errors introduced by the local affine approximation inherent in the splatting itself, and the consequential impact of these errors on the quality of photo-realistic rendering. This paper addresses the projection error function of 3D Gaussian Splatting, commencing with the residual error from the first-order Taylor expansion of the projection function. The analysis establishes a correlation between the error and the Gaussian mean position. Subsequently, leveraging function optimization theory, this paper analyzes the function's minima to provide an optimal projection strategy for Gaussian Splatting referred to Optimal Gaussian Splatting, which can accommodate a variety of camera models. Experimental validation further confirms that this projection methodology reduces artifacts, resulting in a more convincingly realistic rendering.

 
</details>

[📃 arXiv:2402](https://arxiv.org/pdf/2402.00752.pdf) | [⌨️ Code] | [🌐 Project Page]

#### <summary>InFusion: Inpainting 3D Gaussians via Learning Depth Completion from Diffusion Prior
Authors: Zhiheng Liu, Hao Ouyang, Qiuyu Wang, Ka Leong Cheng, Jie Xiao, Kai Zhu, Nan Xue, Yu Liu, Yujun Shen, Yang Cao
<details span>
<summary><b>Abstract</b></summary>
3D Gaussians have recently emerged as an efficient representation for novel view synthesis. This work studies its editability with a particular focus on the inpainting task, which aims to supplement an incomplete set of 3D Gaussians with additional points for visually harmonious rendering. Compared to 2D inpainting, the crux of inpainting 3D Gaussians is to figure out the rendering-relevant properties of the introduced points, whose optimization largely benefits from their initial 3D positions. To this end, we propose to guide the point initialization with an image-conditioned depth completion model, which learns to directly restore the depth map based on the observed image. Such a design allows our model to fill in depth values at an aligned scale with the original depth, and also to harness strong generalizability from largescale diffusion prior. Thanks to the more accurate depth completion, our approach, dubbed InFusion, surpasses existing alternatives with sufficiently better fidelity and efficiency under various complex scenarios. We further demonstrate the effectiveness of InFusion with several practical applications, such as inpainting with user-specific texture or with novel object insertion.
 
![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/b77098e6-16ae-4adb-b16e-46b94569feb8)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.11613.pdf) | [⌨️ Code](https://github.com/ali-vilab/infusion) | [🌐 Project Page](https://johanan528.github.io/Infusion/)




#### <summary>EGGS: Edge Guided Gaussian Splatting for Radiance Fields
Authors: Yuanhao Gong
<details span>
<summary><b>Abstract</b></summary>
The Gaussian splatting methods are getting popular. However, their loss function only contains the ℓ1 norm and the structural similarity between the rendered and input images, without considering the edges in these images. It is well-known that the edges in an image provide important information. Therefore, in this paper, we propose an Edge Guided Gaussian Splatting (EGGS) method that leverages the edges in the input images. More specifically, we give the edge region a higher weight than the flat region. With such edge guidance, the resulting Gaussian particles focus more on the edges instead of the flat regions. Moreover, such edge guidance does not crease the computation cost during the training and rendering stage. The experiments confirm that such simple edge-weighted loss function indeed improves about 1 ∼ 2 dB on several difference data sets. With simply plugging in the edge guidance, the proposed method can improve all Gaussian splatting methods in different scenarios, such as human head modeling, building 3D reconstruction, etc.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/7b2ce10d-d422-4c21-83ce-01b9805ef2e7)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.09105.pdf) | [⌨️ Code] | [🌐 Project Page]


#### <summary>EfficientGS: Streamlining Gaussian Splatting for Large-Scale High-Resolution Scene Representation
Authors: Wenkai Liu, Tao Guan, Bin Zhu, Lili Ju, Zikai Song, Dan Li, Yuesong Wang, Wei Yang
<details span>
<summary><b>Abstract</b></summary>
In the domain of 3D scene representation, 3D Gaussian Splatting (3DGS) has emerged as a pivotal technology. However, its application to large-scale, high-resolution scenes (exceeding 4k×4k pixels) is hindered by the excessive computational requirements for managing a large number of Gaussians. Addressing this, we introduce 'EfficientGS', an advanced approach that optimizes 3DGS for high-resolution, large-scale scenes. We analyze the densification process in 3DGS and identify areas of Gaussian over-proliferation. We propose a selective strategy, limiting Gaussian increase to key primitives, thereby enhancing the representational efficiency. Additionally, we develop a pruning mechanism to remove redundant Gaussians, those that are merely auxiliary to adjacent ones. For further enhancement, we integrate a sparse order increment for Spherical Harmonics (SH), designed to alleviate storage constraints and reduce training overhead. Our empirical evaluations, conducted on a range of datasets including extensive 4K+ aerial images, demonstrate that 'EfficientGS' not only expedites training and rendering times but also achieves this with a model size approximately tenfold smaller than conventional 3DGS while maintaining high rendering fidelity.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/5fb5dcb4-ade4-4e35-847c-5ff3e8658eb2)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.12777.pdf) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Real-Time View Synthesis for Large Scenes with Millions of Square Meters

Authors: Qing Shuai  Haoyu Guo  Zhen Xu  Haotong Lin   Sida Peng   Hujun Bao   Xiaowei Zhou
<details span>
<summary><b>Abstract</b></summary>
This paper tackles the challenge of high-quality, real-time rendering of large-scale scenes with millions of square meters. The recently proposed 3DGS has demonstrated exceptional rendering quality and speed, but it typically requires a large amount of Gaussian primitives to model complex 3D scenes in high fidelity. When users need to holistically view such scenes, the 3DGS model falls short in rendering excessive Gaussians in real time. To solve this issue, we propose a novel representation named Level of Gaussians (LoG) for efficiently rendering 3D scenes, inspired by the classical idea of levels of detail (LOD) in rendering: fine details are essential for close views but become redundant for distant views. We implement LoG as a tree structure storing Gaussians and devise a progressive training strategy to reconstruct it from images in an end-to-end manner, which also provides effective regularization and helps overcome the local minima. In the rendering phase, the optimal level of Gaussians is adaptively selected based on the viewer's distance and angle. Experiments show that our approach enables real-time and high-quality rendering of areas spanning millions of square meters, representing a significant advancement in rendering large-scale scenes.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/e7f56168-8979-4708-8269-1e49193d392b)


</details>

[📃 arXiv:24xx] | [⌨️ Code] | [🌐 Project Page](https://zju3dv.github.io/LoG_webpage/)

#### <summary>Metric3D v2: A Versatile Monocular Geometric Foundation Model for Zero-shot Metric Depth and Surface Normal Estimation

Authors: Mu Hu, Wei Yin, Chi Zhang, Zhipeng Cai, Xiaoxiao Long, Hao Chen, Kaixuan Wang, Gang Yu, Chunhua Shen, Shaojie Shen
<details span>
<summary><b>Abstract</b></summary>
We introduce Metric3D v2, a geometric foundation model for zero-shot metric depth and surface normal estimation from a single image, which is crucial for metric 3D recovery. While depth and normal are geometrically related and highly complimentary, they present distinct challenges. SoTA monocular depth methods achieve zero-shot generalization by learning affine-invariant depths, which cannot recover real-world metrics. Meanwhile, SoTA normal estimation methods have limited zero-shot performance due to the lack of large-scale labeled data. To tackle these issues, we propose solutions for both metric depth estimation and surface normal estimation. For metric depth estimation, we show that the key to a zero-shot single-view model lies in resolving the metric ambiguity from various camera models and large-scale data training. We propose a canonical camera space transformation module, which explicitly addresses the ambiguity problem and can be effortlessly plugged into existing monocular models. For surface normal estimation, we propose a joint depth-normal optimization module to distill diverse data knowledge from metric depth, enabling normal estimators to learn beyond normal labels. Equipped with these modules, our depth-normal models can be stably trained with over 16 million of images from thousands of camera models with different-type annotations, resulting in zero-shot generalization to in-the-wild images with unseen camera settings. Our method enables the accurate recovery of metric 3D structures on randomly collected internet images, paving the way for plausible single-image metrology.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/895b3176-2020-4fbb-9cf5-e1bab9467167)



</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.15506) | [⌨️ Code](https://github.com/YvanYin/Metric3D) | [🌐 Project Page](https://jugghm.github.io/Metric3Dv2/)


#### <summary>DIG3D: Marrying Gaussian Splatting with Deformable Transformer for Single Image 3D Reconstruction

Authors: Jiamin Wu, Kenkun Liu, Han Gao, Xiaoke Jiang, Lei Zhang
<details span>
<summary><b>Abstract</b></summary>
In this paper, we study the problem of 3D reconstruction from a single-view RGB image and propose a novel approach called DIG3D for 3D object reconstruction and novel view synthesis. Our method utilizes an encoder-decoder framework which generates 3D Gaussians in decoder with the guidance of depth-aware image features from encoder. In particular, we introduce the use of deformable transformer, allowing efficient and effective decoding through 3D reference point and multi-layer refinement adaptations. By harnessing the benefits of 3D Gaussians, our approach offers an efficient and accurate solution for 3D reconstruction from single-view images. We evaluate our method on the ShapeNet SRN dataset, getting PSNR of 24.21 and 24.98 in car and chair dataset, respectively. The result outperforming the recent method by around 2.25%, demonstrating the effectiveness of our method in achieving superior results.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/290e9358-34d8-4711-8273-1f3afed3bdb0)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.16323) | [⌨️ Code] | [🌐 Project Page]


<br>
<br>


## Others, not Gaussian

#### <summary>D2NT: A High-Performing Depth-to-Normal Translator
Authors: Yi Feng, Bohuan Xue, Ming Liu, Qijun Chen, and Rui Fan
<details span>
<summary><b>Abstract</b></summary>
Surface normal holds significant importance in visual environmental perception, serving as a source of rich geometric information. However, the state-of-the-art (SoTA) surface normal estimators (SNEs) generally suffer from an unsatisfactory trade-off between efficiency and accuracy. To resolve this dilemma, this paper first presents a superfast depthto-normal translator (D2NT), which can directly translate depth images into surface normal maps without calculating 3D coordinates. We then propose a discontinuity-aware gradient (DAG) filter, which adaptively generates gradient convolution kernels to improve depth gradient estimation. Finally, we propose a surface normal refinement module that can easily be integrated into any depth-to-normal SNEs, substantially improving the surface normal estimation accuracy. Our proposed algorithm demonstrates the best accuracy among all other existing realtime SNEs and achieves the SoTA trade-off between efficiency and accuracy. 

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/d1a0d93d-5382-4235-b3a3-a6d442ae4597)

</details>

[📃 arXiv:2304](https://arxiv.org/pdf/2304.12031.pdf) | [⌨️ Code](https://github.com/fengyi233/depth-to-normal-translator/tree/main?tab=readme-ov-file) | [🌐 Project Page](https://mias.group/D2NT/)

#### <summary>NeuSurf: On-Surface Priors for Neural Surface Reconstruction from Sparse Input Views
Authors: Han Huang, Yulun Wu, Junsheng Zhou, Ge Gao, Ming Gu, Yu-Shen Liu
<details span>
<summary><b>Abstract</b></summary>
Recently, neural implicit functions have demonstrated remarkable results in the field of multi-view reconstruction. However, most existing methods are tailored for dense views and exhibit unsatisfactory performance when dealing with sparse views. Several latest methods have been proposed for generalizing implicit reconstruction to address the sparse view reconstruction task, but they still suffer from high training costs and are merely valid under carefully selected perspectives. In this paper, we propose a novel sparse view reconstruction framework that leverages on-surface priors to achieve highly faithful surface reconstruction. Specifically, we design several constraints on global geometry alignment and local geometry refinement for jointly optimizing coarse shapes and fine details. To achieve this, we train a neural network to learn a global implicit field from the on-surface points obtained from SfM and then leverage it as a coarse geometric constraint. To exploit local geometric consistency, we project on-surface points onto seen and unseen views, treating the consistent loss of projected features as a fine geometric constraint. The experimental results with DTU and BlendedMVS datasets in two prevalent sparse settings demonstrate significant improvements over the state-of-the-art methods.
 
![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/0c8516ad-c054-4d61-adc2-afc59b43ceb9)

 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.13977.pdf) | [⌨️ Code](https://github.com/leonwu0108/NeuSurf) | [🌐 Project Page](https://alvin528.github.io/NeuSurf/)


#### <summary>FouriScale: A Frequency Perspective on Training-Free High-Resolution Image Synthesis
Authors: Linjiang Huang, Rongyao Fang, Aiping Zhang, Guanglu Song, Si Liu, Yu Liu, Hongsheng Li
<details span>
<summary><b>Abstract</b></summary>
In this study, we delve into the generation of high-resolution images from pre-trained diffusion models, addressing persistent challenges, such as repetitive patterns and structural distortions, that emerge when models are applied beyond their trained resolutions. To address this issue, we introduce an innovative, training-free approach FouriScale from the perspective of frequency domain analysis. We replace the original convolutional layers in pre-trained diffusion models by incorporating a dilation technique along with a low-pass operation, intending to achieve structural consistency and scale consistency across resolutions, respectively. Further enhanced by a padding-then-crop strategy, our method can flexibly handle text-to-image generation of various aspect ratios. By using the FouriScale as guidance, our method successfully balances the structural integrity and fidelity of generated images, achieving an astonishing capacity of arbitrary-size, high-resolution, and high-quality generation. With its simplicity and compatibility, our method can provide valuable insights for future explorations into the synthesis of ultra-high-resolution images.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/9286c6c4-2d8d-415b-a784-8ac94212f575)


 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.12963.pdf) | [⌨️ Code](https://github.com/LeonHLJ/FouriScale) | [🌐 Project Page]



#### <summary>Probing the 3D Awareness of Visual Foundation Models
Authors: Mohamed El Banani, Amit Raj, Kevis-Kokitsi Maninis, Abhishek Kar, Yuanzhen Li, Michael Rubinstein, Deqing Sun, Leonidas Guibas, Justin Johnson, Varun Jampani
<details span>
<summary><b>Abstract</b></summary>
Recent advances in large-scale pretraining have yielded visual foundation models with strong capabilities. Not only can recent models generalize to arbitrary images for their training task, their intermediate representations are useful for other visual tasks such as detection and segmentation. Given that such models can classify, delineate, and localize objects in 2D, we ask whether they also represent their 3D structure? In this work, we analyze the 3D awareness of visual foundation models. We posit that 3D awareness implies that representations (1) encode the 3D structure of the scene and (2) consistently represent the surface across views. We conduct a series of experiments using task-specific probes and zero-shot inference procedures on frozen features. Our experiments reveal several limitations of the current models.
 
![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/b2c526b2-eeff-444d-a873-6e56c0106821)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.08636.pdf) | [⌨️ Code](https://github.com/mbanani/probe3d) | [🌐 Project Page]


#### <summary>FlowMap: High-Quality Camera Poses, Intrinsics, and Depth via Gradient Descent
Authors: Cameron Smith, David Charatan, Ayush Tewari, Vincent Sitzmann
<details span>
<summary><b>Abstract</b></summary>
This paper introduces FlowMap, an end-to-end differentiable method that solves for precise camera poses, camera intrinsics, and per-frame dense depth of a video sequence. Our method performs per-video gradient-descent minimization of a simple least-squares objective that compares the optical flow induced by depth, intrinsics, and poses against correspondences obtained via off-the-shelf optical flow and point tracking. Alongside the use of point tracks to encourage long-term geometric consistency, we introduce differentiable re-parameterizations of depth, intrinsics, and pose that are amenable to first-order optimization. We empirically show that camera parameters and dense depth recovered by our method enable photo-realistic novel view synthesis on 360-degree trajectories using Gaussian Splatting. Our method not only far outperforms prior gradient-descent based bundle adjustment methods, but surprisingly performs on par with COLMAP, the state-of-the-art SfM method, on the downstream task of 360-degree novel view synthesis (even though our method is purely gradient-descent based, fully differentiable, and presents a complete departure from conventional SfM).
 
![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/edaf7b9c-da76-4d15-ad96-0d68ee9fc4ba)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.15259.pdf) | [⌨️ Code](https://github.com/dcharatan/flowmap) | [🌐 Project Page]

<br>
<br>

## Pose-free

#### <summary>InstantSplat: Unbounded Sparse-view Pose-free Gaussian Splatting in 40 Seconds
Authors: Zhiwen Fan, Wenyan Cong, Kairun Wen, Kevin Wang, Jian Zhang, Xinghao Ding, Danfei Xu, Boris Ivanovic, Marco Pavone, Georgios Pavlakos, Zhangyang Wang, Yue Wang
<details span>
<summary><b>Abstract</b></summary>
While novel view synthesis (NVS) has made substantial progress in 3D computer vision, it typically requires an initial estimation of camera intrinsics and extrinsics from dense viewpoints. This pre-processing is usually conducted via a Structure-from-Motion (SfM) pipeline, a procedure that can be slow and unreliable, particularly in sparse-view scenarios with insufficient matched features for accurate reconstruction. In this work, we integrate the strengths of point-based representations (e.g., 3D Gaussian Splatting, 3D-GS) with end-to-end dense stereo models (DUSt3R) to tackle the complex yet unresolved issues in NVS under unconstrained settings, which encompasses pose-free and sparse view challenges. Our framework, InstantSplat, unifies dense stereo priors with 3D-GS to build 3D Gaussians of large-scale scenes from sparseview & pose-free images in less than 1 minute. Specifically, InstantSplat comprises a Coarse Geometric Initialization (CGI) module that swiftly establishes a preliminary scene structure and camera parameters across all training views, utilizing globally-aligned 3D point maps derived from a pre-trained dense stereo pipeline. This is followed by the Fast 3D-Gaussian Optimization (F-3DGO) module, which jointly optimizes the 3D Gaussian attributes and the initialized poses with pose regularization. Experiments conducted on the large-scale outdoor Tanks & Temples datasets demonstrate that InstantSplat significantly improves SSIM (by 32%) while concurrently reducing Absolute Trajectory Error (ATE) by 80%. These establish InstantSplat as a viable solution for scenarios involving posefree and sparse-view conditions.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/be988f2c-5843-41b1-8a28-a2a03a8f1a7b)

 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.20309.pdf) | [⌨️ Code] | [🌐 Project Page](https://instantsplat.github.io/)


#### <summary>Incremental Joint Learning of Depth, Pose and Implicit Scene Representation on Monocular Camera in Large-scale Scenes
Authors: Tianchen Deng, Nailin Wang, Chongdi Wang, Shenghai Yuan, Jingchuan Wang, Danwei Wang, Weidong Chen
<details span>
<summary><b>Abstract</b></summary>
Dense scene reconstruction for photo-realistic view synthesis has various applications, such as VR/AR, autonomous vehicles. However, most existing methods have difficulties in large-scale scenes due to three core challenges: \textit{(a) inaccurate depth input.} Accurate depth input is impossible to get in real-world large-scale scenes. \textit{(b) inaccurate pose estimation.} Most existing approaches rely on accurate pre-estimated camera poses. \textit{(c) insufficient scene representation capability.} A single global radiance field lacks the capacity to effectively scale to large-scale scenes. To this end, we propose an incremental joint learning framework, which can achieve accurate depth, pose estimation, and large-scale scene reconstruction. A vision transformer-based network is adopted as the backbone to enhance performance in scale information estimation. For pose estimation, a feature-metric bundle adjustment (FBA) method is designed for accurate and robust camera tracking in large-scale scenes. In terms of implicit scene representation, we propose an incremental scene representation method to construct the entire large-scale scene as multiple local radiance fields to enhance the scalability of 3D scene representation. Extended experiments have been conducted to demonstrate the effectiveness and accuracy of our method in depth estimation, pose estimation, and large-scale scene reconstruction.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/f206f299-4ba0-4cad-8813-397642aecc4c)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.06050.pdf) | [⌨️ Code] | [🌐 Project Page]
