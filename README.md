# AwesomeGaussian

<br>

[Surface](#Surface) | [Sparse View](#Sparse-View) | [Structured](#Structured) | [Large Scale](#Large-Scale) | [Edit](#Edit) | [SLAM](#SLAM) | [Noisy Poses](#Noisy-Poses) | [Generalizable](#Generalizable) | [High Frequency Details](#High-Frequency-Details) | [Anti-Aliasing](#Anti-Aliasing) | [Hyperspectral](#Hyperspectral) | [Event Camera](#Event-Camera) | [Others](#Others)  | [Not Gaussian](#Not-Gaussian)

<br>

#### 3D Gaussian Splatting for Real-Time Radiance Field Rendering
Authors: Bernhard Kerbl, Georgios Kopanas, Thomas Leimkühler, George Drettakis
<details span>
<summary><b>Abstract</b></summary>
Radiance Field methods have recently revolutionized novel-view synthesis of scenes captured with multiple photos or videos. However, achieving high visual quality still requires neural networks that are costly to train and render, while recent faster methods inevitably trade off speed for quality. For unbounded and complete scenes (rather than isolated objects) and 1080p resolution rendering, no current method can achieve real-time display rates. We introduce three key elements that allow us to achieve state-of-the-art visual quality while maintaining competitive training times and importantly allow high-quality real-time (>= 30 fps) novel-view synthesis at 1080p resolution. First, starting from sparse points produced during camera calibration, we represent the scene with 3D Gaussians that preserve desirable properties of continuous volumetric radiance fields for scene optimization while avoiding unnecessary computation in empty space; Second, we perform interleaved optimization/density control of the 3D Gaussians, notably optimizing anisotropic covariance to achieve an accurate representation of the scene; Third, we develop a fast visibility-aware rendering algorithm that supports anisotropic splatting and both accelerates training and allows realtime rendering. We demonstrate state-of-the-art visual quality and real-time rendering on several established datasets.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0d50e748-96c9-41b3-84cf-f6c651d2f726)


</details>

[📃 arXiv:2308](https://arxiv.org/pdf/2308.04079) | [⌨️ Code](https://github.com/graphdeco-inria/gaussian-splatting) | [🌐 Project Page](https://repo-sam.inria.fr/fungraph/3d-gaussian-splatting/)

<br>

## Surface

#### <summary>SuGaR: Surface-Aligned Gaussian Splatting for Efficient 3D Mesh Reconstruction and High-Quality Mesh Rendering
Authors: Xiaoyang Lyu, Yang-Tian Sun, Yi-Hua Huang, Xiuzhe Wu, Ziyi Yang, Yilun Chen, Jiangmiao Pang, Xiaojuan Qi
<details span>
<summary><b>Abstract</b></summary>
Existing neural implicit surface reconstruction methods have achieved impressive performance in multi-view 3D reconstruction by leveraging explicit geometry priors such as depth maps or point clouds as regularization. However, the reconstruction results still lack fine details because of the over-smoothed depth map or sparse point cloud. In this work, we propose a neural implicit surface reconstruction pipeline with guidance from 3D Gaussian Splatting to recover highly detailed surfaces. The advantage of 3D Gaussian Splatting is that it can generate dense point clouds with detailed structure. Nonetheless, a naive adoption of 3D Gaussian Splatting can fail since the generated points are the centers of 3D Gaussians that do not necessarily lie on the surface. We thus introduce a scale regularizer to pull the centers close to the surface by enforcing the 3D Gaussians to be extremely thin. Moreover, we propose to refine the point cloud from 3D Gaussians Splatting with the normal priors from the surface predicted by neural implicit models instead of using a fixed set of points as guidance. Consequently, the quality of surface reconstruction improves from the guidance of the more accurate 3D Gaussian splatting. By jointly optimizing the 3D Gaussian Splatting and the neural implicit model, our approach benefits from both representations and generates complete surfaces with intricate details. Experiments on Tanks and Temples verify the effectiveness of our proposed method.

![1713851280545](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/65393e79-6192-4c91-866b-122b29503f7e)


</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.12775.pdf) | [⌨️ Code](https://github.com/Anttwo/SuGaR?tab=readme-ov-file) | [🌐 Project Page](https://anttwo.github.io/sugar/)

#### <summary>Relightable 3D Gaussian: Real-time Point Cloud Relighting with BRDF Decomposition and Ray Tracing
Authors: Jian Gao, Chun Gu, Youtian Lin, Hao Zhu, Xun Cao, Li Zhang, Yao Yao
<details span>
<summary><b>Abstract</b></summary>
We present a novel differentiable point-based rendering framework for material and lighting decomposition from multi-view images, enabling editing, ray-tracing, and real-time relighting of the 3D point cloud. Specifically, a 3D scene is represented as a set of relightable 3D Gaussian points, where each point is additionally associated with a normal direction, BRDF parameters, and incident lights from different directions. To achieve robust lighting estimation, we further divide incident lights of each point into global and local components, as well as view-dependent visibilities. The 3D scene is optimized through the 3D Gaussian Splatting technique while BRDF and lighting are decomposed by physically-based differentiable rendering. Moreover, we introduce an innovative point-based ray-tracing approach based on the bounding volume hierarchy for efficient visibility baking, enabling real-time rendering and relighting of 3D Gaussian points with accurate shadow effects. Extensive experiments demonstrate improved BRDF estimation and novel view rendering results compared to state-of-the-art material estimation approaches. Our framework showcases the potential to revolutionize the mesh-based graphics pipeline with a relightable, traceable, and editable rendering pipeline solely based on point cloud.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/b1901133-6909-467f-921d-89f113218b06)


</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.16043) | [⌨️ Code](https://github.com/NJU-3DV/Relightable3DGaussian) | [🌐 Project Page](https://nju-3dv.github.io/projects/Relightable3DGaussian/)




#### <summary>GS-IR: 3D Gaussian Splatting for Inverse Rendering
Authors: Zhihao Liang, Qi Zhang, Ying Feng, Ying Shan, Kui Jia
<details span>
<summary><b>Abstract</b></summary>
We propose GS-IR, a novel inverse rendering approach based on 3D Gaussian Splatting (GS) that leverages forward mapping volume rendering to achieve photorealistic novel view synthesis and relighting results. Unlike previous works that use implicit neural representations and volume rendering (e.g. NeRF), which suffer from low expressive power and high computational complexity, we extend GS, a top-performance representation for novel view synthesis, to estimate scene geometry, surface material, and environment illumination from multi-view images captured under unknown lighting conditions. There are two main problems when introducing GS to inverse rendering: 1) GS does not support producing plausible normal natively; 2) forward mapping (e.g. rasterization and splatting) cannot trace the occlusion like backward mapping (e.g. ray tracing). To address these challenges, our GS-IR proposes an efficient optimization scheme that incorporates a depth-derivation-based regularization for normal estimation and a baking-based occlusion to model indirect lighting. The flexible and expressive GS representation allows us to achieve fast and compact geometry reconstruction, photorealistic novel view synthesis, and effective physically-based rendering. We demonstrate the superiority of our method over baseline methods through qualitative and quantitative evaluations on various challenging scenes.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/b1901133-6909-467f-921d-89f113218b06)


</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.16473.pdf) | [⌨️ Code](https://github.com/lzhnb/GS-IR) | [🌐 Project Page](https://lzhnb.github.io/project-pages/gs-ir.html)




#### <summary>NeuSG: Neural Implicit Surface Reconstruction with 3D Gaussian Splatting Guidance
Authors: Hanlin Chen, Chen Li, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
Existing neural implicit surface reconstruction methods have achieved impressive performance in multi-view 3D reconstruction by leveraging explicit geometry priors such as depth maps or point clouds as regularization. However, the reconstruction results still lack fine details because of the over-smoothed depth map or sparse point cloud. In this work, we propose a neural implicit surface reconstruction pipeline with guidance from 3D Gaussian Splatting to recover highly detailed surfaces. The advantage of 3D Gaussian Splatting is that it can generate dense point clouds with detailed structure. Nonetheless, a naive adoption of 3D Gaussian Splatting can fail since the generated points are the centers of 3D Gaussians that do not necessarily lie on the surface. We thus introduce a scale regularizer to pull the centers close to the surface by enforcing the 3D Gaussians to be extremely thin. Moreover, we propose to refine the point cloud from 3D Gaussians Splatting with the normal priors from the surface predicted by neural implicit models instead of using a fixed set of points as guidance. Consequently, the quality of surface reconstruction improves from the guidance of the more accurate 3D Gaussian splatting. By jointly optimizing the 3D Gaussian Splatting and the neural implicit model, our approach benefits from both representations and generates complete surfaces with intricate details. Experiments on Tanks and Temples verify the effectiveness of our proposed method.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/1de18275-365a-42cb-b42d-abdab5f9aa29)

 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.00846.pdf) | [⌨️ Code] | [🌐 Project Page]

#### <summary>GIR: 3D Gaussian Inverse Rendering for Relightable Scene Factorization
Authors: Yahao Shi, Yanmin Wu, Chenming Wu, Xing Liu, Chen Zhao, Haocheng Feng, Jingtuo Liu, Liangjun Zhang, Jian Zhang, Bin Zhou, Errui Ding, Jingdong Wang
<details span>
<summary><b>Abstract</b></summary>
This paper presents GIR, a 3D Gaussian Inverse Rendering method for relightable scene factorization. Compared to existing methods leveraging discrete meshes or neural implicit fields for inverse rendering, our method utilizes 3D Gaussians to estimate the material properties, illumination, and geometry of an object from multi-view images. Our study is motivated by the evidence showing that 3D Gaussian is a more promising backbone than neural fields in terms of performance, versatility, and efficiency. In this paper, we aim to answer the question: ``How can 3D Gaussian be applied to improve the performance of inverse rendering?'' To address the complexity of estimating normals based on discrete and often in-homogeneous distributed 3D Gaussian representations, we proposed an efficient self-regularization method that facilitates the modeling of surface normals without the need for additional supervision. To reconstruct indirect illumination, we propose an approach that simulates ray tracing. Extensive experiments demonstrate our proposed GIR's superior performance over existing methods across multiple tasks on a variety of widely used datasets in inverse rendering. This substantiates its efficacy and broad applicability, highlighting its potential as an influential tool in relighting and reconstruction.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/95675684-a189-428d-b83a-a4287a8db3d8)
 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.05133) | [⌨️ Code] | [🌐 Project Page](https://3dgir.github.io/)




#### <summary>GaussianPro: 3D Gaussian Splatting with Progressive Propagation
Authors: Kai Cheng, Xiaoxiao Long, Kaizhi Yang, Yao Yao, Wei Yin, Yuexin Ma, Wenping Wang, Xuejin Chen
<details span>
<summary><b>Abstract</b></summary>
The advent of 3D Gaussian Splatting (3DGS) has recently brought about a revolution in the field of neural rendering, facilitating high-quality renderings at real-time speed. However, 3DGS heavily depends on the initialized point cloud produced by Structure-from-Motion (SfM) techniques. When tackling with large-scale scenes that unavoidably contain texture-less surfaces, the SfM techniques always fail to produce enough points in these surfaces and cannot provide good initialization for 3DGS. As a result, 3DGS suffers from difficult optimization and low-quality renderings. In this paper, inspired by classical multi-view stereo (MVS) techniques, we propose GaussianPro, a novel method that applies a progressive propagation strategy to guide the densification of the 3D Gaussians. Compared to the simple split and clone strategies used in 3DGS, our method leverages the priors of the existing reconstructed geometries of the scene and patch matching techniques to produce new Gaussians with accurate positions and orientations. Experiments on both large-scale and small-scale scenes validate the effectiveness of our method, where our method significantly surpasses 3DGS on the Waymo dataset, exhibiting an improvement of 1.15dB in terms of PSNR.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/82401777-304d-4586-a0f8-6468b760b99b)


</details>


[📃 arXiv:2402](https://arxiv.org/pdf/2402.14650.pdf) | [⌨️ Code](https://github.com/kcheng1021/GaussianPro) | [🌐 Project Page](https://kcheng1021.github.io/gaussianpro.github.io/)




#### <summary>GSDF: 3DGS Meets SDF for Improved Rendering and Reconstruction
Authors: Mulin Yu, Tao Lu, Linning Xu, Lihan Jiang, Yuanbo Xiangli, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
Presenting a 3D scene from multiview images remains a core and long-standing challenge in computer vision and computer graphics. Two main requirements lie in rendering and reconstruction. Notably, SOTA rendering quality is usually achieved with neural volumetric rendering techniques, which rely on aggregated point/primitive-wise color and neglect the underlying scene geometry. Learning of neural implicit surfaces is sparked from the success of neural rendering. Current works either constrain the distribution of density fields or the shape of primitives, resulting in degraded rendering quality and flaws on the learned scene surfaces. The efficacy of such methods is limited by the inherent constraints of the chosen neural representation, which struggles to capture fine surface details, especially for larger, more intricate scenes. To address these issues, we introduce GSDF, a novel dual-branch architecture that combines the benefits of a flexible and efficient 3D Gaussian Splatting (3DGS) representation with neural Signed Distance Fields (SDF). The core idea is to leverage and enhance the strengths of each branch while alleviating their limitation through mutual guidance and joint supervision. We show on diverse scenes that our design unlocks the potential for more accurate and detailed surface reconstructions, and at the meantime benefits 3DGS rendering with structures that are more aligned with the underlying geometry.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/5663557f-fd3a-4574-a6a8-c98e810a3c04)


</details>


[📃 arXiv:2403](https://arxiv.org/pdf/2403.16964) | [⌨️ Code](https://github.com/city-super/GSDF) | [🌐 Project Page](https://city-super.github.io/GSDF/)

#### <summary>2D Gaussian Splatting for Geometrically Accurate Radiance Fields
Authors: Binbin Huang, Zehao Yu, Anpei Chen, Andreas Geiger, Shenghua Gao
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has recently revolutionized radiance field reconstruction, achieving high quality novel view synthesis and fast rendering speed. However, 3DGS fails to accurately represent surfaces due to the multi-view inconsistent nature of 3D Gaussians. We present 2D Gaussian Splatting (2DGS), a novel approach to model and reconstruct geometrically accurate radiance fields from multi-view images. Our key idea is to collapse the 3D volume into a set of 2D oriented planar Gaussian disks. Unlike 3D Gaussians, 2D Gaussians provide view-consistent geometry while modeling surfaces intrinsically. To accurately recover thin surfaces and achieve stable optimization, we introduce a perspective-accurate 2D splatting process utilizing ray-splat intersection and rasterization. Additionally, we incorporate depth distortion and normal consistency terms to further enhance the quality of the reconstructions. We demonstrate that our differentiable renderer allows for noise-free and detailed geometry reconstruction while maintaining competitive appearance quality, fast training speed, and real-time rendering. Our code will be made publicly available.


</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.17888.pdf) | [⌨️ Code](https://github.com/hbb1/2d-gaussian-splatting) | [🌐 Project Page](https://surfsplatting.github.io/) | [(unofficial)⌨️ Code](https://github.com/hugoycj/2.5d-gaussian-splatting)





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




#### <summary>3D Gaussian Splatting with Deferred Reflection
Authors: Keyang Ye, Qiming Hou, Kun Zhou
<details span>
<summary><b>Abstract</b></summary>
The advent of neural and Gaussian-based radiance field methods have achieved great success in the field of novel view synthesis. However, specular reflection remains non-trivial, as the high frequency radiance field is notoriously difficult to fit stably and accurately. We present a deferred shading method to effectively render specular reflection with Gaussian splatting. The key challenge comes from the environment map reflection model, which requires accurate surface normal while simultaneously bottlenecks normal estimation with discontinuous gradients. We leverage the per-pixel reflection gradients generated by deferred shading to bridge the optimization process of neighboring Gaussians, allowing nearly correct normal estimations to gradually propagate and eventually spread over all reflective objects. Our method significantly outperforms state-of-the-art techniques and concurrent work in synthesizing high-quality specular reflection effects, demonstrating a consistent improvement of peak signal-to-noise ratio (PSNR) for both synthetic and real-world scenes, while running at a frame rate almost identical to vanilla Gaussian splatting.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/29d212a2-ae41-47b6-a7fc-2fa242e1f96c)

</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.18454) | [⌨️ Code] | [🌐 Project Page]

#### <summary>High-quality Surface Reconstruction using Gaussian Surfels
Authors: Pinxuan Dai, Jiamin Xu, Wenxiang Xie, Xinguo Liu, Huamin Wang, Weiwei Xu
<details span>
<summary><b>Abstract</b></summary>
We propose a novel point-based representation, Gaussian surfels, to combine the advantages of the flexible optimization procedure in 3D Gaussian points and the surface alignment property of surfels. This is achieved by directly setting the z-scale of 3D Gaussian points to 0, effectively flattening the original 3D ellipsoid into a 2D ellipse. Such a design provides clear guidance to the optimizer. By treating the local z-axis as the normal direction, it greatly improves optimization stability and surface alignment. While the derivatives to the local z-axis computed from the covariance matrix are zero in this setting, we design a self-supervised normal-depth consistency loss to remedy this issue. Monocular normal priors and foreground masks are incorporated to enhance the reconstruction quality, mitigating issues related to highlights and background. We propose a volumetric cutting method to aggregate the information of Gaussian surfels so as to remove erroneous points in depth maps generated by alpha blending. Finally, we apply screened Poisson reconstruction method to the fused depth maps to extract the surface mesh. Experimental results show that our method demonstrates superior performance in surface reconstruction compared to state-of-the-art neural volume rendering and point-based rendering methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/809c4254-3e9d-41e5-83cc-873f4e4fe332)

</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.17774) | [⌨️ Code](https://github.com/turandai/gaussian_surfels) | [🌐 Project Page](https://turandai.github.io/projects/gaussian_surfels/index.html)


#### <summary>Direct Learning of Mesh and Appearance via 3D Gaussian Splatting
Authors: Ancheng Lin, Jun Li
<details span>
<summary><b>Abstract</b></summary>
Accurately reconstructing a 3D scene including explicit geometry information is both attractive and challenging. Geometry reconstruction can benefit from incorporating differentiable appearance models, such as Neural Radiance Fields and 3D Gaussian Splatting (3DGS). In this work, we propose a learnable scene model that incorporates 3DGS with an explicit geometry representation, namely a mesh. Our model learns the mesh and appearance in an end-to-end manner, where we bind 3D Gaussians to the mesh faces and perform differentiable rendering of 3DGS to obtain photometric supervision. The model creates an effective information pathway to supervise the learning of the scene, including the mesh. Experimental results demonstrate that the learned scene model not only achieves state-of-the-art rendering quality but also supports manipulation using the explicit mesh. In addition, our model has a unique advantage in adapting to scene updates, thanks to the end-to-end learning of both mesh and appearance.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/06cbf0f1-83bc-491e-b1d2-ae5294ce4864)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.06945) | [⌨️ Code] | [🌐 Project Page]



#### <summary>AtomGS: Atomizing Gaussian Splatting for High-Fidelity Radiance Field
Authors: Rong Liu, Rui Xu, Yue Hu, Meida Chen, Andrew Feng
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has recently advanced radiance field reconstruction by offering superior capabilities for novel view synthesis and real-time rendering speed. However, its strategy of blending optimization and adaptive density control might lead to sub-optimal results; it can sometimes yield noisy geometry and blurry artifacts due to prioritizing optimizing large Gaussians at the cost of adequately densifying smaller ones. To address this, we introduce AtomGS, consisting of Atomized Proliferation and Geometry-Guided Optimization. The Atomized Proliferation constrains ellipsoid Gaussians of various sizes into more uniform-sized Atom Gaussians. The strategy enhances the representation of areas with fine features by placing greater emphasis on densification in accordance with scene details. In addition, we proposed a Geometry-Guided Optimization approach that incorporates an Edge-Aware Normal Loss. This optimization method effectively smooths flat surfaces while preserving intricate details. Our evaluation shows that AtomGS outperforms existing state-of-the-art methods in rendering quality. Additionally, it achieves competitive accuracy in geometry reconstruction and offers a significant improvement in training speed over other SDF-based methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/8d35eeff-74da-4ecf-a9c0-d38550cf938f)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12369) | [⌨️ Code](https://github.com/RongLiu-Leo/AtomGS) | [🌐 Project Page](https://rongliu-leo.github.io/AtomGS/)

#### <summary>Vidu4D: Single Generated Video to High-Fidelity 4D Reconstruction with Dynamic Gaussian Surfels
Authors: Yikai Wang, Xinzhou Wang, Zilong Chen, Zhengyi Wang, Fuchun Sun, Jun Zhu
<details span>
<summary><b>Abstract</b></summary>
Video generative models are receiving particular attention given their ability to generate realistic and imaginative frames. Besides, these models are also observed to exhibit strong 3D consistency, significantly enhancing their potential to act as world simulators. In this work, we present Vidu4D, a novel reconstruction model that excels in accurately reconstructing 4D (i.e., sequential 3D) representations from single generated videos, addressing challenges associated with non-rigidity and frame distortion. This capability is pivotal for creating high-fidelity virtual contents that maintain both spatial and temporal coherence. At the core of Vidu4D is our proposed Dynamic Gaussian Surfels (DGS) technique. DGS optimizes time-varying warping functions to transform Gaussian surfels (surface elements) from a static state to a dynamically warped state. This transformation enables a precise depiction of motion and deformation over time. To preserve the structural integrity of surface-aligned Gaussian surfels, we design the warped-state geometric regularization based on continuous warping fields for estimating normals. Additionally, we learn refinements on rotation and scaling parameters of Gaussian surfels, which significantly alleviates texture flickering during the warping process and enhances the capture of fine-grained appearance details. Vidu4D also contains a novel initialization state that provides a proper start for the warping fields in DGS. Equipping Vidu4D with an existing video generative model, the overall framework demonstrates high-fidelity text-to-4D generation in both appearance and geometry.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/1cc231e8-9b08-4708-a65b-d33894d96d35)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16822) | [⌨️ Code](https://github.com/yikaiw/vidu4d) | [🌐 Project Page](https://vidu4d-dgs.github.io/)


#### <summary>GaussianRoom: Improving 3D Gaussian Splatting with SDF Guidance and Monocular Cues for Indoor Scene Reconstruction
Authors: Haodong Xiang, Xinghui Li, Xiansong Lai, Wanting Zhang, Zhichao Liao, Kai Cheng, Xueping Liu
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting(3DGS) has revolutionized neural rendering with its high-quality rendering and real-time speed. However, when it comes to indoor scenes with a significant number of textureless areas, 3DGS yields incomplete and noisy reconstruction results due to the poor initialization of the point cloud and under-constrained optimization. Inspired by the continuity of signed distance field (SDF), which naturally has advantages in modeling surfaces, we present a unified optimizing framework integrating neural SDF with 3DGS. This framework incorporates a learnable neural SDF field to guide the densification and pruning of Gaussians, enabling Gaussians to accurately model scenes even with poor initialized point clouds. At the same time, the geometry represented by Gaussians improves the efficiency of the SDF field by piloting its point sampling. Additionally, we regularize the optimization with normal and edge priors to eliminate geometry ambiguity in textureless areas and improve the details. Extensive experiments in ScanNet and ScanNet++ show that our method achieves state-of-the-art performance in both surface reconstruction and novel view synthesis.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0a64d87f-d434-41e9-978e-bde39acea4e5)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.19671) | [⌨️ Code](https://github.com/xhd0612/GaussianRoom) | [🌐 Project Page](https://xhd0612.github.io/GaussianRoom.github.io/)


#### <summary>DreamMat: High-quality PBR Material Generation with Geometry- and Light-aware Diffusion Models
Authors: Yuqing Zhang, Yuan Liu, Zhiyu Xie, Lei Yang, Zhongyuan Liu, Mengzhou Yang, Runze Zhang, Qilong Kou, Cheng Lin, Wenping Wang, Xiaogang Jin
<details span>
<summary><b>Abstract</b></summary>
2D diffusion model, which often contains unwanted baked-in shading effects and results in unrealistic rendering effects in the downstream applications. Generating Physically Based Rendering (PBR) materials instead of just RGB textures would be a promising solution. However, directly distilling the PBR material parameters from 2D diffusion models still suffers from incorrect material decomposition, such as baked-in shading effects in albedo. We introduce DreamMat, an innovative approach to resolve the aforementioned problem, to generate high-quality PBR materials from text descriptions. We find out that the main reason for the incorrect material distillation is that large-scale 2D diffusion models are only trained to generate final shading colors, resulting in insufficient constraints on material decomposition during distillation. To tackle this problem, we first finetune a new light-aware 2D diffusion model to condition on a given lighting environment and generate the shading results on this specific lighting condition. Then, by applying the same environment lights in the material distillation, DreamMat can generate high-quality PBR materials that are not only consistent with the given geometry but also free from any baked-in shading effects in albedo. Extensive experiments demonstrate that the materials produced through our methods exhibit greater visual appeal to users and achieve significantly superior rendering quality compared to baseline methods, which are preferable for downstream tasks such as game and film production.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4340dd21-05dc-468b-9450-c8dd06af7863)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17176) | [⌨️ Code](https://github.com/zzzyuqing/DreamMat) | [🌐 Project Page](https://zzzyuqing.github.io/dreammat.github.io/)



#### <summary>RaDe-GS: Rasterizing Depth in Gaussian Splatting
Authors: Baowen Zhang, Chuan Fang, Rakesh Shrestha, Yixun Liang, Xiaoxiao Long, Ping Tan
<details span>
<summary><b>Abstract</b></summary>
Gaussian Splatting (GS) has proven to be highly effective in novel view synthesis, achieving high-quality and real-time rendering. However, its potential for reconstructing detailed 3D shapes has not been fully explored. Existing methods often suffer from limited shape accuracy due to the discrete and unstructured nature of Gaussian splats, which complicates the shape extraction. While recent techniques like 2D GS have attempted to improve shape reconstruction, they often reformulate the Gaussian primitives in ways that reduce both rendering quality and computational efficiency. To address these problems, our work introduces a rasterized approach to render the depth maps and surface normal maps of general 3D Gaussian splats. Our method not only significantly enhances shape reconstruction accuracy but also maintains the computational efficiency intrinsic to Gaussian Splatting. Our approach achieves a Chamfer distance error comparable to NeuraLangelo on the DTU dataset and similar training and rendering time as traditional Gaussian Splatting on the Tanks & Temples dataset. Our method is a significant advancement in Gaussian Splatting and can be directly integrated into existing Gaussian Splatting-based methods.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/86c35cf2-d3b7-4e10-a4fd-26e7e0ed47c5)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.01467) | [⌨️ Code](https://github.com/BaowenZ/RaDe-GS) | [🌐 Project Page](https://baowenz.github.io/radegs/)


#### <summary>PGSR: Planar-based Gaussian Splatting for Efficient and High-Fidelity Surface Reconstruction
Authors: Danpeng Chen, Hai Li, Weicai Ye, Yifan Wang, Weijian Xie, Shangjin Zhai, Nan Wang, Haomin Liu, Hujun Bao, Guofeng Zhang
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has attracted widespread attention due to its high-quality rendering, and ultra-fast training and rendering speed. However, due to the unstructured and irregular nature of Gaussian point clouds, it is difficult to guarantee geometric reconstruction accuracy and multi-view consistency simply by relying on image reconstruction loss. Although many studies on surface reconstruction based on 3DGS have emerged recently, the quality of their meshes is generally unsatisfactory. To address this problem, we propose a fast planar-based Gaussian splatting reconstruction representation (PGSR) to achieve high-fidelity surface reconstruction while ensuring high-quality rendering. Specifically, we first introduce an unbiased depth rendering method, which directly renders the distance from the camera origin to the Gaussian plane and the corresponding normal map based on the Gaussian distribution of the point cloud, and divides the two to obtain the unbiased depth. We then introduce single-view geometric, multi-view photometric, and geometric regularization to preserve global geometric accuracy. We also propose a camera exposure compensation model to cope with scenes with large illumination variations. Experiments on indoor and outdoor scenes show that our method achieves fast training and rendering while maintaining high-fidelity rendering and geometric reconstruction, outperforming 3DGS-based and NeRF-based methods.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/65dcf5d4-93a8-4fa9-9d5a-23252ed35dcf)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.06521) | [⌨️ Code](https://github.com/zju3dv/PGSR) | [🌐 Project Page](https://zju3dv.github.io/pgsr/)


#### <summary>VCR-GauS: View Consistent Depth-Normal Regularizer for Gaussian Surface Reconstruction
Authors: Hanlin Chen, Fangyin Wei, Chen Li, Tianxin Huang, Yunsong Wang, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
Although 3D Gaussian Splatting has been widely studied because of its realistic and efficient novel-view synthesis, it is still challenging to extract a high-quality surface from the point-based representation. Previous works improve the surface by incorporating geometric priors from the off-the-shelf normal estimator. However, there are two main limitations: 1) Supervising normal rendered from 3D Gaussians updates only the rotation parameter while neglecting other geometric parameters; 2) The inconsistency of predicted normal maps across multiple views may lead to severe reconstruction artifacts. In this paper, we propose a Depth-Normal regularizer that directly couples normal with other geometric parameters, leading to full updates of the geometric parameters from normal regularization. We further propose a confidence term to mitigate inconsistencies of normal predictions across multiple views. Moreover, we also introduce a densification and splitting strategy to regularize the size and distribution of 3D Gaussians for more accurate surface modeling. Compared with Gaussian-based baselines, experiments show that our approach obtains better reconstruction quality and maintains competitive appearance quality at faster training speed and 100+ FPS rendering. Our code will be made open-source upon paper acceptance.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/69bbb5e9-b6b2-4a6d-bb3f-a7d9be950bbf)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.05774) | [⌨️ Code](https://github.com/HLinChen/VCR-GauS) | [🌐 Project Page](https://hlinchen.github.io/projects/VCR-GauS/)


#### <summary>Trim 3D Gaussian Splatting for Accurate Geometry Representation
Authors: Lue Fan, Yuxue Yang, Minxing Li, Hongsheng Li, Zhaoxiang Zhang
<details span>
<summary><b>Abstract</b></summary>
In this paper, we introduce Trim 3D Gaussian Splatting (TrimGS) to reconstruct accurate 3D geometry from images. Previous arts for geometry reconstruction from 3D Gaussians mainly focus on exploring strong geometry regularization. Instead, from a fresh perspective, we propose to obtain accurate 3D geometry of a scene by Gaussian trimming, which selectively removes the inaccurate geometry while preserving accurate structures. To achieve this, we analyze the contributions of individual 3D Gaussians and propose a contribution-based trimming strategy to remove the redundant or inaccurate Gaussians. Furthermore, our experimental and theoretical analyses reveal that a relatively small Gaussian scale is a non-negligible factor in representing and optimizing the intricate details. Therefore the proposed TrimGS maintains relatively small Gaussian scales. In addition, TrimGS is also compatible with the effective geometry regularization strategies in previous arts. When combined with the original 3DGS and the state-of-the-art 2DGS, TrimGS consistently yields more accurate geometry and higher perceptual quality.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/c9fac592-08e5-45ce-924f-9f270d1e185f)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07499) | [⌨️ Code](https://github.com/YuxueYang1204/TrimGS) | [🌐 Project Page](https://trimgs.github.io/)

#### <summary>Effective Rank Analysis and Regularization for Enhanced 3D Gaussian Splatting
Authors: Junha Hyung, Susung Hong, Sungwon Hwang, Jaeseong Lee, Jaegul Choo, Jin-Hwa Kim
<details span>
<summary><b>Abstract</b></summary>
3D reconstruction from multi-view images is one of the fundamental challenges in computer vision and graphics. Recently, 3D Gaussian Splatting (3DGS) has emerged as a promising technique capable of real-time rendering with high-quality 3D reconstruction. This method utilizes 3D Gaussian representation and tile-based splatting techniques, bypassing the expensive neural field querying. Despite its potential, 3DGS encounters challenges, including needle-like artifacts, suboptimal geometries, and inaccurate normals, due to the Gaussians converging into anisotropic Gaussians with one dominant variance. We propose using effective rank analysis to examine the shape statistics of 3D Gaussian primitives, and identify the Gaussians indeed converge into needle-like shapes with the effective rank 1. To address this, we introduce effective rank as a regularization, which constrains the structure of the Gaussians. Our new regularization method enhances normal and geometry reconstruction while reducing needle-like artifacts. The approach can be integrated as an add-on module to other 3DGS variants, improving their quality without compromising visual fidelity.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/035d5962-97ce-4621-9e9d-370687a6b0f1)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.11672) | [⌨️ Code] | [🌐 Project Page]

#### <summary>GS-Octree: Octree-based 3D Gaussian Splatting for Robust Object-level 3D Reconstruction Under Strong Lighting
Authors: Jiaze Li, Zhengyu Wen, Luo Zhang, Jiangbei Hu, Fei Hou, Zhebin Zhang, Ying He
<details span>
<summary><b>Abstract</b></summary>
The 3D Gaussian Splatting technique has significantly advanced the construction of radiance fields from multi-view images, enabling real-time rendering. While point-based rasterization effectively reduces computational demands for rendering, it often struggles to accurately reconstruct the geometry of the target object, especially under strong lighting. To address this challenge, we introduce a novel approach that combines octree-based implicit surface representations with Gaussian splatting. Our method consists of four stages. Initially, it reconstructs a signed distance field (SDF) and a radiance field through volume rendering, encoding them in a low-resolution octree. The initial SDF represents the coarse geometry of the target object. Subsequently, it introduces 3D Gaussians as additional degrees of freedom, which are guided by the SDF. In the third stage, the optimized Gaussians further improve the accuracy of the SDF, allowing it to recover finer geometric details compared to the initial SDF obtained in the first stage. Finally, it adopts the refined SDF to further optimize the 3D Gaussians via splatting, eliminating those that contribute little to visual appearance. Experimental results show that our method, which leverages the distribution of 3D Gaussians with SDFs, reconstructs more accurate geometry, particularly in images with specular highlights caused by strong lighting.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/5359fe1c-4052-4477-8279-62b67cd01002)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.18199) | [⌨️ Code] | [🌐 Project Page]

#### <summary>MVG-Splatting: Multi-View Guided Gaussian Splatting with Adaptive Quantile-Based Geometric Consistency Densification
Authors: Zhuoxiao Li, Shanliang Yao, Yijie Chu, Angel F. Garcia-Fernandez, Yong Yue, Eng Gee Lim, Xiaohui Zhu
<details span>
<summary><b>Abstract</b></summary>
In the rapidly evolving field of 3D reconstruction, 3D Gaussian Splatting (3DGS) and 2D Gaussian Splatting (2DGS) represent significant advancements. Although 2DGS compresses 3D Gaussian primitives into 2D Gaussian surfels to effectively enhance mesh extraction quality, this compression can potentially lead to a decrease in rendering quality. Additionally, unreliable densification processes and the calculation of depth through the accumulation of opacity can compromise the detail of mesh extraction. To address this issue, we introduce MVG-Splatting, a solution guided by Multi-View considerations. Specifically, we integrate an optimized method for calculating normals, which, combined with image gradients, helps rectify inconsistencies in the original depth computations. Additionally, utilizing projection strategies akin to those in Multi-View Stereo (MVS), we propose an adaptive quantile-based method that dynamically determines the level of additional densification guided by depth maps, from coarse to fine detail. Experimental evidence demonstrates that our method not only resolves the issues of rendering quality degradation caused by depth discrepancies but also facilitates direct mesh extraction from dense Gaussian point clouds using the Marching Cubes algorithm. This approach significantly enhances the overall fidelity and accuracy of the 3D reconstruction process, ensuring that both the geometric details and visual quality.



</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.11840) | [⌨️ Code] | [🌐 Project Page](https://mvgsplatting.github.io/)

#### <summary>DHGS: Decoupled Hybrid Gaussian Splatting for Driving Scene
Authors: Xi Shi, Lingli Chen, Peng Wei, Xi Wu, Tian Jiang, Yonggang Luo, Lecheng Xie
<details span>
<summary><b>Abstract</b></summary>
Existing Gaussian splatting methods struggle to achieve satisfactory novel view synthesis in driving scenes due to the lack of crafty design and geometric constraints of related elements. This paper introduces a novel method called Decoupled Hybrid Gaussian Splatting (DHGS), which aims at promoting the rendering quality of novel view synthesis for driving scenes. The novelty of this work lies in the decoupled and hybrid pixel-level blender for road and non-road layers, without conventional unified differentiable rendering logic for the entire scene, meanwhile maintaining consistent and continuous superimposition through the proposed depth-ordered rendering strategy. Beyond that, an implicit road representation comprised of Signed Distance Field (SDF) is trained to supervise the road surface with subtle geometric attributes. Accompanied by the use of auxiliary transmittance loss and consistency loss, novel images with imperceptible boundary and elevated fidelity are ultimately obtained. Substantial experiments on Waymo dataset prove that DHGS outperforms the state-of-the-art methods.

![image](https://github.com/user-attachments/assets/ba88a8cf-b324-40d8-a0b3-7de6892ea80f)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.16600) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Integrating Meshes and 3D Gaussians for Indoor Scene Reconstruction with SAM Mask Guidance
Authors: Jiyeop Kim, Jongwoo Lim
<details span>
<summary><b>Abstract</b></summary>
We present a novel approach for 3D indoor scene reconstruction that combines 3D Gaussian Splatting (3DGS) with mesh representations. We use meshes for the room layout of the indoor scene, such as walls, ceilings, and floors, while employing 3D Gaussians for other objects. This hybrid approach leverages the strengths of both representations, offering enhanced flexibility and ease of editing. However, joint training of meshes and 3D Gaussians is challenging because it is not clear which primitive should affect which part of the rendered image. Objects close to the room layout often struggle during training, particularly when the room layout is textureless, which can lead to incorrect optimizations and unnecessary 3D Gaussians. To overcome these challenges, we employ Segment Anything Model (SAM) to guide the selection of primitives. The SAM mask loss enforces each instance to be represented by either Gaussians or meshes, ensuring clear separation and stable training. Furthermore, we introduce an additional densification stage without resetting the opacity after the standard densification. This stage mitigates the degradation of image quality caused by a limited number of 3D Gaussians after the standard densification.

![image](https://github.com/user-attachments/assets/da41901d-cff1-421c-a147-24c5f4ecc74e)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.16173) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Surface Reconstruction from 3D Gaussian Splatting via Local Structural Hints
Authors: Qianyi Wu, Jianmin Zheng, Jianfei Cai   
<details span>
<summary><b>Abstract</b></summary>
This paper presents a novel approach for surface mesh reconstruction from 3D Gaussian Splatting (3DGS), a technique renowned for its efficiency in novel view synthesis but challenged for surface reconstruction. The key obstacle is the lack of geometry hints to regulate the optimization of millions of unorganized Gaussian blobs to align to the true surface. This paper introduces local structural hints during training to address the challenge. We first leverage the prior knowledge from monocular normal and depth estimations to refine the covariance and mean of Gaussian primitives, enhancing their organization and providing crucial normal information for surface extraction. However, due to the highly discrete nature of Gaussian primitives, such geometry guidance remains insufficient for the alignment with the true surface. We then propose to construct a signed distance field by a moving least square (MLS) function over the Gaussians in each local region. More importantly, we further propose to jointly learn a neural implicit network to mimic and regularize the MLS function. The joint optimization helps the optimization of Gaussian Splatting towards accurate surface alignment. Extensive experimental results demonstrate the effectiveness of our method in achieving superior mesh quality compared with the SoTA surface reconstruction for 3DGS.

![image](https://github.com/user-attachments/assets/7e8504c0-8b00-4adc-bc76-9556653d03d0)


</details>

[📃 arXiv:24xx] | [⌨️ Code](https://github.com/QianyiWu/GSRec/tree/main) | [🌐 Project Page](https://wuqianyi.top/gsrec)

#### <summary>Spurfies: Sparse Surface Reconstruction using Local Geometry Priors
>*Local Prior*

Authors: Kevin Raj, Christopher Wewer, Raza Yunus, Eddy Ilg, Jan Eric Lenssen
<details span>
<summary><b>Abstract</b></summary>
We introduce Spurfies, a novel method for sparse-view surface reconstruction that disentangles appearance and geometry information to utilize local geometry priors trained on synthetic data. Recent research heavily focuses on 3D reconstruction using dense multi-view setups, typically requiring hundreds of images. However, these methods often struggle with few-view scenarios. Existing sparse-view reconstruction techniques often rely on multi-view stereo networks that need to learn joint priors for geometry and appearance from a large amount of data. In contrast, we introduce a neural point representation that disentangles geometry and appearance to train a local geometry prior using a subset of the synthetic ShapeNet dataset only. During inference, we utilize this surface prior as additional constraint for surface and appearance reconstruction from sparse input views via differentiable volume rendering, restricting the space of possible solutions. We validate the effectiveness of our method on the DTU dataset and demonstrate that it outperforms previous state of the art by 35% in surface quality while achieving competitive novel view synthesis quality. Moreover, in contrast to previous works, our method can be applied to larger, unbounded scenes, such as Mip-NeRF 360.

![image](https://github.com/user-attachments/assets/8d5e307d-ad97-477e-af27-1688a4794f55)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.16544) | [⌨️ Code] | [🌐 Project Page](https://geometric-rl.mpi-inf.mpg.de/spurfies/)

#### <summary>Space-time 2D Gaussian Splatting for Accurate Surface Reconstruction under Complex Dynamic Scenes


Authors: Shuo Wang, Binbin Huang, Ruoyu Wang, Shenghua Gao
<details span>
<summary><b>Abstract</b></summary>
Previous surface reconstruction methods either suffer from low geometric accuracy or lengthy training times when dealing with real-world complex dynamic scenes involving multi-person activities, and human-object interactions. To tackle the dynamic contents and the occlusions in complex scenes, we present a space-time 2D Gaussian Splatting approach. Specifically, to improve geometric quality in dynamic scenes, we learn canonical 2D Gaussian splats and deform these 2D Gaussian splats while enforcing the disks of the Gaussian located on the surface of the objects by introducing depth and normal regularizers. Further, to tackle the occlusion issues in complex scenes, we introduce a compositional opacity deformation strategy, which further reduces the surface recovery of those occluded areas. Experiments on real-world sparse-view video datasets and monocular dynamic datasets demonstrate that our reconstructions outperform state-of-the-art methods, especially for the surface of the details. 

![image](https://github.com/user-attachments/assets/44d30691-1263-4b4e-b898-40db0ad8072b)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2409.18852) | [⌨️ Code](https://github.com/tb2-sy/st-2dgs) | [🌐 Project Page](https://tb2-sy.github.io/st-2dgs/)

<br>
<br>

## Sparse View

#### <summary>Depth-Regularized Optimization for 3D Gaussian Splatting in Few-Shot Images
Authors: Jaeyoung Chung, Jeongtaek Oh, Kyoung Mu Lee
<details span>
<summary><b>Abstract</b></summary>
In this paper, we present a method to optimize Gaussian splatting with a limited number of images while avoiding overfitting. Representing a 3D scene by combining numerous Gaussian splats has yielded outstanding visual quality. However, it tends to overfit the training views when only a small number of images are available. To address this issue, we introduce a dense depth map as a geometry guide to mitigate overfitting. We obtained the depth map using a pre-trained monocular depth estimation model and aligning the scale and offset using sparse COLMAP feature points. The adjusted depth aids in the color-based optimization of 3D Gaussian splatting, mitigating floating artifacts, and ensuring adherence to geometric constraints. We verify the proposed method on the NeRF-LLFF dataset with varying numbers of few images. Our approach demonstrates robust geometry compared to the original method that relies solely on images.


![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4453dd18-8e1a-4b18-bd6a-250484919aab)

</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.13398) | [⌨️ Code](https://github.com/robot0321/DepthRegularizedGS) | [🌐 Project Page](https://robot0321.github.io/DepthRegGS/)



#### <summary>FSGS: Real-Time Few-shot View Synthesis using Gaussian Splatting
Authors: Zehao Zhu, Zhiwen Fan, Yifan Jiang, Zhangyang Wang
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis from limited observations remains an important and persistent task. However, high efficiency in existing NeRF-based few-shot view synthesis is often compromised to obtain an accurate 3D representation. To address this challenge, we propose a few-shot view synthesis framework based on 3D Gaussian Splatting that enables real-time and photo-realistic view synthesis with as few as three training views. The proposed method, dubbed FSGS, handles the extremely sparse initialized SfM points with a thoughtfully designed Gaussian Unpooling process. Our method iteratively distributes new Gaussians around the most representative locations, subsequently infilling local details in vacant areas. We also integrate a large-scale pre-trained monocular depth estimator within the Gaussians optimization process, leveraging online augmented views to guide the geometric optimization towards an optimal solution. Starting from sparse points observed from limited input viewpoints, our FSGS can accurately grow into unseen regions, comprehensively covering the scene and boosting the rendering quality of novel views. Overall, FSGS achieves state-of-the-art performance in both accuracy and rendering efficiency across diverse datasets, including LLFF, Mip-NeRF360, and Blender.


![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f24b7ccf-ee32-4529-8061-b20a37f0a608)

</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.00451) | [⌨️ Code](https://github.com/VITA-Group/FSGS) | [🌐 Project Page](https://zehaozhu.github.io/FSGS/)

#### <summary>SparseGS: Real-Time 360° Sparse View Synthesis using Gaussian Splatting
>*the method of rendering depth*

Authors: Haolin Xiong, Sairisheek Muttukuru, Rishi Upadhyay, Pradyumna Chari, Achuta Kadambi
<details span>
<summary><b>Abstract</b></summary>
The problem of novel view synthesis has grown significantly in popularity recently with the introduction of Neural Radiance Fields (NeRFs) and other implicit scene representation methods. A recent advance, 3D Gaussian Splatting (3DGS), leverages an explicit representation to achieve real-time rendering with high-quality results. However, 3DGS still requires an abundance of training views to generate a coherent scene representation. In few shot settings, similar to NeRF, 3DGS tends to overfit to training views, causing background collapse and excessive floaters, especially as the number of training views are reduced. We propose a method to enable training coherent 3DGS-based radiance fields of 360 scenes from sparse training views. We find that using naive depth priors is not sufficient and integrate depth priors with generative and explicit constraints to reduce background collapse, remove floaters, and enhance consistency from unseen viewpoints. Experiments show that our method outperforms base 3DGS by up to 30.5% and NeRF-based methods by up to 15.6% in LPIPS on the MipNeRF-360 dataset with substantially less training and inference cost.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d5d2f9b8-33e7-4ee0-b385-591c1efa7395)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.00206) | [⌨️ Code](https://github.com/ForMyCat/SparseGS) | [🌐 Project Page](https://formycat.github.io/SparseGS-Real-Time-360-Sparse-View-Synthesis-using-Gaussian-Splatting/)

#### <summary>DNGaussian: Optimizing Sparse-View 3D Gaussian Radiance Fields with Global-Local Depth Normalization
Authors: Jiahe Li, Jiawei Zhang, Xiao Bai, Jin Zheng, Xin Ning, Jun Zhou, Lin Gu
<details span>
<summary><b>Abstract</b></summary>
Radiance fields have demonstrated impressive performance in synthesizing novel views from sparse input views, yet prevailing methods suffer from high training costs and slow inference speed. This paper introduces DNGaussian, a depth-regularized framework based on 3D Gaussian radiance fields, offering real-time and high-quality few-shot novel view synthesis at low costs. Our motivation stems from the highly efficient representation and surprising quality of the recent 3D Gaussian Splatting, despite it will encounter a geometry degradation when input views decrease. In the Gaussian radiance fields, we find this degradation in scene geometry primarily lined to the positioning of Gaussian primitives and can be mitigated by depth constraint. Consequently, we propose a Hard and Soft Depth Regularization to restore accurate scene geometry under coarse monocular depth supervision while maintaining a fine-grained color appearance. To further refine detailed geometry reshaping, we introduce Global-Local Depth Normalization, enhancing the focus on small local depth changes. Extensive experiments on LLFF, DTU, and Blender datasets demonstrate that DNGaussian outperforms state-of-the-art methods, achieving comparable or better results with significantly reduced memory cost, a 25× reduction in training time, and over 3000× faster rendering speed.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/1275b710-5c38-43fb-98ca-0915777b5d19)


</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.06912) | [⌨️ Code](https://github.com/Fictionarry/DNGaussian) | [🌐 Project Page](https://fictionarry.github.io/DNGaussian/)

#### <summary>CoherentGS: Sparse Novel View Synthesis with Coherent 3D Gaussians
Authors: Avinash Paliwal, Wei Ye, Jinhui Xiong, Dmytro Kotovenko, Rakesh Ranjan, Vikas Chandra, Nima Khademi Kalantari
<details span>
<summary><b>Abstract</b></summary>
The field of 3D reconstruction from images has rapidly evolved in the past few years, first with the introduction of Neural Radiance Field (NeRF) and more recently with 3D Gaussian Splatting (3DGS). The latter provides a significant edge over NeRF in terms of the training and inference speed, as well as the reconstruction quality. Although 3DGS works well for dense input images, the unstructured point-cloud like representation quickly overfits to the more challenging setup of extremely sparse input images (e.g., 3 images), creating a representation that appears as a jumble of needles from novel views. To address this issue, we propose regularized optimization and depth-based initialization. Our key idea is to introduce a structured Gaussian representation that can be controlled in 2D image space. We then constraint the Gaussians, in particular their position, and prevent them from moving independently during optimization. Specifically, we introduce single and multiview constraints through an implicit convolutional decoder and a total variation loss, respectively. With the coherency introduced to the Gaussians, we further constrain the optimization through a flow-based loss function. To support our regularized optimization, we propose an approach to initialize the Gaussians using monocular depth estimates at each input view. We demonstrate significant improvements compared to the state-of-the-art sparse-view NeRF-based approaches on a variety of scenes.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/14730d86-052e-4110-92cf-684eece33a7e)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.19495) | [⌨️ Code] | [🌐 Project Page](https://people.engr.tamu.edu/nimak/Papers/CoherentGS/index.html)


#### <summary>A Construct-Optimize Approach to Sparse View Synthesis without Camera Pose
Authors: Kaiwen Jiang, Yang Fu, Mukund Varma T, Yash Belhe, Xiaolong Wang, Hao Su, Ravi Ramamoorthi
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis from a sparse set of input images is a challenging problem of great practical interest, especially when camera poses are absent or inaccurate. Direct optimization of camera poses and usage of estimated depths in neural radiance field algorithms usually do not produce good results because of the coupling between poses and depths, and inaccuracies in monocular depth estimation. In this paper, we leverage the recent 3D Gaussian splatting method to develop a novel construct-and-optimize method for sparse view synthesis without camera poses. Specifically, we construct a solution progressively by using monocular depth and projecting pixels back into the 3D world. During construction, we optimize the solution by detecting 2D correspondences between training views and the corresponding rendered images. We develop a unified differentiable pipeline for camera registration and adjustment of both camera poses and depths, followed by back-projection. We also introduce a novel notion of an expected surface in Gaussian splatting, which is critical to our optimization. These steps enable a coarse solution, which can then be low-pass filtered and refined using standard optimization methods. We demonstrate results on the Tanks and Temples and Static Hikes datasets with as few as three widely-spaced views, showing significantly better quality than competing methods, including those with approximate camera pose information. Moreover, our results improve with more views and outperform previous InstantNGP and Gaussian Splatting algorithms even when using half the dataset.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/03b3bba4-e9b4-4ff7-977b-15f4ec596be3)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.03659) | [⌨️ Code] | [🌐 Project Page]


#### <summary>CoR-GS: Sparse-View 3D Gaussian Splatting via Co-Regularization
Authors: Jiawei Zhang, Jiahe Li, Xiaohan Yu, Lei Huang, Lin Gu, Jin Zheng, Xiao Bai
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) creates a radiance field consisting of 3D Gaussians to represent a scene. With sparse training views, 3DGS easily suffers from overfitting, negatively impacting the reconstruction quality. This paper introduces a new co-regularization perspective for improving sparse-view 3DGS. When training two 3D Gaussian radiance fields with the same sparse views of a scene, we observe that the two radiance fields exhibit \textit{point disagreement} and \textit{rendering disagreement} that can unsupervisedly predict reconstruction quality, stemming from the sampling implementation in densification. We further quantify the point disagreement and rendering disagreement by evaluating the registration between Gaussians' point representations and calculating differences in their rendered pixels. The empirical study demonstrates the negative correlation between the two disagreements and accurate reconstruction, which allows us to identify inaccurate reconstruction without accessing ground-truth information. Based on the study, we propose CoR-GS, which identifies and suppresses inaccurate reconstruction based on the two disagreements: (\romannumeral1) Co-pruning considers Gaussians that exhibit high point disagreement in inaccurate positions and prunes them. (\romannumeral2) Pseudo-view co-regularization considers pixels that exhibit high rendering disagreement are inaccurately rendered and suppress the disagreement. Results on LLFF, Mip-NeRF360, DTU, and Blender demonstrate that CoR-GS effectively regularizes the scene geometry, reconstructs the compact representations, and achieves state-of-the-art novel view synthesis quality under sparse training views.



</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12110) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Uncertainty-guided Optimal Transport in Depth Supervised Sparse-View 3D Gaussian
Authors: Wei Sun, Qi Zhang, Yanzhao Zhou, Qixiang Ye, Jianbin Jiao, Yuan Li
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian splatting has demonstrated impressive performance in real-time novel view synthesis. However, achieving successful reconstruction from RGB images generally requires multiple input views captured under static conditions. To address the challenge of sparse input views, previous approaches have incorporated depth supervision into the training of 3D Gaussians to mitigate overfitting, using dense predictions from pretrained depth networks as pseudo-ground truth. Nevertheless, depth predictions from monocular depth estimation models inherently exhibit significant uncertainty in specific areas. Relying solely on pixel-wise L2 loss may inadvertently incorporate detrimental noise from these uncertain areas. In this work, we introduce a novel method to supervise the depth distribution of 3D Gaussians, utilizing depth priors with integrated uncertainty estimates. To address these localized errors in depth predictions, we integrate a patch-wise optimal transport strategy to complement traditional L2 loss in depth supervision. Extensive experiments conducted on the LLFF, DTU, and Blender datasets demonstrate that our approach, UGOT, achieves superior novel view synthesis and consistently outperforms state-of-the-art methods.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/cfee31c9-1738-46b7-9e4f-cfec7a5d9bd8)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.19657) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Self-augmented Gaussian Splatting with Structure-aware Masks for Sparse-view 3D Reconstruction
Authors: Lingbei Meng, Bi'an Du, Wei Hu
<details span>
<summary><b>Abstract</b></summary>
Sparse-view 3D reconstruction stands as a formidable challenge in computer vision, aiming to build complete three-dimensional models from a limited array of viewing perspectives. This task confronts several difficulties: 1) the limited number of input images that lack consistent information; 2) dependence on the quality of input images; and 3) the substantial size of model parameters. To address these challenges, we propose a self-augmented coarse-to-fine Gaussian splatting paradigm, enhanced with a structure-aware mask, for sparse-view 3D reconstruction. In particular, our method initially employs a coarse Gaussian model to obtain a basic 3D representation from sparse-view inputs. Subsequently, we develop a fine Gaussian network to enhance consistent and detailed representation of the output with both 3D geometry augmentation and perceptual view augmentation. During training, we design a structure-aware masking strategy to further improve the model's robustness against sparse inputs and noise.Experimental results on the MipNeRF360 and OmniObject3D datasets demonstrate that the proposed method achieves state-of-the-art performances for sparse input views in both perceptual quality and efficiency.
 
![image](https://github.com/user-attachments/assets/770d39cb-e357-4c63-ba49-07499df92baa)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.04831) | [⌨️ Code] | [🌐 Project Page]


#### <summary>LM-Gaussian: Boost Sparse-view 3D Gaussian Splatting with Large Model Priors
Authors: Hanyang Yu, Xiaoxiao Long, Ping Tan
<details span>
<summary><b>Abstract</b></summary>
We aim to address sparse-view reconstruction of a 3D scene by leveraging priors from large-scale vision models. While recent advancements such as 3D Gaussian Splatting (3DGS) have demonstrated remarkable successes in 3D reconstruction, these methods typically necessitate hundreds of input images that densely capture the underlying scene, making them time-consuming and impractical for real-world applications. However, sparse-view reconstruction is inherently ill-posed and under-constrained, often resulting in inferior and incomplete outcomes. This is due to issues such as failed initialization, overfitting on input images, and a lack of details. To mitigate these challenges, we introduce LM-Gaussian, a method capable of generating high-quality reconstructions from a limited number of images. Specifically, we propose a robust initialization module that leverages stereo priors to aid in the recovery of camera poses and the reliable point clouds. Additionally, a diffusion-based refinement is iteratively applied to incorporate image diffusion priors into the Gaussian optimization process to preserve intricate scene details. Finally, we utilize video diffusion priors to further enhance the rendered images for realistic visual effects. Overall, our approach significantly reduces the data acquisition requirements compared to previous 3DGS methods. We validate the effectiveness of our framework through experiments on various public datasets, demonstrating its potential for high-quality 360-degree scene reconstruction. Visual results are on our website.

![image](https://github.com/user-attachments/assets/87ac6848-8360-4eab-9d74-2479c011ae54)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.03456) | [⌨️ Code](https://github.com/hanyangyu1021/LMGaussian) | [🌐 Project Page](https://hanyangyu1021.github.io/lm-gaussian.github.io/)

#### <summary>Optimizing 3D Gaussian Splatting for Sparse Viewpoint Scene Reconstruction
Authors: Shen Chen, Jiale Zhou, Lei Li
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has emerged as a promising approach for 3D scene representation, offering a reduction in computational overhead compared to Neural Radiance Fields (NeRF). However, 3DGS is susceptible to high-frequency artifacts and demonstrates suboptimal performance under sparse viewpoint conditions, thereby limiting its applicability in robotics and computer vision. To address these limitations, we introduce SVS-GS, a novel framework for Sparse Viewpoint Scene reconstruction that integrates a 3D Gaussian smoothing filter to suppress artifacts. Furthermore, our approach incorporates a Depth Gradient Profile Prior (DGPP) loss with a dynamic depth mask to sharpen edges and 2D diffusion with Score Distillation Sampling (SDS) loss to enhance geometric consistency in novel view synthesis. Experimental evaluations on the MipNeRF-360 and SeaThru-NeRF datasets demonstrate that SVS-GS markedly improves 3D reconstruction from sparse viewpoints, offering a robust and efficient solution for scene understanding in robotics and computer vision applications.

![image](https://github.com/user-attachments/assets/2ac18201-7908-4794-899d-e1c3f29bf7f7)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.03213) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Dense Point Clouds Matter: Dust-GS for Scene Reconstruction from Sparse Viewpoints
>*Dynamic depth mask for distant background*

Authors: Shan Chen, Jiale Zhou, Lei Li
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has demonstrated remarkable performance in scene synthesis and novel view synthesis tasks. Typically, the initialization of 3D Gaussian primitives relies on point clouds derived from Structure-from-Motion (SfM) methods. However, in scenarios requiring scene reconstruction from sparse viewpoints, the effectiveness of 3DGS is significantly constrained by the quality of these initial point clouds and the limited number of input images. In this study, we present Dust-GS, a novel framework specifically designed to overcome the limitations of 3DGS in sparse viewpoint conditions. Instead of relying solely on SfM, Dust-GS introduces an innovative point cloud initialization technique that remains effective even with sparse input data. Our approach leverages a hybrid strategy that integrates an adaptive depth-based masking technique, thereby enhancing the accuracy and detail of reconstructed scenes. Extensive experiments conducted on several benchmark datasets demonstrate that Dust-GS surpasses traditional 3DGS methods in scenarios with sparse viewpoints, achieving superior scene reconstruction quality with a reduced number of input images.

![image](https://github.com/user-attachments/assets/107375e5-920d-4536-b56f-4a0b0034efa1)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.08613) | [⌨️ Code] | [🌐 Project Page]

#### <summary>MVPGS: Excavating Multi-view Priors for Gaussian Splatting from Sparse Input Views
>*mvs depth as Geometric Filter for 3dgs, similar to GaussianPro*

Authors: Wangze Xu, Huachen Gao, Shihe Shen, Rui Peng, Jianbo Jiao, Ronggang Wang
<details span>
<summary><b>Abstract</b></summary>
Recently, the Neural Radiance Field (NeRF) advancement has facilitated few-shot Novel View Synthesis (NVS), which is a significant challenge in 3D vision applications. Despite numerous attempts to reduce the dense input requirement in NeRF, it still suffers from time-consumed training and rendering processes. More recently, 3D Gaussian Splatting (3DGS) achieves real-time high-quality rendering with an explicit point-based representation. However, similar to NeRF, it tends to overfit the train views for lack of constraints. In this paper, we propose \textbf{MVPGS}, a few-shot NVS method that excavates the multi-view priors based on 3D Gaussian Splatting. We leverage the recent learning-based Multi-view Stereo (MVS) to enhance the quality of geometric initialization for 3DGS. To mitigate overfitting, we propose a forward-warping method for additional appearance constraints conforming to scenes based on the computed geometry. Furthermore, we introduce a view-consistent geometry constraint for Gaussian parameters to facilitate proper optimization convergence and utilize a monocular depth regularization as compensation. Experiments show that the proposed method achieves state-of-the-art performance with real-time rendering speed.

![image](https://github.com/user-attachments/assets/b2e8aeb9-71d3-442a-829a-1ff493b05707)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.14316) | [⌨️ Code](https://github.com/zezeaaa/MVPGS) | [🌐 Project Page](https://zezeaaa.github.io/projects/MVPGS/)


<br>
<br>



## Structured

#### <summary>Scaffold-GS: Structured 3D Gaussians for View-Adaptive Rendering
Authors: Tao Lu, Mulin Yu, Linning Xu, Yuanbo Xiangli, Limin Wang, Dahua Lin, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
Neural rendering methods have significantly advanced photo-realistic 3D scene rendering in various academic and industrial applications. The recent 3D Gaussian Splatting method has achieved the state-of-the-art rendering quality and speed combining the benefits of both primitive-based representations and volumetric representations. However, it often leads to heavily redundant Gaussians that try to fit every training view, neglecting the underlying scene geometry. Consequently, the resulting model becomes less robust to significant view changes, texture-less area and lighting effects. We introduce Scaffold-GS, which uses anchor points to distribute local 3D Gaussians, and predicts their attributes on-the-fly based on viewing direction and distance within the view frustum. Anchor growing and pruning strategies are developed based on the importance of neural Gaussians to reliably improve the scene coverage. We show that our method effectively reduces redundant Gaussians while delivering high-quality rendering. We also demonstrates an enhanced capability to accommodate scenes with varying levels-of-detail and view-dependent observations, without sacrificing the rendering speed.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4ca042f1-a5c9-4315-9ed3-58726096577b)
 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.00109) | [⌨️ Code](https://github.com/city-super/Scaffold-GS?tab=readme-ov-file) | [🌐 Project Page](https://city-super.github.io/scaffold-gs/)



#### <summary>HAC: Hash-grid Assisted Context for 3D Gaussian Splatting Compression
Authors: Yihang Chen, Qianyi Wu, Jianfei Cai, Mehrtash Harandi, Weiyao Lin
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has emerged as a promising framework for novel view synthesis, boasting rapid rendering speed with high fidelity. However, the substantial Gaussians and their associated attributes necessitate effective compression techniques. Nevertheless, the sparse and unorganized nature of the point cloud of Gaussians (or anchors in our paper) presents challenges for compression. To address this, we make use of the relations between the unorganized anchors and the structured hash grid, leveraging their mutual information for context modeling, and propose a Hash-grid Assisted Context (HAC) framework for highly compact 3DGS representation. Our approach introduces a binary hash grid to establish continuous spatial consistencies, allowing us to unveil the inherent spatial relations of anchors through a carefully designed context model. To facilitate entropy coding, we utilize Gaussian distributions to accurately estimate the probability of each quantized attribute, where an adaptive quantization module is proposed to enable high-precision quantization of these attributes for improved fidelity restoration. Additionally, we incorporate an adaptive masking strategy to eliminate invalid Gaussians and anchors. Importantly, our work is the pioneer to explore context-based compression for 3DGS representation, resulting in a remarkable size reduction of over 75× compared to vanilla 3DGS, while simultaneously improving fidelity, and achieving over 11× size reduction over SOTA 3DGS compression approach Scaffold-GS.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/525af2a3-7202-4b0d-a6a3-1498fdcf6c46)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.14530) | [⌨️ Code](https://github.com/YihangChen-ee/HAC) | [🌐 Project Page](https://yihangchen-ee.github.io/project_hac/)

#### <summary>Octree-GS: Towards Consistent Real-time Rendering with LOD-Structured 3D Gaussians
Authors: Kerui Ren, Lihan Jiang, Tao Lu, Mulin Yu, Linning Xu, Zhangkai Ni, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
The recent 3D Gaussian splatting (3D-GS) has shown remarkable rendering fidelity and efficiency compared to NeRF-based neural scene representations. While demonstrating the potential for real-time rendering, 3D-GS encounters rendering bottlenecks in large scenes with complex details due to an excessive number of Gaussian primitives located within the viewing frustum. This limitation is particularly noticeable in zoom-out views and can lead to inconsistent rendering speeds in scenes with varying details. Moreover, it often struggles to capture the corresponding level of details at different scales with its heuristic density control operation. Inspired by the Level-of-Detail (LOD) techniques, we introduce Octree-GS, featuring an LOD-structured 3D Gaussian approach supporting level-of-detail decomposition for scene representation that contributes to the final rendering results. Our model dynamically selects the appropriate level from the set of multi-resolution anchor points, ensuring consistent rendering performance with adaptive LOD adjustments while maintaining high-fidelity rendering results.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4adb3feb-4df8-4a16-8788-e3b1f06ffbbb)


</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.17898) | [⌨️ Code](https://github.com/city-super/Octree-GS) | [🌐 Project Page](https://city-super.github.io/octree-gs/)


#### <summary>GSDF: 3DGS Meets SDF for Improved Rendering and Reconstruction
Authors: Mulin Yu, Tao Lu, Linning Xu, Lihan Jiang, Yuanbo Xiangli, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
Presenting a 3D scene from multiview images remains a core and long-standing challenge in computer vision and computer graphics. Two main requirements lie in rendering and reconstruction. Notably, SOTA rendering quality is usually achieved with neural volumetric rendering techniques, which rely on aggregated point/primitive-wise color and neglect the underlying scene geometry. Learning of neural implicit surfaces is sparked from the success of neural rendering. Current works either constrain the distribution of density fields or the shape of primitives, resulting in degraded rendering quality and flaws on the learned scene surfaces. The efficacy of such methods is limited by the inherent constraints of the chosen neural representation, which struggles to capture fine surface details, especially for larger, more intricate scenes. To address these issues, we introduce GSDF, a novel dual-branch architecture that combines the benefits of a flexible and efficient 3D Gaussian Splatting (3DGS) representation with neural Signed Distance Fields (SDF). The core idea is to leverage and enhance the strengths of each branch while alleviating their limitation through mutual guidance and joint supervision. We show on diverse scenes that our design unlocks the potential for more accurate and detailed surface reconstructions, and at the meantime benefits 3DGS rendering with structures that are more aligned with the underlying geometry.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/8694f554-390c-447b-a34e-bbd6201cf0e2)


</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.16964) | [⌨️ Code](https://github.com/city-super/GSDF) | [🌐 Project Page](https://city-super.github.io/GSDF/)

#### <summary>GeoGaussian: Geometry-aware Gaussian Splatting for Scene Rendering
Authors: Yanyan Li, Chenyu Lyu, Yan Di, Guangyao Zhai, Gim Hee Lee, Federico Tombari
<details span>
<summary><b>Abstract</b></summary>
During the Gaussian Splatting optimization process, the scene’s geometry can gradually deteriorate if its structure is not deliberately preserved, especially in non-textured regions such as walls, ceilings, and furniture surfaces. This degradation significantly affects the rendering quality of novel views that deviate significantly from the viewpoints in the training data. To mitigate this issue, we propose a novel approach called GeoGaussian. Based on the smoothly connected areas observed from point clouds, this method introduces a novel pipeline to initialize thin Gaussians aligned with the surfaces, where the characteristic can be transferred to new generations through a carefully designed densification strategy. Finally, the pipeline ensures that the scene’s geometry and texture are maintained through constrained optimization processes with explicit geometry constraints. Benefiting from the proposed architecture, the generative ability of 3D Gaussians is enhanced, especially in structured regions. Our proposed pipeline achieves state-of-the-art performance in novel view synthesis and geometric reconstruction, as evaluated qualitatively and quantitatively on public datasets.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9cd2a10a-5286-4b78-9b68-f107136cae73)


</details>


[📃 arXiv:2403](https://arxiv.org/pdf/2403.11324) | [⌨️ Code](https://github.com/yanyan-li/GeoGaussian) | [🌐 Project Page](https://yanyan-li.github.io/project/gs/geogaussian)


#### <summary>Structure-Aware 3D Gaussian Splatting
Authors: Evangelos Ververas, Rolandos Alexandros Potamias, Jifei Song, Jiankang Deng, Stefanos Zafeiriou
<details span>
<summary><b>Abstract</b></summary>
Following the advent of NeRFs, 3D Gaussian Splatting (3DGS) has paved the way to real-time neural rendering overcoming the computational burden of volumetric methods. Following the pioneering work of 3D-GS, several methods have attempted to achieve compressible and high-fidelity performance alternatives. However, by employing a geometry-agnostic optimization scheme, these methods neglect the inherent 3D structure of the scene, thereby restricting the expressivity and the quality of the representation, resulting in various floating points and artifacts. In this work, we propose a structure-aware Gaussian Splatting method (SAGS) that implicitly encodes the geometry of the scene, which reflects to state-of-the-art rendering performance and reduced storage requirements on benchmark novel-view synthesis datasets. SAGS is founded on a local-global graph representation that facilitates the learning of complex scenes and enforces meaningful point displacements that preserve the scene’s geometry. Additionally, we introduce a lightweight version of SAGS, using a simple yet effective mid-point interpolation scheme, which showcases a compact representation of the scene with up to 24 × size reduction without the reliance on any compression strategies. Extensive experiments across multiple benchmark datasets demonstrate the superiority of SAGS compared to state-of-the-art 3D-GS methods under both rendering quality and model size. Besides, we demonstrate that our structure-aware method can effectively mitigate floating artifacts and irregular distortions of previous methods while obtaining precise depth maps.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/84b21f32-acb6-4332-af59-f6e0bd14e572)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.19149) | [⌨️ Code] | [🌐 Project Page](https://eververas.github.io/SAGS/)




#### <summary>ContextGS: Compact 3D Gaussian Splatting with Anchor Level Context Model
Authors: Yufei Wang, Zhihao Li, Lanqing Guo, Wenhan Yang, Alex C. Kot, Bihan Wen
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has become a promising framework for novel view synthesis, offering fast rendering speeds and high fidelity. However, the large number of Gaussians and their associated attributes require effective compression techniques. Existing methods primarily compress neural Gaussians individually and independently, i.e., coding all the neural Gaussians at the same time, with little design for their interactions and spatial dependence. Inspired by the effectiveness of the context model in image compression, we propose the first autoregressive model at the anchor level for 3DGS compression in this work. We divide anchors into different levels and the anchors that are not coded yet can be predicted based on the already coded ones in all the coarser levels, leading to more accurate modeling and higher coding efficiency. To further improve the efficiency of entropy coding, e.g., to code the coarsest level with no already coded anchors, we propose to introduce a low-dimensional quantized feature as the hyperprior for each anchor, which can be effectively compressed. Our work pioneers the context model in the anchor level for 3DGS representation, yielding an impressive size reduction of over 100 times compared to vanilla 3DGS and 15 times compared to the most recent state-of-the-art work Scaffold-GS, while achieving comparable or even higher rendering quality.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/996e5c55-1ed7-41d1-a928-24e26ed624ef)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20721) | [⌨️ Code](https://github.com/wyf0912/ContextGS) | [🌐 Project Page]





#### <summary>Superpoint Gaussian Splatting for Real-Time High-Fidelity Dynamic Scene Reconstruction
Authors: Diwen Wan, Ruijie Lu, Gang Zeng
<details span>
<summary><b>Abstract</b></summary>
Rendering novel view images in dynamic scenes is a crucial yet challenging task. Current methods mainly utilize NeRF-based methods to represent the static scene and an additional time-variant MLP to model scene deformations, resulting in relatively low rendering quality as well as slow inference speed. To tackle these challenges, we propose a novel framework named Superpoint Gaussian Splatting (SP-GS). Specifically, our framework first employs explicit 3D Gaussians to reconstruct the scene and then clusters Gaussians with similar properties (e.g., rotation, translation, and location) into superpoints. Empowered by these superpoints, our method manages to extend 3D Gaussian splatting to dynamic scenes with only a slight increase in computational expense. Apart from achieving state-of-the-art visual quality and real-time rendering under high resolutions, the superpoint representation provides a stronger manipulation capability. Extensive experiments demonstrate the practicality and effectiveness of our approach on both synthetic and real-world datasets.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d164cbfc-74bb-4a08-bc3a-d91e52dd6a68)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.03697) | [⌨️ Code] | [🌐 Project Page](https://dnvtmf.github.io/SP_GS.github.io)


#### <summary>InfoGaussian: Structure-Aware Dynamic Gaussians through Lightweight Information Shaping
Authors: Yunchao Zhang, Guandao Yang, Leonidas Guibas, Yanchao Yang
<details span>
<summary><b>Abstract</b></summary>
3D Gaussians, as a low-level scene representation, typically involve thousands to millions of Gaussians. This makes it difficult to control the scene in ways that reflect the underlying dynamic structure, where the number of independent entities is typically much smaller. In particular, it can be challenging to animate and move objects in the scene, which requires coordination among many Gaussians. To address this issue, we develop a mutual information shaping technique that enforces movement resonance between correlated Gaussians in a motion network. Such correlations can be learned from putative 2D object masks in different views. By approximating the mutual information with the Jacobians of the motions, our method ensures consistent movements of the Gaussians composing different objects under various perturbations. In particular, we develop an efficient contrastive training pipeline with lightweight optimization to shape the motion network, avoiding the need for re-shaping throughout the motion sequence. Notably, our training only touches a small fraction of all Gaussians in the scene yet attains the desired compositional behavior according to the underlying dynamic structure. The proposed technique is evaluated on challenging scenes and demonstrates significant performance improvement in promoting consistent movements and 3D object segmentation while inducing low computation and memory requirements.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/99c2f56f-ed1c-475a-a4cd-af7dee6231e7)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.05897) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Gaussian-Forest: Hierarchical-Hybrid 3D Gaussian Splatting for Compressed Scene Modeling
Authors: Fengyi Zhang, Tianjun Zhang, Lin Zhang, Helen Huang, Yadan Luo
<details span>
<summary><b>Abstract</b></summary>
The field of novel-view synthesis has recently witnessed the emergence of 3D Gaussian Splatting, which represents scenes in a point-based manner and renders through rasterization. This methodology, in contrast to Radiance Fields that rely on ray tracing, demonstrates superior rendering quality and speed. However, the explicit and unstructured nature of 3D Gaussians poses a significant storage challenge, impeding its broader application. To address this challenge, we introduce the Gaussian-Forest modeling framework, which hierarchically represents a scene as a forest of hybrid 3D Gaussians. Each hybrid Gaussian retains its unique explicit attributes while sharing implicit ones with its sibling Gaussians, thus optimizing parameterization with significantly fewer variables. Moreover, adaptive growth and pruning strategies are designed, ensuring detailed representation in complex regions and a notable reduction in the number of required Gaussians. Extensive experiments demonstrate that Gaussian-Forest not only maintains comparable speed and quality but also achieves a compression rate surpassing 10 times, marking a significant advancement in efficient scene modeling.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/dbd9bfaa-20d7-4d2e-858e-32de7553fb41)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.08759) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Gaussian Splatting with Localized Points Management
Authors: Haosen Yang, Chenhao Zhang, Wenqing Wang, Marco Volino, Adrian Hilton, Li Zhang, Xiatian Zhu
<details span>
<summary><b>Abstract</b></summary>
Point management is a critical component in optimizing 3D Gaussian Splatting (3DGS) models, as the point initiation (e.g., via structure from motion) is distributionally inappropriate. Typically, the Adaptive Density Control (ADC) algorithm is applied, leveraging view-averaged gradient magnitude thresholding for point densification, opacity thresholding for pruning, and regular all-points opacity reset. However, we reveal that this strategy is limited in tackling intricate/special image regions (e.g., transparent) as it is unable to identify all the 3D zones that require point densification, and lacking an appropriate mechanism to handle the ill-conditioned points with negative impacts (occlusion due to false high opacity). To address these limitations, we propose a Localized Point Management (LPM) strategy, capable of identifying those error-contributing zones in the highest demand for both point addition and geometry calibration. Zone identification is achieved by leveraging the underlying multiview geometry constraints, with the guidance of image rendering errors. We apply point densification in the identified zone, whilst resetting the opacity of those points residing in front of these regions so that a new opportunity is created to correct ill-conditioned points. Serving as a versatile plugin, LPM can be seamlessly integrated into existing 3D Gaussian Splatting models. Experimental evaluation across both static 3D and dynamic 4D scenes validate the efficacy of our LPM strategy in boosting a variety of existing 3DGS models both quantitatively and qualitatively. Notably, LPM improves both vanilla 3DGS and SpaceTimeGS to achieve state-of-the-art rendering quality while retaining real-time speeds, outperforming on challenging datasets such as Tanks & Temples and the Neural 3D Video Dataset.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/cf43d4da-650b-44f7-afde-4d059c02d6dd)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04251) | [⌨️ Code](https://github.com/Surrey-UPLab/Localized-Gaussian-Point-Management) | [🌐 Project Page](https://surrey-uplab.github.io/research/LPM/)



#### <summary>SplatFields: Neural Gaussian Splats for Sparse 3D and 4D Reconstruction
> *To quantify the local spatial autocorrelation of each splat, we select the five nearest neighbors and measure Moran’s I of the splat’s attributes (color, opacity, covariance). The core idea of our method is to introduce a spatial bias during the optimization phase, which encourages nearby primitives to share similar features. combine explicit and implicit representation. we identify the lack of spatial autocorrelation of splat features as one of the factors contributing to the suboptimal performance of the 3DGS technique in sparse reconstruction settings*

Authors: Marko Mihajlovic, Sergey Prokudin, Siyu Tang, Robert Maier, Federica Bogo, Tony Tung, Edmond Boyer
<details span>
<summary><b>Abstract</b></summary>
Digitizing 3D static scenes and 4D dynamic events from multi-view images has long been a challenge in computer vision and graphics. Recently, 3D Gaussian Splatting (3DGS) has emerged as a practical and scalable reconstruction method, gaining popularity due to its impressive reconstruction quality, real-time rendering capabilities, and compatibility with widely used visualization tools. However, the method requires a substantial number of input views to achieve high-quality scene reconstruction, introducing a significant practical bottleneck. This challenge is especially severe in capturing dynamic scenes, where deploying an extensive camera array can be prohibitively costly. In this work, we identify the lack of spatial autocorrelation of splat features as one of the factors contributing to the suboptimal performance of the 3DGS technique in sparse reconstruction settings. To address the issue, we propose an optimization strategy that effectively regularizes splat features by modeling them as the outputs of a corresponding implicit neural field. This results in a consistent enhancement of reconstruction quality across various scenarios. Our approach effectively handles static and dynamic cases, as demonstrated by extensive testing across different setups and scene complexities.

![image](https://github.com/user-attachments/assets/5a238f8f-9b06-4d60-855e-a0d079ba6348)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.11211) | [⌨️ Code](https://github.com/markomih/SplatFields) | [🌐 Project Page](https://markomih.github.io/SplatFields/)



<br>
<br>

## Large Scale

#### <summary>MatrixCity: A Large-scale City Dataset for City-scale Neural Rendering and Beyond
Authors: Yixuan Li, Lihan Jiang, Linning Xu, Yuanbo Xiangli, Zhenzhi Wang, Dahua Lin, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
Neural radiance fields (NeRF) and its subsequent variants have led to remarkable progress in neural rendering. While most of recent neural rendering works focus on objects and small-scale scenes, developing neural rendering methods for city-scale scenes is of great potential in many real-world applications. However, this line of research is impeded by the absence of a comprehensive and high-quality dataset, yet collecting such a dataset over real city-scale scenes is costly, sensitive, and technically difficult. To this end, we build a large-scale, comprehensive, and high-quality synthetic dataset for city-scale neural rendering researches. Leveraging the Unreal Engine 5 City Sample project, we develop a pipeline to easily collect aerial and street city views, accompanied by ground-truth camera poses and a range of additional data modalities. Flexible controls over environmental factors like light, weather, human and car crowd are also available in our pipeline, supporting the need of various tasks covering city-scale neural rendering and beyond. The resulting pilot dataset, MatrixCity, contains 67k aerial images and 452k street images from two city maps of total size 28km2. On top of MatrixCity, a thorough benchmark is also conducted, which not only reveals unique challenges of the task of city-scale neural rendering, but also highlights potential improvements for future works.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a77a947a-2c66-42fc-bf47-134a3aa150cc)


</details>

[📃 arXiv:2309](https://arxiv.org/pdf/2309.16553) | [⌨️ Code](https://github.com/city-super/MatrixCity) | [🌐 Project Page](https://city-super.github.io/matrixcity/)



#### <summary>VastGaussian: Vast 3D Gaussians for Large Scene Reconstruction
Authors: Jiaqi Lin, Zhihao Li, Xiao Tang, Jianzhuang Liu, Shiyong Liu, Jiayue Liu, Yangdi Lu, Xiaofei Wu, Songcen Xu, Youliang Yan, Wenming Yang
<details span>
<summary><b>Abstract</b></summary>
Existing NeRF-based methods for large scene reconstruction often have limitations in visual quality and rendering speed. While the recent 3D Gaussian Splatting works well on small-scale and object-centric scenes, scaling it up to large scenes poses challenges due to limited video memory, long optimization time, and noticeable appearance variations. To address these challenges, we present VastGaussian, the first method for high-quality reconstruction and real-time rendering on large scenes based on 3D Gaussian Splatting. We propose a progressive partitioning strategy to divide a large scene into multiple cells, where the training cameras and point cloud are properly distributed with an airspace-aware visibility criterion. These cells are merged into a complete scene after parallel optimization. We also introduce decoupled appearance modeling into the optimization process to reduce appearance variations in the rendered images. Our approach outperforms existing NeRF-based methods and achieves state-of-the-art results on multiple large scene datasets, enabling fast optimization and high-fidelity real-time rendering.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/59c74feb-7b85-4ca3-a69b-7d65b1cdbfb7)


</details>

[📃 arXiv:2402](https://arxiv.org/pdf/2402.17427) | [⌨️ Code] | [🌐 Project Page](https://vastgaussian.github.io/) | [(unofficial)⌨️ Code](https://github.com/kangpeilun/VastGaussian?tab=readme-ov-file)


#### <summary>Octree-GS: Towards Consistent Real-time Rendering with LOD-Structured 3D Gaussians
Authors: Kerui Ren, Lihan Jiang, Tao Lu, Mulin Yu, Linning Xu, Zhangkai Ni, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
The recent 3D Gaussian splatting (3D-GS) has shown remarkable rendering fidelity and efficiency compared to NeRF-based neural scene representations. While demonstrating the potential for real-time rendering, 3D-GS encounters rendering bottlenecks in large scenes with complex details due to an excessive number of Gaussian primitives located within the viewing frustum. This limitation is particularly noticeable in zoom-out views and can lead to inconsistent rendering speeds in scenes with varying details. Moreover, it often struggles to capture the corresponding level of details at different scales with its heuristic density control operation. Inspired by the Level-of-Detail (LOD) techniques, we introduce Octree-GS, featuring an LOD-structured 3D Gaussian approach supporting level-of-detail decomposition for scene representation that contributes to the final rendering results. Our model dynamically selects the appropriate level from the set of multi-resolution anchor points, ensuring consistent rendering performance with adaptive LOD adjustments while maintaining high-fidelity rendering results.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4adb3feb-4df8-4a16-8788-e3b1f06ffbbb)


</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.17898) | [⌨️ Code](https://github.com/city-super/Octree-GS) | [🌐 Project Page](https://city-super.github.io/octree-gs/)


#### <summary>EfficientGS: Streamlining Gaussian Splatting for Large-Scale High-Resolution Scene Representation
Authors: Wenkai Liu, Tao Guan, Bin Zhu, Lili Ju, Zikai Song, Dan Li, Yuesong Wang, Wei Yang
<details span>
<summary><b>Abstract</b></summary>
In the domain of 3D scene representation, 3D Gaussian Splatting (3DGS) has emerged as a pivotal technology. However, its application to large-scale, high-resolution scenes (exceeding 4k×4k pixels) is hindered by the excessive computational requirements for managing a large number of Gaussians. Addressing this, we introduce 'EfficientGS', an advanced approach that optimizes 3DGS for high-resolution, large-scale scenes. We analyze the densification process in 3DGS and identify areas of Gaussian over-proliferation. We propose a selective strategy, limiting Gaussian increase to key primitives, thereby enhancing the representational efficiency. Additionally, we develop a pruning mechanism to remove redundant Gaussians, those that are merely auxiliary to adjacent ones. For further enhancement, we integrate a sparse order increment for Spherical Harmonics (SH), designed to alleviate storage constraints and reduce training overhead. Our empirical evaluations, conducted on a range of datasets including extensive 4K+ aerial images, demonstrate that 'EfficientGS' not only expedites training and rendering times but also achieves this with a model size approximately tenfold smaller than conventional 3DGS while maintaining high rendering fidelity.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/5fb5dcb4-ade4-4e35-847c-5ff3e8658eb2)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.12777.pdf) | [⌨️ Code] | [🌐 Project Page]


#### <summary>CityGaussian: Real-time High-quality Large-Scale Scene Rendering with Gaussians

Authors: Yang Liu, He Guan, Chuanchen Luo, Lue Fan, Junran Peng, Zhaoxiang Zhang
<details span>
<summary><b>Abstract</b></summary>
The advancement of real-time 3D scene reconstruction and novel view synthesis has been significantly propelled by 3D Gaussian Splatting (3DGS). However, effectively training large-scale 3DGS and rendering it in real-time across various scales remains challenging. This paper introduces CityGaussian (CityGS), which employs a novel divide-and-conquer training approach and Level-of-Detail (LoD) strategy for efficient large-scale 3DGS training and rendering. Specifically, the global scene prior and adaptive training data selection enables efficient training and seamless fusion. Based on fused Gaussian primitives, we generate different detail levels through compression, and realize fast rendering across various scales through the proposed block-wise detail levels selection and aggregation strategy. Extensive experimental results on large-scale scenes demonstrate that our approach attains state-of-theart rendering quality, enabling consistent real-time rendering of largescale scenes across vastly different scales.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/5b8a439a-f6c3-47dc-a713-0c1d59c34f86)
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4e9d4be3-e13f-463e-8c1c-54cf45734e3a)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.01133) | [⌨️ Code](https://github.com/DekuLiuTesla/CityGaussian) | [🌐 Project Page](https://dekuliutesla.github.io/citygs/)





#### <summary>Real-Time View Synthesis for Large Scenes with Millions of Square Meters

Authors: Qing Shuai  Haoyu Guo  Zhen Xu  Haotong Lin   Sida Peng   Hujun Bao   Xiaowei Zhou
<details span>
<summary><b>Abstract</b></summary>
This paper tackles the challenge of high-quality, real-time rendering of large-scale scenes with millions of square meters. The recently proposed 3DGS has demonstrated exceptional rendering quality and speed, but it typically requires a large amount of Gaussian primitives to model complex 3D scenes in high fidelity. When users need to holistically view such scenes, the 3DGS model falls short in rendering excessive Gaussians in real time. To solve this issue, we propose a novel representation named Level of Gaussians (LoG) for efficiently rendering 3D scenes, inspired by the classical idea of levels of detail (LOD) in rendering: fine details are essential for close views but become redundant for distant views. We implement LoG as a tree structure storing Gaussians and devise a progressive training strategy to reconstruct it from images in an end-to-end manner, which also provides effective regularization and helps overcome the local minima. In the rendering phase, the optimal level of Gaussians is adaptively selected based on the viewer's distance and angle. Experiments show that our approach enables real-time and high-quality rendering of areas spanning millions of square meters, representing a significant advancement in rendering large-scale scenes.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/e7f56168-8979-4708-8269-1e49193d392b)


</details>

[📃 arXiv:24xx] | [⌨️ Code](https://github.com/zju3dv/LoG) | [🌐 Project Page](https://zju3dv.github.io/LoG_webpage/)

#### <summary>A Hierarchical 3D Gaussian Representation for Real-Time Rendering of Very Large Datasets

Authors: Bernhard Kerbl, Andréas Meuleman, Georgios Kopanas, Michael Wimmer, Alexandre Lanvin, George Drettakis
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis has seen major advances in recent years, with 3D Gaussian splatting offering an excellent level of visual quality, fast training and real-time rendering. However, the resources needed for training and rendering inevitably limit the size of the captured scenes that can be represented with good visual quality.

We introduce a hierarchy of 3D Gaussians that preserves visual quality for very large scenes, while offering an efficient Level-of-Detail (LOD) solution for efficient rendering of distant content with effective level selection and smooth transitions between levels. We introduce a divide-and-conquer approach that allows us to train very large scenes in independent chunks. We consolidate the chunks into a hierarchy that can be optimized to further improve visual quality of Gaussians merged into intermediate nodes.

Very large captures typically have sparse coverage of the scene, presenting many challenges to the original 3D Gaussian splatting training method; we adapt and regularize training to account for these is- sues. We present a complete solution, that enables real-time rendering of very large scenes and can adapt to available resources thanks to our LOD method. We show results for captured scenes with up to tens of thousands of images with a simple and affordable rig, covering trajectories of up to several kilometers and lasting up to one hour.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d4091762-7533-4f68-a992-218b55acfc00)


</details>

[📃 2405](https://repo-sam.inria.fr/fungraph/hierarchical-3d-gaussians/hierarchical-3d-gaussians_low.pdf) | [📃 arXiv:2406](https://arxiv.org/pdf/2406.12080) | [⌨️ Code](https://github.com/graphdeco-inria/hierarchical-3d-gaussians) | [🌐 Project Page](https://repo-sam.inria.fr/fungraph/hierarchical-3d-gaussians/)


#### <summary>S3Gaussian: Self-Supervised Street Gaussians for Autonomous Driving
Authors: Nan Huang, Xiaobao Wei, Wenzhao Zheng, Pengju An, Ming Lu, Wei Zhan, Masayoshi Tomizuka, Kurt Keutzer, Shanghang Zhang
<details span>
<summary><b>Abstract</b></summary>
Photorealistic 3D reconstruction of street scenes is a critical technique for developing real-world simulators for autonomous driving. Despite the efficacy of Neural Radiance Fields (NeRF) for driving scenes, 3D Gaussian Splatting (3DGS) emerges as a promising direction due to its faster speed and more explicit representation. However, most existing street 3DGS methods require tracked 3D vehicle bounding boxes to decompose the static and dynamic elements for effective reconstruction, limiting their applications for in-the-wild scenarios. To facilitate efficient 3D scene reconstruction without costly annotations, we propose a self-supervised street Gaussian (S3Gaussian) method to decompose dynamic and static elements from 4D consistency. We represent each scene with 3D Gaussians to preserve the explicitness and further accompany them with a spatial-temporal field network to compactly model the 4D dynamics. We conduct extensive experiments on the challenging Waymo-Open dataset to evaluate the effectiveness of our method. Our S3Gaussian demonstrates the ability to decompose static and dynamic scenes and achieves the best performance without using 3D annotations.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/cd6040d0-1145-4b68-a204-5eb96a13fc71)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20323) | [⌨️ Code](https://github.com/nnanhuang/S3Gaussian/) | [🌐 Project Page](https://wzzheng.net/S3Gaussian/)



#### <summary>DoGaussian: Distributed-Oriented Gaussian Splatting for Large-Scale 3D Reconstruction Via Gaussian Consensus

Authors: Yu Chen, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
The recent advances in 3D Gaussian Splatting (3DGS) show promising results on the novel view synthesis (NVS) task. With its superior rendering performance and high-fidelity rendering quality, 3DGS is excelling at its previous NeRF counterparts. The most recent 3DGS method focuses either on improving the instability of rendering efficiency or reducing the model size. On the other hand, the training efficiency of 3DGS on large-scale scenes has not gained much attention. In this work, we propose DoGaussian, a method that trains 3DGS distributedly. Our method first decomposes a scene into K blocks and then introduces the Alternating Direction Method of Multipliers (ADMM) into the training procedure of 3DGS. During training, our DoGaussian maintains one global 3DGS model on the master node and K local 3DGS models on the slave nodes. The K local 3DGS models are dropped after training and we only query the global 3DGS model during inference. The training time is reduced by scene decomposition, and the training convergence and stability are guaranteed through the consensus on the shared 3D Gaussians. Our method accelerates the training of 3DGS by 6+ times when evaluated on large-scale scenes while concurrently achieving state-of-the-art rendering quality.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/1a533b9d-df74-4994-89d6-35a1ffc2c98a)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.13943) | [⌨️ Code](https://github.com/aibluefisher/DoGaussian) | [🌐 Project Page](https://aibluefisher.github.io/DoGaussian/)


#### <summary>SA-GS: Semantic-Aware Gaussian Splatting for Large Scene Reconstruction with Geometry Constrain

Authors: Butian Xiong, Xiaoyu Ye, Tze Ho Elden Tse, Kai Han, Shuguang Cui, Zhen Li
<details span>
<summary><b>Abstract</b></summary>
With the emergence of Gaussian Splats, recent efforts have focused on large-scale scene geometric reconstruction. However, most of these efforts either concentrate on memory reduction or spatial space division, neglecting information in the semantic space. In this paper, we propose a novel method, named SA-GS, for fine-grained 3D geometry reconstruction using semantic-aware 3D Gaussian Splats. Specifically, we leverage prior information stored in large vision models such as SAM and DINO to generate semantic masks. We then introduce a geometric complexity measurement function to serve as soft regularization, guiding the shape of each Gaussian Splat within specific semantic areas. Additionally, we present a method that estimates the expected number of Gaussian Splats in different semantic areas, effectively providing a lower bound for Gaussian Splats in these areas. Subsequently, we extract the point cloud using a novel probability density-based extraction method, transforming Gaussian Splats into a point cloud crucial for downstream tasks. Our method also offers the potential for detailed semantic inquiries while maintaining high image-based reconstruction results. We provide extensive experiments on publicly available large-scale scene reconstruction datasets with highly accurate point clouds as ground truth and our novel dataset. Our results demonstrate the superiority of our method over current state-of-the-art Gaussian Splats reconstruction methods by a significant margin in terms of geometric-based measurement metrics.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d1ae147b-fa98-4940-9058-12fe1c8502db)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16923) | [⌨️ Code](https://github.com/saliteta/SA-GS-CODE) | [🌐 Project Page](https://saliteta.github.io/SA-GS/)



#### <summary>PyGS: Large-scale Scene Representation with Pyramidal 3D Gaussian Splatting

Authors: Zipeng Wang, Dan Xu
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRFs) have demonstrated remarkable proficiency in synthesizing photorealistic images of large-scale scenes. However, they are often plagued by a loss of fine details and long rendering durations. 3D Gaussian Splatting has recently been introduced as a potent alternative, achieving both high-fidelity visual results and accelerated rendering performance. Nonetheless, scaling 3D Gaussian Splatting is fraught with challenges. Specifically, large-scale scenes grapples with the integration of objects across multiple scales and disparate viewpoints, which often leads to compromised efficacy as the Gaussians need to balance between detail levels. Furthermore, the generation of initialization points via COLMAP from large-scale dataset is both computationally demanding and prone to incomplete reconstructions. To address these challenges, we present Pyramidal 3D Gaussian Splatting (PyGS) with NeRF Initialization. Our approach represent the scene with a hierarchical assembly of Gaussians arranged in a pyramidal fashion. The top level of the pyramid is composed of a few large Gaussians, while each subsequent layer accommodates a denser collection of smaller Gaussians. We effectively initialize these pyramidal Gaussians through sampling a rapidly trained grid-based NeRF at various frequencies. We group these pyramidal Gaussians into clusters and use a compact weighting network to dynamically determine the influence of each pyramid level of each cluster considering camera viewpoint during rendering. Our method achieves a significant performance leap across multiple large-scale datasets and attains a rendering time that is over 400 times faster than current state-of-the-art approaches.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/58d48965-9dbf-4188-85ea-78b67d82b0d2)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16829) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Dynamic 3D Gaussian Fields for Urban Areas

Authors: Tobias Fischer, Jonas Kulhanek, Samuel Rota Bulò, Lorenzo Porzi, Marc Pollefeys, Peter Kontschieder
<details span>
<summary><b>Abstract</b></summary>
We present an efficient neural 3D scene representation for novel-view synthesis (NVS) in large-scale, dynamic urban areas. Existing works are not well suited for applications like mixed-reality or closed-loop simulation due to their limited visual quality and non-interactive rendering speeds. Recently, rasterization-based approaches have achieved high-quality NVS at impressive speeds. However, these methods are limited to small-scale, homogeneous data, i.e. they cannot handle severe appearance and geometry variations due to weather, season, and lighting and do not scale to larger, dynamic areas with thousands of images. We propose 4DGF, a neural scene representation that scales to large-scale dynamic urban areas, handles heterogeneous input data, and substantially improves rendering speeds. We use 3D Gaussians as an efficient geometry scaffold while relying on neural fields as a compact and flexible appearance model. We integrate scene dynamics via a scene graph at global scale while modeling articulated motions on a local level via deformations. This decomposed approach enables flexible scene composition suitable for real-world applications. In experiments, we surpass the state-of-the-art by over 3 dB in PSNR and more than 200 times in rendering speed.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/bdea228e-d324-4ca0-bd0a-ba9194c73a3e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.03175) | [⌨️ Code](https://github.com/tobiasfshr/map4d) | [🌐 Project Page](https://tobiasfshr.github.io/pub/4dgf/)


#### <summary>GaussianCity: Generative Gaussian Splatting for Unbounded 3D City Generation

Authors: Haozhe Xie, Zhaoxi Chen, Fangzhou Hong, Ziwei Liu
<details span>
<summary><b>Abstract</b></summary>
3D city generation with NeRF-based methods shows promising generation results but is computationally inefficient. Recently 3D Gaussian Splatting (3D-GS) has emerged as a highly efficient alternative for object-level 3D generation. However, adapting 3D-GS from finite-scale 3D objects and humans to infinite-scale 3D cities is non-trivial. Unbounded 3D city generation entails significant storage overhead (out-of-memory issues), arising from the need to expand points to billions, often demanding hundreds of Gigabytes of VRAM for a city scene spanning 10km^2. In this paper, we propose GaussianCity, a generative Gaussian Splatting framework dedicated to efficiently synthesizing unbounded 3D cities with a single feed-forward pass. Our key insights are two-fold: 1) Compact 3D Scene Representation: We introduce BEV-Point as a highly compact intermediate representation, ensuring that the growth in VRAM usage for unbounded scenes remains constant, thus enabling unbounded city generation. 2) Spatial-aware Gaussian Attribute Decoder: We present spatial-aware BEV-Point decoder to produce 3D Gaussian attributes, which leverages Point Serializer to integrate the structural and contextual characteristics of BEV points. Extensive experiments demonstrate that GaussianCity achieves state-of-the-art results in both drone-view and street-view 3D city generation. Notably, compared to CityDreamer, GaussianCity exhibits superior performance with a speedup of 60 times (10.72 FPS v.s. 0.18 FPS).

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/66803887-d85f-4705-a097-0cd1a8760d70)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.06526) | [⌨️ Code](https://github.com/hzxie/GaussianCity) | [🌐 Project Page](https://www.infinitescript.com/project/gaussian-city)


#### <summary>RetinaGS: Scalable Training for Dense Scene Rendering with Billion-Scale 3D Gaussians

Authors: Bingling Li, Shengyi Chen, Luchao Wang, Kaimin He, Sijie Yan, Yuanjun Xiong
<details span>
<summary><b>Abstract</b></summary>
In this work, we explore the possibility of training high-parameter 3D Gaussian splatting (3DGS) models on large-scale, high-resolution datasets. We design a general model parallel training method for 3DGS, named RetinaGS, which uses a proper rendering equation and can be applied to any scene and arbitrary distribution of Gaussian primitives. It enables us to explore the scaling behavior of 3DGS in terms of primitive numbers and training resolutions that were difficult to explore before and surpass previous state-of-the-art reconstruction quality. We observe a clear positive trend of increasing visual quality when increasing primitive numbers with our method. We also demonstrate the first attempt at training a 3DGS model with more than one billion primitives on the full MatrixCity dataset that attains a promising visual quality.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/51b3ea3d-206f-415e-ba01-830405ffe9d8)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.11836) | [⌨️ Code] | [🌐 Project Page]


#### <summary>On Scaling Up 3D Gaussian Splatting Training

Authors: Hexu Zhao, Haoyang Weng, Daohan Lu, Ang Li, Jinyang Li, Aurojit Panda, Saining Xie
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) is increasingly popular for 3D reconstruction due to its superior visual quality and rendering speed. However, 3DGS training currently occurs on a single GPU, limiting its ability to handle high-resolution and large-scale 3D reconstruction tasks due to memory constraints. We introduce Grendel, a distributed system designed to partition 3DGS parameters and parallelize computation across multiple GPUs. As each Gaussian affects a small, dynamic subset of rendered pixels, Grendel employs sparse all-to-all communication to transfer the necessary Gaussians to pixel partitions and performs dynamic load balancing. Unlike existing 3DGS systems that train using one camera view image at a time, Grendel supports batched training with multiple views. We explore various optimization hyperparameter scaling strategies and find that a simple sqrt(batch size) scaling rule is highly effective. Evaluations using large-scale, high-resolution scenes show that Grendel enhances rendering quality by scaling up 3DGS parameters across multiple GPUs. On the Rubble dataset, we achieve a test PSNR of 27.28 by distributing 40.4 million Gaussians across 16 GPUs, compared to a PSNR of 26.28 using 11.2 million Gaussians on a single GPU.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/1cfd6eaf-73ef-4beb-9d75-b1d3d7845460)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.18533) | [⌨️ Code](https://github.com/nyu-systems/Grendel-GS) | [🌐 Project Page](https://daohanlu.github.io/scaling-up-3dgs/)

#### <summary>Enhancement of 3D Gaussian Splatting using Raw Mesh for Photorealistic Recreation of Architectures

Authors: Ruizhe Wang, Chunliang Hua, Tomakayev Shingys, Mengyuan Niu, Qingxin Yang, Lizhong Gao, Yi Zheng, Junyan Yang, Qiao Wang
<details span>
<summary><b>Abstract</b></summary>
The photorealistic reconstruction and rendering of architectural scenes have extensive applications in industries such as film, games, and transportation. It also plays an important role in urban planning, architectural design, and the city's promotion, especially in protecting historical and cultural relics. The 3D Gaussian Splatting, due to better performance over NeRF, has become a mainstream technology in 3D reconstruction. Its only input is a set of images but it relies heavily on geometric parameters computed by the SfM process. At the same time, there is an existing abundance of raw 3D models, that could inform the structural perception of certain buildings but cannot be applied. In this paper, we propose a straightforward method to harness these raw 3D models to guide 3D Gaussians in capturing the basic shape of the building and improve the visual quality of textures and details when photos are captured non-systematically. This exploration opens up new possibilities for improving the effectiveness of 3D reconstruction techniques in the field of architectural design.



</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.15435) | [⌨️ Code] | [🌐 Project Page]


#### <summary>FlashGS: Efficient 3D Gaussian Splatting for Large-scale and High-resolution Rendering

Authors: Guofeng Feng, Siyan Chen, Rong Fu, Zimu Liao, Yi Wang, Tao Liu, Zhilin Pei, Hengjie Li, Xingcheng Zhang, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
This work introduces FlashGS, an open-source CUDA Python library, designed to facilitate the efficient differentiable rasterization of 3D Gaussian Splatting through algorithmic and kernel-level optimizations. FlashGS is developed based on the observations from a comprehensive analysis of the rendering process to enhance computational efficiency and bring the technique to wide adoption. The paper includes a suite of optimization strategies, encompassing redundancy elimination, efficient pipelining, refined control and scheduling mechanisms, and memory access optimizations, all of which are meticulously integrated to amplify the performance of the rasterization process. An extensive evaluation of FlashGS' performance has been conducted across a diverse spectrum of synthetic and real-world large-scale scenes, encompassing a variety of image resolutions. The empirical findings demonstrate that FlashGS consistently achieves an average 4x acceleration over mobile consumer GPUs, coupled with reduced memory consumption. These results underscore the superior performance and resource optimization capabilities of FlashGS, positioning it as a formidable tool in the domain of 3D rendering.

![image](https://github.com/user-attachments/assets/8fb5029d-03a7-4ecb-b2a9-48de2139f17b)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.07967) | [⌨️ Code](https://github.com/InternLandMark/FlashGS) | [🌐 Project Page]

#### <summary>FLoD: Integrating Flexible Level of Detail into 3D Gaussian Splatting for Customizable Rendering

Authors: Yunji Seo, Young Sun Choi, Hyun Seung Son, Youngjung Uh
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) achieves fast and high-quality renderings by using numerous small Gaussians, which leads to significant memory consumption. This reliance on a large number of Gaussians restricts the application of 3DGS-based models on low-cost devices due to memory limitations. However, simply reducing the number of Gaussians to accommodate devices with less memory capacity leads to inferior quality compared to the quality that can be achieved on high-end hardware. To address this lack of scalability, we propose integrating a Flexible Level of Detail (FLoD) to 3DGS, to allow a scene to be rendered at varying levels of detail according to hardware capabilities. While existing 3DGSs with LoD focus on detailed reconstruction, our method provides reconstructions using a small number of Gaussians for reduced memory requirements, and a larger number of Gaussians for greater detail. Experiments demonstrate our various rendering options with tradeoffs between rendering quality and memory usage, thereby allowing real-time rendering across different memory constraints. Furthermore, we show that our method generalizes to different 3DGS frameworks, indicating its potential for integration into future state-of-the-art developments.

![image](https://github.com/user-attachments/assets/f51c889e-ed15-49d0-b799-13583d7c3942)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.12894) | [⌨️ Code] | [🌐 Project Page](https://3dgs-flod.github.io/flod.github.io/)

#### <summary>Drone-assisted Road Gaussian Splatting with Cross-view Uncertainty
>  *assist in the synthesis of areas where ground images have poor learning results*

Authors: Saining Zhang, Baijun Ye, Xiaoxue Chen, Yuantao Chen, Zongzheng Zhang, Cheng Peng, Yongliang Shi, Hao Zhao
<details span>
<summary><b>Abstract</b></summary>
Robust and realistic rendering for large-scale road scenes is essential in autonomous driving simulation. Recently, 3D Gaussian Splatting (3D-GS) has made groundbreaking progress in neural rendering, but the general fidelity of large-scale road scene renderings is often limited by the input imagery, which usually has a narrow field of view and focuses mainly on the street-level local area. Intuitively, the data from the drone's perspective can provide a complementary viewpoint for the data from the ground vehicle's perspective, enhancing the completeness of scene reconstruction and rendering. However, training naively with aerial and ground images, which exhibit large view disparity, poses a significant convergence challenge for 3D-GS, and does not demonstrate remarkable improvements in performance on road views. In order to enhance the novel view synthesis of road views and to effectively use the aerial information, we design an uncertainty-aware training method that allows aerial images to assist in the synthesis of areas where ground images have poor learning outcomes instead of weighting all pixels equally in 3D-GS training like prior work did. We are the first to introduce the cross-view uncertainty to 3D-GS by matching the car-view ensemble-based rendering uncertainty to aerial images, weighting the contribution of each pixel to the training process. Additionally, to systematically quantify evaluation metrics, we assemble a high-quality synthesized dataset comprising both aerial and ground images for road scenes.
 
![image](https://github.com/user-attachments/assets/d5e9aa3f-4cc4-4fec-932e-0521106fe342)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.15242) | [⌨️ Code](https://github.com/SainingZhang/uc-gs/) | [🌐 Project Page](https://sainingzhang.github.io/project/uc-gs/)


#### <summary>LapisGS: Layered Progressive 3D Gaussian Splatting for Adaptive Streaming
>  *L1 loss is not sensitive to blurriness or low-resolution artifacts that do not alter the image’s structure*

Authors: Yuang Shi, Simone Gasparini, Géraldine Morin, Wei Tsang Ooi
<details span>
<summary><b>Abstract</b></summary>
The rise of Extended Reality (XR) requires efficient streaming of 3D online worlds, challenging current 3DGS representations to adapt to bandwidth-constrained environments. This paper proposes LapisGS, a layered 3DGS that supports adaptive streaming and progressive rendering. Our method constructs a layered structure for cumulative representation, incorporates dynamic opacity optimization to maintain visual fidelity, and utilizes occupancy maps to efficiently manage Gaussian splats. This proposed model offers a progressive representation supporting a continuous rendering quality adapted for bandwidth-aware streaming. Extensive experiments validate the effectiveness of our approach in balancing visual fidelity with the compactness of the model, with up to 50.71% improvement in SSIM, 286.53% improvement in LPIPS, and 318.41% reduction in model size, and shows its potential for bandwidth-adapted 3D streaming and rendering applications.
 
![image](https://github.com/user-attachments/assets/1e1d247d-1514-493d-906e-cefd70b62a78)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.14823) | [⌨️ Code] | [🌐 Project Page]


#### <summary>3D Gaussian Splatting for Large-scale 3D Surface Reconstruction from Aerial Images
>  *Ray-Gaussian Intersection*

Authors: YuanZheng Wu, Jin Liu, Shunping Ji
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has garnered significant attention. However, the unstructured nature of 3DGS poses challenges for large-scale surface reconstruction from aerial images. To address this gap, we propose the first large-scale surface reconstruction method for multi-view stereo (MVS) aerial images based on 3DGS, named Aerial Gaussian Splatting (AGS). Initially, we introduce a data chunking method tailored for large-scale aerial imagery, making the modern 3DGS technology feasible for surface reconstruction over extensive scenes. Additionally, we integrate the Ray-Gaussian Intersection method to obtain normal and depth information, facilitating geometric constraints. Finally, we introduce a multi-view geometric consistency constraint to enhance global geometric consistency and improve reconstruction accuracy. Our experiments on multiple datasets demonstrate for the first time that the GS-based technique can match traditional aerial MVS methods on geometric accuracy, and beat state-of-the-art GS-based methods on geometry and rendering quality.
 
![image](https://github.com/user-attachments/assets/1fb73098-8efd-4fd3-8c42-2d796d70a93a)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.00381) | [⌨️ Code] | [🌐 Project Page]

#### <summary>GigaGS: Scaling up Planar-Based 3D Gaussians for Large Scene Surface Reconstruction
>  *large-scale surface reconstruction*

Authors: Junyi Chen, Weicai Ye, Yifan Wang, Danpeng Chen, Di Huang, Wanli Ouyang, Guofeng Zhang, Yu Qiao, Tong He
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has shown promising performance in novel view synthesis. Previous methods adapt it to obtaining surfaces of either individual 3D objects or within limited scenes. In this paper, we make the first attempt to tackle the challenging task of large-scale scene surface reconstruction. This task is particularly difficult due to the high GPU memory consumption, different levels of details for geometric representation, and noticeable inconsistencies in appearance. To this end, we propose GigaGS, the first work for high-quality surface reconstruction for large-scale scenes using 3DGS. GigaGS first applies a partitioning strategy based on the mutual visibility of spatial regions, which effectively grouping cameras for parallel processing. To enhance the quality of the surface, we also propose novel multi-view photometric and geometric consistency constraints based on Level-of-Detail representation. In doing so, our method can reconstruct detailed surface structures. Comprehensive experiments are conducted on various datasets. The consistent improvement demonstrates the superiority of GigaGS.
 
![image](https://github.com/user-attachments/assets/cc844c41-e969-4116-86df-69e4937e4264)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.06685) | [⌨️ Code](https://github.com/Open3DVLab/GigaGS) | [🌐 Project Page](https://open3dvlab.github.io/GigaGS/)

#### <summary>DENSER: 3D Gaussians Splatting for Scene Reconstruction of Dynamic Urban Environments
>  *introduce and integrate a new method aiming at dynamically estimating SH bases using wavelets, resulting in a better representation of dynamic objects appearance in both space and time*

Authors: Junyi Chen, Weicai Ye, Yifan Wang, Danpeng Chen, Di Huang, Wanli Ouyang, Guofeng Zhang, Yu Qiao, Tong He
<details span>
<summary><b>Abstract</b></summary>
This paper presents DENSER, an efficient and effective approach leveraging 3D Gaussian splatting (3DGS) for the reconstruction of dynamic urban environments. While several methods for photorealistic scene representations, both implicitly using neural radiance fields (NeRF) and explicitly using 3DGS have shown promising results in scene reconstruction of relatively complex dynamic scenes, modeling the dynamic appearance of foreground objects tend to be challenging, limiting the applicability of these methods to capture subtleties and details of the scenes, especially far dynamic objects. To this end, we propose DENSER, a framework that significantly enhances the representation of dynamic objects and accurately models the appearance of dynamic objects in the driving scene. Instead of directly using Spherical Harmonics (SH) to model the appearance of dynamic objects, we introduce and integrate a new method aiming at dynamically estimating SH bases using wavelets, resulting in better representation of dynamic objects appearance in both space and time. Besides object appearance, DENSER enhances object shape representation through densification of its point cloud across multiple scene frames, resulting in faster convergence of model training. Extensive evaluations on KITTI dataset show that the proposed approach significantly outperforms state-of-the-art methods by a wide margin.
 
![image](https://github.com/user-attachments/assets/a48c93e4-7eea-452e-9dc9-70850bfe683e)


</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.10041) | [⌨️ Code](https://github.com/sntubix/denser) | [🌐 Project Page]


#### <summary>MesonGS: Post-training Compression of 3D Gaussians via Efficient Attribute Transformation
>  *view-dependent and view-independent factors for gaussian primitive importance. notice that 40% of the Gaussians contain over 80% of the importance. RAHT involves taking voxelized coordinates from octree and converting the corresponding attributes into transformed coefficients.*

Authors: Shuzhao Xie, Weixiang Zhang, Chen Tang, Yunpeng Bai, Rongwei Lu, Shijia Ge, Zhi Wang
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting demonstrates excellent quality and speed in novel view synthesis. Nevertheless, the huge file size of the 3D Gaussians presents challenges for transmission and storage. Current works design compact models to replace the substantial volume and attributes of 3D Gaussians, along with intensive training to distill information. These endeavors demand considerable training time, presenting formidable hurdles for practical deployment. To this end, we propose MesonGS, a codec for post-training compression of 3D Gaussians. Initially, we introduce a measurement criterion that considers both view-dependent and view-independent factors to assess the impact of each Gaussian point on the rendering output, enabling the removal of insignificant points. Subsequently, we decrease the entropy of attributes through two transformations that complement subsequent entropy coding techniques to enhance the file compression rate. More specifically, we first replace rotation quaternions with Euler angles; then, we apply region adaptive hierarchical transform to key attributes to reduce entropy. Lastly, we adopt finer-grained quantization to avoid excessive information loss. Moreover, a well-crafted finetune scheme is devised to restore quality. Extensive experiments demonstrate that MesonGS significantly reduces the size of 3D Gaussians while preserving competitive quality.
 
![image](https://github.com/user-attachments/assets/e77c73b8-752a-4914-bd7f-4fc30fcb8de2)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.09756) | [⌨️ Code](https://github.com/ShuzhaoXie/MesonGS) | [🌐 Project Page](https://shuzhaoxie.github.io/mesongs/)


#### <summary>GaRField++: Reinforced Gaussian Radiance Fields for Large-Scale 3D Scene Reconstruction
>  *Partitioning + GOF Ray-Gaussian render + abs density control + ConvKAN-based Decoupled Appearance Modeling*

Authors: Hanyue Zhang, Zhiliu Yang, Xinhe Zuo, Yuxin Tong, Ying Long, Chen Liu
<details span>
<summary><b>Abstract</b></summary>
This paper proposes a novel framework for large-scale scene reconstruction based on 3D Gaussian splatting (3DGS) and aims to address the scalability and accuracy challenges faced by existing methods. For tackling the scalability issue, we split the large scene into multiple cells, and the candidate point-cloud and camera views of each cell are correlated through a visibility-based camera selection and a progressive point-cloud extension. To reinforce the rendering quality, three highlighted improvements are made in comparison with vanilla 3DGS, which are a strategy of the ray-Gaussian intersection and the novel Gaussians density control for learning efficiency, an appearance decoupling module based on ConvKAN network to solve uneven lighting conditions in large-scale scenes, and a refined final loss with the color loss, the depth distortion loss, and the normal consistency loss. Finally, the seamless stitching procedure is executed to merge the individual Gaussian radiance field for novel view synthesis across different cells. Evaluation of Mill19, Urban3D, and MatrixCity datasets shows that our method consistently generates more high-fidelity rendering results than state-of-the-art methods of large-scale scene reconstruction. We further validate the generalizability of the proposed approach by rendering on self-collected video clips recorded by a commercial drone.
 
![image](https://github.com/user-attachments/assets/181699a6-7529-4089-9979-5abaf88090ea)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.12774) | [⌨️ Code](https://github.com/ShuzhaoXie/MesonGS) | [🌐 Project Page](https://shuzhaoxie.github.io/mesongs/)


#### <summary>StreetSurfGS: Scalable Urban Street Surface Reconstruction with Planar-based Gaussian Splatting
>  *SAM for Edge Filtering*

Authors: Xiao Cui, Weicai Ye, Yifan Wang, Guofeng Zhang, Wengang Zhou, Tong He, Houqiang Li
<details span>
<summary><b>Abstract</b></summary>
Reconstructing urban street scenes is crucial due to its vital role in applications such as autonomous driving and urban planning. These scenes are characterized by long and narrow camera trajectories, occlusion, complex object relationships, and data sparsity across multiple scales. Despite recent advancements, existing surface reconstruction methods, which are primarily designed for object-centric scenarios, struggle to adapt effectively to the unique characteristics of street scenes. To address this challenge, we introduce StreetSurfGS, the first method to employ Gaussian Splatting specifically tailored for scalable urban street scene surface reconstruction. StreetSurfGS utilizes a planar-based octree representation and segmented training to reduce memory costs, accommodate unique camera characteristics, and ensure scalability. Additionally, to mitigate depth inaccuracies caused by object overlap, we propose a guided smoothing strategy within regularization to eliminate inaccurate boundary points and outliers. Furthermore, to address sparse views and multi-scale challenges, we use a dual-step matching strategy that leverages adjacent and long-term information. Extensive experiments validate the efficacy of StreetSurfGS in both novel view synthesis and surface reconstruction.
 
![image](https://github.com/user-attachments/assets/bd8aeec0-ad0d-42a2-9fe6-15d58710c1fe)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2410.04354) | [⌨️ Code] | [🌐 Project Page]



<br>
<br>

## Edit


#### <summary>StylizedGS: Controllable Stylization for 3D Gaussian Splatting

Authors: Dingxi Zhang, Zhuoxun Chen, Yu-Jie Yuan, Fang-Lue Zhang, Zhenliang He, Shiguang Shan, Lin Gao
<details span>
<summary><b>Abstract</b></summary>
With the rapid development of XR, 3D generation and editing are becoming more and more important, among which, stylization is an important tool of 3D appearance editing. It can achieve consistent 3D artistic stylization given a single reference style image and thus is a user-friendly editing way. However, recent NeRF-based 3D stylization methods face efficiency issues that affect the actual user experience and the implicit nature limits its ability to transfer the geometric pattern styles. Additionally, the ability for artists to exert flexible control over stylized scenes is considered highly desirable, fostering an environment conducive to creative exploration. In this paper, we introduce StylizedGS, a 3D neural style transfer framework with adaptable control over perceptual factors based on 3D Gaussian Splatting (3DGS) representation. The 3DGS brings the benefits of high efficiency. We propose a GS filter to eliminate floaters in the reconstruction which affects the stylization effects before stylization. Then the nearest neighbor-based style loss is introduced to achieve stylization by fine-tuning the geometry and color parameters of 3DGS, while a depth preservation loss with other regularizations is proposed to prevent the tampering of geometry content. Moreover, facilitated by specially designed losses, StylizedGS enables users to control color, stylized scale and regions during the stylization to possess customized capabilities. Our method can attain high-quality stylization results characterized by faithful brushstrokes and geometric consistency with flexible controls. Extensive experiments across various scenes and styles demonstrate the effectiveness and efficiency of our method concerning both stylization quality and inference FPS.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/aab5e330-0233-43d2-96a7-8e6cbf9d13d8)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.05220v1) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Reference-based Controllable Scene Stylization with Gaussian Splatting

Authors: Yiqun Mei, Jiacong Xu, Vishal M. Patel
<details span>
<summary><b>Abstract</b></summary>
Referenced-based scene stylization that edits the appearance based on a content-aligned reference image is an emerging research area. Starting with a pretrained neural radiance field (NeRF), existing methods typically learn a novel appearance that matches the given style. Despite their effectiveness, they inherently suffer from time-consuming volume rendering, and thus are impractical for many real-time applications. In this work, we propose ReGS, which adapts 3D Gaussian Splatting (3DGS) for reference-based stylization to enable real-time stylized view synthesis. Editing the appearance of a pretrained 3DGS is challenging as it uses discrete Gaussians as 3D representation, which tightly bind appearance with geometry. Simply optimizing the appearance as prior methods do is often insufficient for modeling continuous textures in the given reference image. To address this challenge, we propose a novel texture-guided control mechanism that adaptively adjusts local responsible Gaussians to a new geometric arrangement, serving for desired texture details. The proposed process is guided by texture clues for effective appearance editing, and regularized by scene depth for preserving original geometric structure. With these novel designs, we show ReGs can produce state-of-the-art stylization results that respect the reference texture while embracing real-time rendering speed for free-view navigation.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d759a470-45d6-4ca8-940d-b51104608eed)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.07220) | [⌨️ Code] | [🌐 Project Page]


#### <summary>StyleSplat: 3D Object Style Transfer with Gaussian Splatting

Authors: Sahil Jain, Avik Kuthiala, Prabhdeep Singh Sethi, Prakanshul Saxena
<details span>
<summary><b>Abstract</b></summary>
Recent advancements in radiance fields have opened new avenues for creating high-quality 3D assets and scenes. Style transfer can enhance these 3D assets with diverse artistic styles, transforming creative expression. However, existing techniques are often slow or unable to localize style transfer to specific objects. We introduce StyleSplat, a lightweight method for stylizing 3D objects in scenes represented by 3D Gaussians from reference style images. Our approach first learns a photorealistic representation of the scene using 3D Gaussian splatting while jointly segmenting individual 3D objects. We then use a nearest-neighbor feature matching loss to finetune the Gaussians of the selected objects, aligning their spherical harmonic coefficients with the style image to ensure consistency and visual appeal. StyleSplat allows for quick, customizable style transfer and localized stylization of multiple objects within a scene, each with a different style. We demonstrate its effectiveness across various 3D scenes and styles, showcasing enhanced control and customization in 3D creation.

![image](https://github.com/user-attachments/assets/3ceea64b-4b03-4a7b-9d9f-ce586e0c1f7c)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.09473) | [⌨️ Code] | [🌐 Project Page](https://bernard0047.github.io/stylesplat/)



#### <summary>A General Framework to Boost 3D GS Initialization for Text-to-3D Generation by Lexical Richness
Authors: Lutao Jiang, Hangyu Li, Lin Wang
<details span>
<summary><b>Abstract</b></summary>
Text-to-3D content creation has recently received much attention, especially with the prevalence of 3D Gaussians Splatting. In general, GS-based methods comprise two key stages: initialization and rendering optimization. To achieve initialization, existing works directly apply random sphere initialization or 3D diffusion models, e.g., Point-E, to derive the initial shapes. However, such strategies suffer from two critical yet challenging problems: 1) the final shapes are still similar to the initial ones even after training; 2) shapes can be produced only from simple texts, e.g., "a dog", not for lexically richer texts, e.g., "a dog is sitting on the top of the airplane". To address these problems, this paper proposes a novel general framework to boost the 3D GS Initialization for text-to-3D generation upon the lexical richness. Our key idea is to aggregate 3D Gaussians into spatially uniform voxels to represent complex shapes while enabling the spatial interaction among the 3D Gaussians and semantic interaction between Gaussians and texts. Specifically, we first construct a voxelized representation, where each voxel holds a 3D Gaussian with its position, scale, and rotation fixed while setting opacity as the sole factor to determine a position's occupancy. We then design an initialization network mainly consisting of two novel components: 1) Global Information Perception (GIP) block and 2) Gaussians-Text Fusion (GTF) block. Such a design enables each 3D Gaussian to assimilate the spatial information from other areas and semantic information from texts. Extensive experiments show the superiority of our framework of high-quality 3D GS initialization against the existing methods, e.g., Shap-E, by taking lexically simple, medium, and hard texts. Also, our framework can be seamlessly plugged into SoTA training frameworks, e.g., LucidDreamer, for semantically consistent text-to-3D generation.

![image](https://github.com/user-attachments/assets/8385c947-f738-4ad3-9ad1-20dea8f51a20)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.01269) | [⌨️ Code] | [🌐 Project Page](https://vlislab22.github.io/DreamInit/)

#### <summary>InstantStyleGaussian: Efficient Art Style Transfer with 3D Gaussian Splatting
Authors: Xin-Yi Yu, Jun-Xin Yu, Li-Bo Zhou, Yan Wei, Lin-Lin Ou
<details span>
<summary><b>Abstract</b></summary>
We present InstantStyleGaussian, an innovative 3D style transfer method based on the 3D Gaussian Splatting (3DGS) scene representation. By inputting a target style image, it quickly generates new 3D GS scenes. Our approach operates on pre-reconstructed GS scenes, combining diffusion models with an improved iterative dataset update strategy. It utilizes diffusion models to generate target style images, adds these new images to the training dataset, and uses this dataset to iteratively update and optimize the GS scenes. Extensive experimental results demonstrate that our method ensures high-quality stylized scenes while offering significant advantages in style transfer speed and consistency.

![image](https://github.com/user-attachments/assets/b2a46930-0e70-4710-987e-4cfef8cac3cc)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.04249) | [⌨️ Code] | [🌐 Project Page]

#### <summary>3D Gaussian Editing with A Single Image
Authors: Guan Luo, Tian-Xing Xu, Ying-Tian Liu, Xiao-Xiong Fan, Fang-Lue Zhang, Song-Hai Zhang
<details span>
<summary><b>Abstract</b></summary>
The modeling and manipulation of 3D scenes captured from the real world are pivotal in various applications, attracting growing research interest. While previous works on editing have achieved interesting results through manipulating 3D meshes, they often require accurately reconstructed meshes to perform editing, which limits their application in 3D content generation. To address this gap, we introduce a novel single-image-driven 3D scene editing approach based on 3D Gaussian Splatting, enabling intuitive manipulation via directly editing the content on a 2D image plane. Our method learns to optimize the 3D Gaussians to align with an edited version of the image rendered from a user-specified viewpoint of the original scene. To capture long-range object deformation, we introduce positional loss into the optimization process of 3D Gaussian Splatting and enable gradient propagation through reparameterization. To handle occluded 3D Gaussians when rendering from the specified viewpoint, we build an anchor-based structure and employ a coarse-to-fine optimization strategy capable of handling long-range deformation while maintaining structural stability. Furthermore, we design a novel masking strategy to adaptively identify non-rigid deformation regions for fine-scale modeling. Extensive experiments show the effectiveness of our method in handling geometric details, long-range, and non-rigid deformation, demonstrating superior editing flexibility and quality compared to previous approaches.

![image](https://github.com/user-attachments/assets/59305693-d048-499c-804f-f327ef26731d)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.07540) | [⌨️ Code] | [🌐 Project Page]


#### <summary>G-Style: Stylized Gaussian Splatting
>  *CLIP loss for Low-frequency, nearest neighbor feature loss(NNFM) loss for High-frequency*

Authors: Áron Samuel Kovács, Pedro Hermosilla, Renata G. Raidou
<details span>
<summary><b>Abstract</b></summary>
We introduce G-Style, a novel algorithm designed to transfer the style of an image onto a 3D scene represented using Gaussian Splatting. Gaussian Splatting is a powerful 3D representation for novel view synthesis, as -- compared to other approaches based on Neural Radiance Fields -- it provides fast scene renderings and user control over the scene. Recent pre-prints have demonstrated that the style of Gaussian Splatting scenes can be modified using an image exemplar. However, since the scene geometry remains fixed during the stylization process, current solutions fall short of producing satisfactory results. Our algorithm aims to address these limitations by following a three-step process: In a pre-processing step, we remove undesirable Gaussians with large projection areas or highly elongated shapes. Subsequently, we combine several losses carefully designed to preserve different scales of the style in the image, while maintaining as much as possible the integrity of the original scene content. During the stylization process and following the original design of Gaussian Splatting, we split Gaussians where additional detail is necessary within our scene by tracking the gradient of the stylized color. Our experiments demonstrate that G-Style generates high-quality stylizations within just a few minutes, outperforming existing methods both qualitatively and quantitatively.
 
![image](https://github.com/user-attachments/assets/1621f1a9-3999-4d2a-be51-b53cfe6f74e6)

</details>

[📃 arXiv:2408](https://www.arxiv.org/pdf/2408.15695) | [⌨️ Code] | [🌐 Project Page]


#### <summary>SpecGaussian with Latent Features: A High-quality Modeling of the View-dependent Appearance for 3D Gaussian Splatting
> *latent feature for editing?*

Authors: Zhiru Wang, Shiyun Xie, Chengwei Pan, Guoping Wang
<details span>
<summary><b>Abstract</b></summary>
Recently, the 3D Gaussian Splatting (3D-GS) method has achieved great success in novel view synthesis, providing real-time rendering while ensuring high-quality rendering results. However, this method faces challenges in modeling specular reflections and handling anisotropic appearance components, especially in dealing with view-dependent color under complex lighting conditions. Additionally, 3D-GS uses spherical harmonic to learn the color representation, which has limited ability to represent complex scenes. To overcome these challenges, we introduce Lantent-SpecGS, an approach that utilizes a universal latent neural descriptor within each 3D Gaussian. This enables a more effective representation of 3D feature fields, including appearance and geometry. Moreover, two parallel CNNs are designed to decoder the splatting feature maps into diffuse color and specular color separately. A mask that depends on the viewpoint is learned to merge these two colors, resulting in the final rendered image. Experimental results demonstrate that our method obtains competitive performance in novel view synthesis and extends the ability of 3D-GS to handle intricate scenarios with specular reflections.
 
![image](https://github.com/user-attachments/assets/cc2690d5-9e9e-4514-a469-1b980ca2694d)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.05868) | [⌨️ Code](https://github.com/MarcWangzhiru/SpeclatentGS) | [🌐 Project Page]

#### <summary>FlashSplat: 2D to 3D Gaussian Splatting Segmentation Solved Optimally
> *come back later!!!!!*
> *framing the 2D mask lifting in 3D Gaussian Splatting as a Linear Programming (LP) optimization problem, solved in a single step*

Authors: Qiuhong Shen, Xingyi Yang, Xinchao Wang
<details span>
<summary><b>Abstract</b></summary>
This study addresses the challenge of accurately segmenting 3D Gaussian Splatting from 2D masks. Conventional methods often rely on iterative gradient descent to assign each Gaussian a unique label, leading to lengthy optimization and sub-optimal solutions. Instead, we propose a straightforward yet globally optimal solver for 3D-GS segmentation. The core insight of our method is that, with a reconstructed 3D-GS scene, the rendering of the 2D masks is essentially a linear function with respect to the labels of each Gaussian. As such, the optimal label assignment can be solved via linear programming in closed form. This solution capitalizes on the alpha blending characteristic of the splatting process for single step optimization. By incorporating the background bias in our objective function, our method shows superior robustness in 3D segmentation against noises. Remarkably, our optimization completes within 30 seconds, about 50× faster than the best existing methods. Extensive experiments demonstrate the efficiency and robustness of our method in segmenting various scenes, and its superior performance in downstream tasks such as object removal and inpainting.
 
![image](https://github.com/user-attachments/assets/362265c3-3f79-4083-a586-0a70d5e4f9d8)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.08270) | [⌨️ Code](https://github.com/florinshen/FlashSplat) | [🌐 Project Page]

#### <summary>Gradient-Driven 3D Segmentation and Affordance Transfer in Gaussian Splatting Using 2D Masks
> *2D-to-3D affordance transfer*

Authors: Joji Joseph, Bharadwaj Amrutur, Shalabh Bhatnagar
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting has emerged as a powerful 3D scene representation technique, capturing fine details with high efficiency. In this paper, we introduce a novel voting-based method that extends 2D segmentation models to 3D Gaussian splats. Our approach leverages masked gradients, where gradients are filtered by input 2D masks, and these gradients are used as votes to achieve accurate segmentation. As a byproduct, we discovered that inference-time gradients can also be used to prune Gaussians, resulting in up to 21% compression. Additionally, we explore few-shot affordance transfer, allowing annotations from 2D images to be effectively transferred onto 3D Gaussian splats. The robust yet straightforward mathematical formulation underlying this approach makes it a highly effective tool for numerous downstream applications, such as augmented reality (AR), object editing, and robotics. 
 
![image](https://github.com/user-attachments/assets/082890b4-a963-476c-b6ef-74af53a99e39)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.11681) | [⌨️ Code](https://github.com/JojiJoseph/3dgs-gradient-segmentation) | [🌐 Project Page](https://jojijoseph.github.io/3dgs-segmentation/)

#### <summary>WaSt-3D: Wasserstein-2 Distance for Scene-to-Scene Stylization on 3D Gaussians

Authors: Dmytro Kotovenko, Olga Grebenkova, Nikolaos Sarafianos, Avinash Paliwal, Pingchuan Ma, Omid Poursaeed, Sreyas Mohan, Yuchen Fan, Yilei Li, Rakesh Ranjan, Björn Ommer
<details span>
<summary><b>Abstract</b></summary>
While style transfer techniques have been well-developed for 2D image stylization, the extension of these methods to 3D scenes remains relatively unexplored. Existing approaches demonstrate proficiency in transferring colors and textures but often struggle with replicating the geometry of the scenes. In our work, we leverage an explicit Gaussian Splatting (GS) representation and directly match the distributions of Gaussians between style and content scenes using the Earth Mover's Distance (EMD). By employing the entropy-regularized Wasserstein-2 distance, we ensure that the transformation maintains spatial smoothness. Additionally, we decompose the scene stylization problem into smaller chunks to enhance efficiency. This paradigm shift reframes stylization from a pure generative process driven by latent space losses to an explicit matching of distributions between two Gaussian representations. Our method achieves high-resolution 3D stylization by faithfully transferring details from 3D style scenes onto the content scene. Furthermore, WaSt-3D consistently delivers results across diverse content and style scenes without necessitating any training, as it relies solely on optimization-based techniques.
 
![image](https://github.com/user-attachments/assets/52d15d61-1faf-4508-a4e9-5f9ac8cd548a)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.17917) | [⌨️ Code](https://github.com/facebookresearch/WaSt3D) | [🌐 Project Page](https://compvis.github.io/wast3d/)

#### <summary>MiraGe: Editable 2D Images using Gaussian Splatting
>*come back later*

Authors: Joanna Waczyńska, Tomasz Szczepanik, Piotr Borycki, Sławomir Tadeja, Thomas Bohné, Przemysław Spurek
<details span>
<summary><b>Abstract</b></summary>
Implicit Neural Representations (INRs) approximate discrete data through continuous functions and are commonly used for encoding 2D images. Traditional image-based INRs employ neural networks to map pixel coordinates to RGB values, capturing shapes, colors, and textures within the network's weights. Recently, GaussianImage has been proposed as an alternative, using Gaussian functions instead of neural networks to achieve comparable quality and compression. Such a solution obtains a quality and compression ratio similar to classical INR models but does not allow image modification. In contrast, our work introduces a novel method, MiraGe, which uses mirror reflections to perceive 2D images in 3D space and employs flat-controlled Gaussians for precise 2D image editing. Our approach improves the rendering quality and allows realistic image modifications, including human-inspired perception of photos in the 3D world. Thanks to modeling images in 3D space, we obtain the illusion of 3D-based modification in 2D images. We also show that our Gaussian representation can be easily combined with a physics engine to produce physics-based modification of 2D images. Consequently, MiraGe allows for better quality than the standard approach and natural modification of 2D images.
 
![image](https://github.com/user-attachments/assets/11fe3dfd-6636-4746-a53f-0ff8e46cdb15)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.01521) | [⌨️ Code](https://github.com/waczjoan/MiraGe/tree/main) | [🌐 Project Page](https://waczjoan.github.io/MiraGe/)

#### <summary>GaussianBlock: Building Part-Aware Compositional and Editable 3D Scene by Primitives and Gaussians
>*semantic coherent part-aware superquadrics, a hybrid representation that integrates superquadric primitives and Gaussians, where superquadric serve as coarse but disentangled building blocks, while Gaussians act as “skin” to refine the structure and ensure high fidelity, 3D Gaussians at the triangles of each reconstructed superquadric*

Authors: Shuyi Jiang, Qihao Zhao, Hossein Rahmani, De Wen Soh, Jun Liu, Na Zhao
<details span>
<summary><b>Abstract</b></summary>
Recently, with the development of Neural Radiance Fields and Gaussian Splatting, 3D reconstruction techniques have achieved remarkably high fidelity. However, the latent representations learnt by these methods are highly entangled and lack interpretability. In this paper, we propose a novel part-aware compositional reconstruction method, called GaussianBlock, that enables semantically coherent and disentangled representations, allowing for precise and physical editing akin to building blocks, while simultaneously maintaining high fidelity. Our GaussianBlock introduces a hybrid representation that leverages the advantages of both primitives, known for their flexible actionability and editability, and 3D Gaussians, which excel in reconstruction quality. Specifically, we achieve semantically coherent primitives through a novel attention-guided centering loss derived from 2D semantic priors, complemented by a dynamic splitting and fusion strategy. Furthermore, we utilize 3D Gaussians that hybridize with primitives to refine structural details and enhance fidelity. Additionally, a binding inheritance strategy is employed to strengthen and maintain the connection between the two. Our reconstructed scenes are evidenced to be disentangled, compositional, and compact across diverse benchmarks, enabling seamless, direct and precise editing while maintaining high quality.
 
![image](https://github.com/user-attachments/assets/230b968c-76a8-40a7-ac45-16664bdd06f7)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.01535) | [⌨️ Code] | [🌐 Project Page]



<br>
<br>

## SLAM


#### <summary>RTG-SLAM: Real-time 3D Reconstruction at Scale using Gaussian Splatting
Authors: Zhexi Peng, Tianjia Shao, Yong Liu, Jingke Zhou, Yin Yang, Jingdong Wang, Kun Zhou
<details span>
<summary><b>Abstract</b></summary>
We present Real-time Gaussian SLAM (RTG-SLAM), a real-time 3D reconstruction system with an RGBD camera for large-scale environments using Gaussian splatting. The system features a compact Gaussian representation and a highly efficient on-the-fly Gaussian optimization scheme. We force each Gaussian to be either opaque or nearly transparent, with the opaque ones fitting the surface and dominant colors, and transparent ones fitting residual colors. By rendering depth in a different way from color rendering, we let a single opaque Gaussian well fit a local surface region without the need of multiple overlapping Gaussians, hence largely reducing the memory and computation cost. For on-the-fly Gaussian optimization, we explicitly add Gaussians for three types of pixels per frame: newly observed, with large color errors, and with large depth errors. We also categorize all Gaussians into stable and unstable ones, where the stable Gaussians are expected to well fit previously observed RGBD images and otherwise unstable. We only optimize the unstable Gaussians and only render the pixels occupied by unstable Gaussians. In this way, both the number of Gaussians to be optimized and pixels to be rendered are largely reduced, and the optimization can be done in real time. We show real-time reconstructions of a variety of large scenes. Compared with the state-of-the-art NeRF-based RGBD SLAM, our system achieves comparable high-quality reconstruction but with around twice the speed and half the memory cost, and shows superior performance in the realism of novel view synthesis and camera tracking accuracy.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ae306778-dc5a-40e2-99e6-fe8d8b827d42)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.19706) | [⌨️ Code](https://github.com/MisEty/RTG-SLAM?tab=readme-ov-file) | [🌐 Project Page]


#### <summary>Monocular Gaussian SLAM with Language Extended Loop Closure
Authors: Tian Lan, Qinwei Lin, Haoqian Wang
<details span>
<summary><b>Abstract</b></summary>
Recently,3DGaussianSplattinghasshowngreatpotentialin visual Simultaneous Localization And Mapping (SLAM). Existing methods have achieved encouraging results on RGB-D SLAM, but studies of the monocular case are still scarce. Moreover, they also fail to correct drift errors due to the lack of loop closure and global optimization. In this paper, we present MG-SLAM, a monocular Gaussian SLAM with a language-extended loop closure module capable of performing drift-corrected tracking and high-fidelity reconstruction while achieving a high-level understanding of the environment. Our key idea is to represent the global map as 3D Gaussian and use it to guide the estimation of the scene geometry, thus mitigating the efforts of missing depth information. Further, an additional language-extended loop closure module which is based on CLIP feature is designed to continually perform global optimization to correct drift errors accumulated as the system runs. Our system shows promising results on multiple challenging datasets in both tracking and mapping and even surpasses some existing RGB-D methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ec122248-f518-461a-b38d-63b3ec8162a6)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.13748) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Splat-SLAM: Globally Optimized RGB-only SLAM with 3D Gaussians
Authors: Xiangyu Sun, Joo Chan Lee, Daniel Rho, Jong Hwan Ko, Usman Ali, Eunbyung Park
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting has emerged as a powerful representation of geometry and appearance for RGB-only dense Simultaneous Localization and Mapping (SLAM), as it provides a compact dense map representation while enabling efficient and high-quality map rendering. However, existing methods show significantly worse reconstruction quality than competing methods using other 3D representations, e.g. neural points clouds, since they either do not employ global map and pose optimization or make use of monocular depth. In response, we propose the first RGB-only SLAM system with a dense 3D Gaussian map representation that utilizes all benefits of globally optimized tracking by adapting dynamically to keyframe pose and depth updates by actively deforming the 3D Gaussian map. Moreover, we find that refining the depth updates in inaccurate areas with a monocular depth estimator further improves the accuracy of the 3D reconstruction. Our experiments on the Replica, TUM-RGBD, and ScanNet datasets indicate the effectiveness of globally optimized 3D Gaussians, as the approach achieves superior or on par performance with existing RGB-only SLAM methods methods in tracking, mapping and rendering accuracy while yielding small map sizes and fast runtimes.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/223b9a44-1b78-48c1-a5a8-112e2695e2cb)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16544) | [⌨️ Code](https://github.com/eriksandstroem/Splat-SLAM) | [🌐 Project Page]


#### <summary>Structure Gaussian SLAM with Manhattan World Hypothesis
Authors: Shuhong Liu, Heng Zhou, Liuzhuozheng Li, Yun Liu, Tianchen Deng, Yiming Zhou, Mingrui Li
<details span>
<summary><b>Abstract</b></summary>
Gaussian SLAM systems have made significant advancements in improving the efficiency and fidelity of real-time reconstructions. However, these systems often encounter incomplete reconstructions in complex indoor environments, characterized by substantial holes due to unobserved geometry caused by obstacles or limited view angles. To address this challenge, we present Manhattan Gaussian SLAM (MG-SLAM), an RGB-D system that leverages the Manhattan World hypothesis to enhance geometric accuracy and completeness. By seamlessly integrating fused line segments derived from structured scenes, MG-SLAM ensures robust tracking in textureless indoor areas. Moreover, The extracted lines and planar surface assumption allow strategic interpolation of new Gaussians in regions of missing geometry, enabling efficient scene completion. Extensive experiments conducted on both synthetic and real-world scenes demonstrate that these advancements enable our method to achieve state-of-the-art performance, marking a substantial improvement in the capabilities of Gaussian SLAM systems.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/703df897-a955-4bac-b95e-dac8e2a3f317)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20031) | [⌨️ Code] | [🌐 Project Page]


#### <summary>OmniRe: Omni Urban Scene Reconstruction
Authors: Ziyu Chen, Jiawei Yang, Jiahui Huang, Riccardo de Lutio, Janick Martinez Esturo, Boris Ivanovic, Or Litany, Zan Gojcic, Sanja Fidler, Marco Pavone, Li Song, Yue Wang
<details span>
<summary><b>Abstract</b></summary>
We introduce OmniRe, a holistic approach for efficiently reconstructing high-fidelity dynamic urban scenes from on-device logs. Recent methods for modeling driving sequences using neural radiance fields or Gaussian Splatting have demonstrated the potential of reconstructing challenging dynamic scenes, but often overlook pedestrians and other non-vehicle dynamic actors, hindering a complete pipeline for dynamic urban scene reconstruction. To that end, we propose a comprehensive 3DGS framework for driving scenes, named OmniRe, that allows for accurate, full-length reconstruction of diverse dynamic objects in a driving log. OmniRe builds dynamic neural scene graphs based on Gaussian representations and constructs multiple local canonical spaces that model various dynamic actors, including vehicles, pedestrians, and cyclists, among many others. This capability is unmatched by existing methods. OmniRe allows us to holistically reconstruct different objects present in the scene, subsequently enabling the simulation of reconstructed scenarios with all actors participating in real-time (~60Hz). Extensive evaluations on the Waymo dataset show that our approach outperforms prior state-of-the-art methods quantitatively and qualitatively by a large margin. We believe our work fills a critical gap in driving reconstruction.
 
![image](https://github.com/user-attachments/assets/32fb5f74-5a15-44e1-b55d-1e0879ad6b1d)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.16760) | [⌨️ Code](https://github.com/ziyc/drivestudio) | [🌐 Project Page](https://ziyc.github.io/omnire/)


#### <summary>OG-Mapping: Octree-based Structured 3D Gaussians for Online Dense Mapping
>*anchor growth method based on Scaffold-GS*

Authors: Meng Wang, Junyi Wang, Changqun Xia, Chen Wang, Yue Qi
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian splatting (3DGS) has recently demonstrated promising advancements in RGB-D online dense mapping. Nevertheless, existing methods excessively rely on per-pixel depth cues to perform map densification, which leads to significant redundancy and increased sensitivity to depth noise. Additionally, explicitly storing 3D Gaussian parameters of room-scale scene poses a significant storage challenge. In this paper, we introduce OG-Mapping, which leverages the robust scene structural representation capability of sparse octrees, combined with structured 3D Gaussian representations, to achieve efficient and robust online dense mapping. Moreover, OG-Mapping employs an anchor-based progressive map refinement strategy to recover the scene structures at multiple levels of detail. Instead of maintaining a small number of active keyframes with a fixed keyframe window as previous approaches do, a dynamic keyframe window is employed to allow OG-Mapping to better tackle false local minima and forgetting issues. Experimental results demonstrate that OG-Mapping delivers more robust and superior realism mapping results than existing Gaussian-based RGB-D online mapping methods with a compact model, and no additional post-processing is required.
 
![image](https://github.com/user-attachments/assets/d7225b17-aab2-4aae-b57b-43cb471e9342)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.17223) | [⌨️ Code] | [🌐 Project Page]


#### <summary>MGSO: Monocular Real-time Photometric SLAM with Efficient 3D Gaussian Splatting


Authors: Yan Song Hu, Nicolas Abboud, Muhammad Qasim Ali, Adam Srebrnjak Yang, Imad Elhajj, Daniel Asmar, Yuhao Chen, John S. Zelek
<details span>
<summary><b>Abstract</b></summary>
Real-time SLAM with dense 3D mapping is computationally challenging, especially on resource-limited devices. The recent development of 3D Gaussian Splatting (3DGS) offers a promising approach for real-time dense 3D reconstruction. However, existing 3DGS-based SLAM systems struggle to balance hardware simplicity, speed, and map quality. Most systems excel in one or two of the aforementioned aspects but rarely achieve all. A key issue is the difficulty of initializing 3D Gaussians while concurrently conducting SLAM. To address these challenges, we present Monocular GSO (MGSO), a novel real-time SLAM system that integrates photometric SLAM with 3DGS. Photometric SLAM provides dense structured point clouds for 3DGS initialization, accelerating optimization and producing more efficient maps with fewer Gaussians. As a result, experiments show that our system generates reconstructions with a balance of quality, memory efficiency, and speed that outperforms the state-of-the-art. Furthermore, our system achieves all results using RGB inputs. We evaluate the Replica, TUM-RGBD, and EuRoC datasets against current live dense reconstruction systems. Not only do we surpass contemporary systems, but experiments also show that we maintain our performance on laptop hardware, making it a practical solution for robotics, A/R, and other real-time applications.
 
![image](https://github.com/user-attachments/assets/796e8a55-8adc-429a-98ee-ec096558705c)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.13055) | [⌨️ Code] | [🌐 Project Page]


#### <summary>CaRtGS: Computational Alignment for Real-Time Gaussian Splatting SLAM
>*Fast Splat-wise Backpropagation*

Authors: Dapeng Feng, Zhiqiang Chen, Yizhen Yin, Shipeng Zhong, Yuhua Qi, Hongbo Chen
<details span>
<summary><b>Abstract</b></summary>
Simultaneous Localization and Mapping (SLAM) is pivotal in robotics, with photorealistic scene reconstruction emerging as a key challenge. To address this, we introduce Computational Alignment for Real-Time Gaussian Splatting SLAM (CaRtGS), a novel method enhancing the efficiency and quality of photorealistic scene reconstruction in real-time environments. Leveraging 3D Gaussian Splatting (3DGS), CaRtGS achieves superior rendering quality and processing speed, which is crucial for scene photorealistic reconstruction. Our approach tackles computational misalignment in Gaussian Splatting SLAM (GS-SLAM) through an adaptive strategy that optimizes training, addresses long-tail optimization, and refines densification. Experiments on Replica and TUM-RGBD datasets demonstrate CaRtGS's effectiveness in achieving high-fidelity rendering with fewer Gaussian primitives. This work propels SLAM towards real-time, photorealistic dense rendering, significantly advancing photorealistic scene representation. 
 
![image](https://github.com/user-attachments/assets/d3a14956-85a0-4e15-8677-32321009b7fe)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.00486) | [⌨️ Code](https://github.com/dapengfeng/cartgs) | [🌐 Project Page](https://dapengfeng.github.io/cartgs)


<br>
<br>


## Noisy Poses


#### <summary>Robust Gaussian Splatting
Authors: François Darmon, Lorenzo Porzi, Samuel Rota-Bulò, Peter Kontschieder
<details span>
<summary><b>Abstract</b></summary>
In this paper, we address common error sources for 3D Gaussian Splatting (3DGS) including blur, imperfect camera poses, and color inconsistencies, with the goal of improving its robustness for practical applications like reconstructions from handheld phone captures. Our main contribution involves modeling motion blur as a Gaussian distribution over camera poses, allowing us to address both camera pose refinement and motion blur correction in a unified way. Additionally, we propose mechanisms for defocus blur compensation and for addressing color in-consistencies caused by ambient light, shadows, or due to camera-related factors like varying white balancing settings. Our proposed solutions integrate in a seamless way with the 3DGS formulation while maintaining its benefits in terms of training efficiency and rendering speed. We experimentally validate our contributions on relevant benchmark datasets including Scannet++ and Deblur-NeRF, obtaining state-of-the-art results and thus consistent improvements over relevant baselines.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/73f17da8-961d-47b3-a641-2e597816861e)

</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.04211) | [⌨️ Code] | [🌐 Project Page]





#### <summary>SPARF: Neural Radiance Fields from Sparse and Noisy Poses
Authors: Tao Lu, Mulin Yu, Linning Xu, Yuanbo Xiangli, Limin Wang, Dahua Lin, Bo Dai
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Field (NeRF) has recently emerged as a powerful representation to synthesize photorealistic novel views. While showing impressive performance, it relies on the availability of dense input views with highly accurate camera poses, thus limiting its application in real-world scenarios. In this work, we introduce Sparse Pose Adjusting Radiance Field (SPARF), to address the challenge of novel-view synthesis given only few wide-baseline input images (as low as 3) with noisy camera poses. Our approach exploits multi-view geometry constraints in order to jointly learn the NeRF and refine the camera poses. By relying on pixel matches extracted between the input views, our multi-view correspondence objective enforces the optimized scene and camera poses to converge to a global and geometrically accurate solution. Our depth consistency loss further encourages the reconstructed scene to be consistent from any viewpoint. Our approach sets a new state of the art in the sparse-view regime on multiple challenging datasets.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/256f55eb-747d-49d2-ae35-baa4c993a30f)

</details>

[📃 arXiv:2211](https://arxiv.org/pdf/2211.11738) | [⌨️ Code](https://github.com/google-research/sparf) | [🌐 Project Page](https://prunetruong.com/sparf.github.io/)

#### <summary>TrackNeRF: Bundle Adjusting NeRF from Sparse and Noisy Views via Feature Tracks
Authors: Jinjie Mai, Wenxuan Zhu, Sara Rojas, Jesus Zarzar, Abdullah Hamdi, Guocheng Qian, Bing Li, Silvio Giancola, Bernard Ghanem
<details span>
<summary><b>Abstract</b></summary>
Neural radiance fields (NeRFs) generally require many images with accurate poses for accurate novel view synthesis, which does not reflect realistic setups where views can be sparse and poses can be noisy. Previous solutions for learning NeRFs with sparse views and noisy poses only consider local geometry consistency with pairs of views. Closely following \textit{bundle adjustment} in Structure-from-Motion (SfM), we introduce TrackNeRF for more globally consistent geometry reconstruction and more accurate pose optimization. TrackNeRF introduces \textit{feature tracks}, \ie connected pixel trajectories across \textit{all} visible views that correspond to the \textit{same} 3D points. By enforcing reprojection consistency among feature tracks, TrackNeRF encourages holistic 3D consistency explicitly. Through extensive experiments, TrackNeRF sets a new benchmark in noisy and sparse view reconstruction. In particular, TrackNeRF shows significant improvements over the state-of-the-art BARF and SPARF by ∼8 and ∼1 in terms of PSNR on DTU under various sparse and noisy view setups.

![image](https://github.com/user-attachments/assets/29204efb-0e80-40d2-93dc-23ead3214a61)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.10739) | [⌨️ Code](https://github.com/Wayne-Mai/traf_public) | [🌐 Project Page](https://tracknerf.github.io/)

<br>
<br>


## Generalizable


#### <summary>GPS-Gaussian: Generalizable Pixel-wise 3D Gaussian Splatting for Real-time Human Novel View Synthesis

Authors: Shunyuan Zheng, Boyao Zhou, Ruizhi Shao, Boning Liu, Shengping Zhang, Liqiang Nie, Yebin Liu
<details span>
<summary><b>Abstract</b></summary>
We present a new approach, termed GPS-Gaussian, for synthesizing novel views of a character in a real-time manner. The proposed method enables 2K-resolution rendering under a sparse-view camera setting. Unlike the original Gaussian Splatting or neural implicit rendering methods that necessitate per-subject optimizations, we introduce Gaussian parameter maps defined on the source views and regress directly Gaussian Splatting properties for instant novel view synthesis without any fine-tuning or optimization. To this end, we train our Gaussian parameter regression module on a large amount of human scan data, jointly with a depth estimation module to lift 2D parameter maps to 3D space. The proposed framework is fully differentiable and experiments on several datasets demonstrate that our method outperforms state-of-the-art methods while achieving an exceeding rendering speed.

![image](https://github.com/user-attachments/assets/24ca6e12-ea69-404f-a137-5fa0bd79fd4d)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.02155) | [⌨️ Code](https://github.com/ShunyuanZheng/GPS-Gaussian) | [🌐 Project Page](https://shunyuanzheng.github.io/GPS-Gaussian)



#### <summary>Triplane Meets Gaussian Splatting: Fast and Generalizable Single-View 3D Reconstruction with Transformers

Authors: Zi-Xin Zou, Zhipeng Yu, Yuan-Chen Guo, Yangguang Li, Ding Liang, Yan-Pei Cao, Song-Hai Zhang
<details span>
<summary><b>Abstract</b></summary>
Recent advancements in 3D reconstruction from single images have been driven by the evolution of generative models. Prominent among these are methods based on Score Distillation Sampling (SDS) and the adaptation of diffusion models in the 3D domain. Despite their progress, these techniques often face limitations due to slow optimization or rendering processes, leading to extensive training and optimization times. In this paper, we introduce a novel approach for single-view reconstruction that efficiently generates a 3D model from a single image via feed-forward inference. Our method utilizes two transformer-based networks, namely a point decoder and a triplane decoder, to reconstruct 3D objects using a hybrid Triplane-Gaussian intermediate representation. This hybrid representation strikes a balance, achieving a faster rendering speed compared to implicit representations while simultaneously delivering superior rendering quality than explicit representations. The point decoder is designed for generating point clouds from single images, offering an explicit representation which is then utilized by the triplane decoder to query Gaussian features for each point. This design choice addresses the challenges associated with directly regressing explicit 3D Gaussian attributes characterized by their non-structural nature. Subsequently, the 3D Gaussians are decoded by an MLP to enable rapid rendering through splatting. Both decoders are built upon a scalable, transformer-based architecture and have been efficiently trained on large-scale 3D datasets. The evaluations conducted on both synthetic datasets and real-world images demonstrate that our method not only achieves higher quality but also ensures a faster runtime in comparison to previous state-of-the-art techniques.

![image](https://github.com/user-attachments/assets/ebc265ff-3c2a-49f5-8d56-d8279876960b)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.09147) | [⌨️ Code](https://github.com/VAST-AI-Research/TriplaneGaussian) | [🌐 Project Page](https://zouzx.github.io/TriplaneGaussian/)



#### <summary>pixelSplat: 3D Gaussian Splats from Image Pairs for Scalable Generalizable 3D Reconstruction

Authors: David Charatan, Sizhe Li, Andrea Tagliasacchi, Vincent Sitzmann
<details span>
<summary><b>Abstract</b></summary>
We introduce pixelSplat, a feed-forward model that learns to reconstruct 3D radiance fields parameterized by 3D Gaussian primitives from pairs of images. Our model features real-time and memory-efficient rendering for scalable training as well as fast 3D reconstruction at inference time. To overcome local minima inherent to sparse and locally supported representations, we predict a dense probability distribution over 3D and sample Gaussian means from that probability distribution. We make this sampling operation differentiable via a reparameterization trick, allowing us to back-propagate gradients through the Gaussian splatting representation. We benchmark our method on wide-baseline novel view synthesis on the real-world RealEstate10k and ACID datasets, where we outperform state-of-the-art light field transformers and accelerate rendering by 2.5 orders of magnitude while reconstructing an interpretable and editable 3D radiance field.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d46225eb-97c6-44ab-a96b-10ca2754fa56)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.12337) | [⌨️ Code](https://github.com/dcharatan/pixelsplat) | [🌐 Project Page](https://davidcharatan.com/pixelsplat/)

#### <summary>GGRt: Towards Pose-free Generalizable 3D Gaussian Splatting in Real-time
Authors: Hao Li, Yuanyuan Gao, Chenming Wu, Dingwen Zhang, Yalun Dai, Chen Zhao, Haocheng Feng, Errui Ding, Jingdong Wang, Junwei Han
<details span>
<summary><b>Abstract</b></summary>
This paper presents GGRt, a novel approach to generalizable novel view synthesis that alleviates the need for real camera poses, complexity in processing high-resolution images, and lengthy optimization processes, thus facilitating stronger applicability of 3D Gaussian Splatting (3D-GS) in real-world scenarios. Specifically, we design a novel joint learning framework that consists of an Iterative Pose Optimization Network (IPO-Net) and a Generalizable 3D-Gaussians (G-3DG) model. With the joint learning mechanism, the proposed framework can inherently estimate robust relative pose information from the image observations and thus primarily alleviate the requirement of real camera poses. Moreover, we implement a deferred back-propagation mechanism that enables high-resolution training and inference, overcoming the resolution constraints of previous methods. To enhance the speed and efficiency, we further introduce a progressive Gaussian cache module that dynamically adjusts during training and inference. As the first pose-free generalizable 3D-GS framework, GGRt achieves inference at ≥ 5 FPS and real-time rendering at ≥ 100 FPS. Through extensive experimentation, we demonstrate that our method outperforms existing NeRF-based pose-free techniques in terms of inference speed and effectiveness. It can also approach the real pose-based 3D-GS methods. Our contributions provide a significant leap forward for the integration of computer vision and computer graphics into practical applications, offering state-of-the-art results on LLFF, KITTI, and Waymo Open datasets and enabling real-time rendering for immersive experiences.

![image](https://github.com/user-attachments/assets/eba387ee-6661-4324-9eae-ff25a09aa072)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.10147) | [⌨️ Code] | [🌐 Project Page](https://3d-aigc.github.io/GGRt/)


#### <summary>MVSplat: Efficient 3D Gaussian Splatting from Sparse Multi-View Images
Authors: Yuedong Chen, Haofei Xu, Chuanxia Zheng, Bohan Zhuang, Marc Pollefeys, Andreas Geiger, Tat-Jen Cham, Jianfei Cai
<details span>
<summary><b>Abstract</b></summary>
We propose MVSplat, an efficient feed-forward 3D Gaussian Splatting model learned from sparse multi-view images. To accurately localize the Gaussian centers, we propose to build a cost volume representation via plane sweeping in the 3D space, where the cross-view feature similarities stored in the cost volume can provide valuable geometry cues to the estimation of depth. We learn the Gaussian primitives' opacities, covariances, and spherical harmonics coefficients jointly with the Gaussian centers while only relying on photometric supervision. We demonstrate the importance of the cost volume representation in learning feed-forward Gaussian Splatting models via extensive experimental evaluations. On the large-scale RealEstate10K and ACID benchmarks, our model achieves state-of-the-art performance with the fastest feed-forward inference speed (22 fps). Compared to the latest state-of-the-art method pixelSplat, our model uses 10× fewer parameters and infers more than 2× faster while providing higher appearance and geometry quality as well as better cross-dataset generalization.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/5f4ec424-1dcd-4747-a2a2-bc0395f412d4)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.14627) | [⌨️ Code](https://github.com/donydchen/mvsplat?tab=readme-ov-file) | [🌐 Project Page](https://donydchen.github.io/mvsplat/)


#### <summary>latentSplat: Autoencoding Variational Gaussians for Fast Generalizable 3D Reconstruction
Authors: Christopher Wewer, Kevin Raj, Eddy Ilg, Bernt Schiele, Jan Eric Lenssen
<details span>
<summary><b>Abstract</b></summary>
We present latentSplat, a method to predict semantic Gaussians in a 3D latent space that can be splatted and decoded by a light-weight generative 2D architecture. Existing methods for generalizable 3D reconstruction either do not enable fast inference of high resolution novel views due to slow volume rendering, or are limited to interpolation of close input views, even in simpler settings with a single central object, where 360-degree generalization is possible. In this work, we combine a regression-based approach with a generative model, moving towards both of these capabilities within the same method, trained purely on readily available real video data. The core of our method are variational 3D Gaussians, a representation that efficiently encodes varying uncertainty within a latent space consisting of 3D feature Gaussians. From these Gaussians, specific instances can be sampled and rendered via efficient Gaussian splatting and a fast, generative decoder network. We show that latentSplat outperforms previous works in reconstruction quality and generalization, while being fast and scalable to high-resolution data.

![image](https://github.com/user-attachments/assets/ab1c6edb-96f3-4fd5-b9d5-07f2033c9beb)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.16292) | [⌨️ Code](https://github.com/Chrixtar/latentsplat) | [🌐 Project Page](https://geometric-rl.mpi-inf.mpg.de/latentsplat/)



#### <summary>Fast Generalizable Gaussian Splatting Reconstruction from Multi-View Stereo
Authors: Tianqi Liu, Guangcong Wang, Shoukang Hu, Liao Shen, Xinyi Ye, Yuhang Zang, Zhiguo Cao, Wei Li, Ziwei Liu
<details span>
<summary><b>Abstract</b></summary>
We present MVSGaussian, a new generalizable 3D Gaussian representation approach derived from Multi-View Stereo (MVS) that can efficiently reconstruct unseen scenes. Specifically, 1) we leverage MVS to encode geometry-aware Gaussian representations and decode them into Gaussian parameters. 2) To further enhance performance, we propose a hybrid Gaussian rendering that integrates an efficient volume rendering design for novel view synthesis. 3) To support fast fine-tuning for specific scenes, we introduce a multi-view geometric consistent aggregation strategy to effectively aggregate the point clouds generated by the generalizable model, serving as the initialization for per-scene optimization. Compared with previous generalizable NeRF-based methods, which typically require minutes of fine-tuning and seconds of rendering per image, MVSGaussian achieves real-time rendering with better synthesis quality for each scene. Compared with the vanilla 3D-GS, MVSGaussian achieves better view synthesis with less training computational cost. Extensive experiments on DTU, Real Forward-facing, NeRF Synthetic, and Tanks and Temples datasets validate that MVSGaussian attains state-of-the-art performance with convincing generalizability, real-time rendering speed, and fast per-scene optimization.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ac046c9d-a95f-4f52-9bf4-559215733ce8)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12218) | [⌨️ Code](https://github.com/TQTQliu/MVSGaussian) | [🌐 Project Page](https://mvsgaussian.github.io/)


#### <summary>FreeSplat: Generalizable 3D Gaussian Splatting Towards Free-View Synthesis of Indoor Scenes
Authors: Yunsong Wang, Tianxin Huang, Hanlin Chen, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
Empowering 3D Gaussian Splatting with generalization ability is appealing. However, existing generalizable 3D Gaussian Splatting methods are largely confined to narrow-range interpolation between stereo images due to their heavy backbones, thus lacking the ability to accurately localize 3D Gaussian and support free-view synthesis across wide view range. In this paper, we present a novel framework FreeSplat that is capable of reconstructing geometrically consistent 3D scenes from long sequence input towards free-view synthesis.Specifically, we firstly introduce Low-cost Cross-View Aggregation achieved by constructing adaptive cost volumes among nearby views and aggregating features using a multi-scale structure. Subsequently, we present the Pixel-wise Triplet Fusion to eliminate redundancy of 3D Gaussians in overlapping view regions and to aggregate features observed across multiple views. Additionally, we propose a simple but effective free-view training strategy that ensures robust view synthesis across broader view range regardless of the number of views. Our empirical results demonstrate state-of-the-art novel view synthesis peformances in both novel view rendered color maps quality and depth maps accuracy across different numbers of input views. We also show that FreeSplat performs inference more efficiently and can effectively reduce redundant Gaussians, offering the possibility of feed-forward large scene reconstruction without depth priors.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9d6fcc96-b8ca-4743-9c2f-638d8533a545)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17958) | [⌨️ Code](https://github.com/wangys16/FreeSplat) | [🌐 Project Page]


#### <summary>LaRa: Efficient Large-Baseline Radiance Fields
Authors: Anpei Chen, Haofei Xu, Stefano Esposito, Siyu Tang, Andreas Geiger
<details span>
<summary><b>Abstract</b></summary>
Radiance field methods have achieved photorealistic novel view synthesis and geometry reconstruction. But they are mostly applied in per-scene optimization or small-baseline settings. While several recent works investigate feed-forward reconstruction with large baselines by utilizing transformers, they all operate with a standard global attention mechanism and hence ignore the local nature of 3D reconstruction. We propose a method that unifies local and global reasoning in transformer layers, resulting in improved quality and faster convergence. Our model represents scenes as Gaussian Volumes and combines this with an image encoder and Group Attention Layers for efficient feed-forward reconstruction. Experimental results demonstrate that our model, trained for two days on four GPUs, demonstrates high fidelity in reconstructing 360&deg radiance fields, and robustness to zero-shot and out-of-domain testing.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/844cccd5-3bd5-40c8-bfbb-1fce46817848)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2407.04699) | [⌨️ Code](https://github.com/autonomousvision/LaRa) | [🌐 Project Page](https://apchenstu.github.io/LaRa/)


#### <summary>Splatt3R: Zero-shot Gaussian Splatting from Uncalibarated Image Pairs
Authors: Brandon Smart, Chuanxia Zheng, Iro Laina, Victor Adrian Prisacariu
<details span>
<summary><b>Abstract</b></summary>
In this paper, we introduce Splatt3R, a pose-free, feed-forward method for in-the-wild 3D reconstruction and novel view synthesis from stereo pairs. Given uncalibrated natural images, Splatt3R can predict 3D Gaussian Splats without requiring any camera parameters or depth information. For generalizability, we start from a 'foundation' 3D geometry reconstruction method, MASt3R, and extend it to be a full 3D structure and appearance reconstructor. Specifically, unlike the original MASt3R which reconstructs only 3D point clouds, we predict the additional Gaussian attributes required to construct a Gaussian primitive for each point. Hence, unlike other novel view synthesis methods, Splatt3R is first trained by optimizing the 3D point cloud's geometry loss, and then a novel view synthesis objective. By doing this, we avoid the local minima present in training 3D Gaussian Splats from stereo views. We also propose a novel loss masking strategy that we empirically find is critical for strong performance on extrapolated viewpoints. We train Splatt3R on the ScanNet++ dataset and demonstrate excellent generalisation to uncalibrated, in-the-wild images. Splatt3R can reconstruct scenes at 4FPS at 512 x 512 resolution, and the resultant splats can be rendered in real-time.

![image](https://github.com/user-attachments/assets/24c1c2fb-5c38-468a-8e8d-ba4d9514cd40)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.13912) | [⌨️ Code] | [🌐 Project Page]

#### <summary>TranSplat: Generalizable 3D Gaussian Splatting from Sparse Multi-View Images with Transformers
Authors: Chuanrui Zhang, Yingshuang Zou, Zhuoling Li, Minmin Yi, Haoqian Wang
<details span>
<summary><b>Abstract</b></summary>
Compared with previous 3D reconstruction methods like Nerf, recent Generalizable 3D Gaussian Splatting (G-3DGS) methods demonstrate impressive efficiency even in the sparse-view setting. However, the promising reconstruction performance of existing G-3DGS methods relies heavily on accurate multi-view feature matching, which is quite challenging. Especially for the scenes that have many non-overlapping areas between various views and contain numerous similar regions, the matching performance of existing methods is poor and the reconstruction precision is limited. To address this problem, we develop a strategy that utilizes a predicted depth confidence map to guide accurate local feature matching. In addition, we propose to utilize the knowledge of existing monocular depth estimation models as prior to boost the depth estimation precision in non-overlapping areas between views. Combining the proposed strategies, we present a novel G-3DGS method named TranSplat, which obtains the best performance on both the RealEstate10K and ACID benchmarks while maintaining competitive speed and presenting strong cross-dataset generalization ability.

![image](https://github.com/user-attachments/assets/70cd0f0b-65b2-4455-82eb-1de3d3a1a5e0)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.13770) | [⌨️ Code] | [🌐 Project Page](https://xingyoujun.github.io/transplat/)


<br>
<br>

## High Frequency Details

#### <summary>FreGS: 3D Gaussian Splatting with Progressive Frequency Regularization</summary>
Authors: Jiahui Zhang, Fangneng Zhan, Muyu Xu, Shijian Lu, Eric Xing
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian splatting has achieved very impressive performance in real-time novel view synthesis. However, it often suffers from over-reconstruction during Gaussian densification where high-variance image regions are covered by a few large Gaussians only, leading to blur and artifacts in the rendered images. We design a progressive frequency regularization (FreGS) technique to tackle the over-reconstruction issue within the frequency space. Specifically, FreGS performs coarse-to-fine Gaussian densification by exploiting low-to-high frequency components that can be easily extracted with low-pass and high-pass filters in the Fourier space. By minimizing the discrepancy between the frequency spectrum of the rendered image and the corresponding ground truth, it achieves high-quality Gaussian densification and alleviates the over-reconstruction of Gaussian splatting effectively. Experiments over multiple widely adopted benchmarks (e.g., Mip-NeRF360, Tanks-and-Temples and Deep Blending) show that FreGS achieves superior novel view synthesis and outperforms the state-of-the-art consistently.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/1789b70e-4fb7-4be6-8c53-0d164b1c977b)

 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.06908.pdf) | [⌨️ Code](https://rogeraigc.github.io/FreGS-Page/) | [🌐 Project Page](https://rogeraigc.github.io/FreGS-Page/)

#### <summary>Pixel-GS: Density Control with Pixel-aware Gradient for 3D Gaussian Splatting
Authors: Zheng Zhang, Wenbo Hu, Yixing Lao, Tong He, Hengshuang Zhao
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has demonstrated impressive novel view synthesis results while advancing real-time rendering performance. However, it relies heavily on the quality of the initial point cloud, resulting in blurring and needle-like artifacts in areas with insufficient initializing points. This is mainly attributed to the point cloud growth condition in 3DGS that only considers the average gradient magnitude of points from observable views, thereby failing to grow for large Gaussians that are observable for many viewpoints while many of them are only covered in the boundaries. To this end, we propose a novel method, named Pixel-GS, to take into account the number of pixels covered by the Gaussian in each view during the computation of the growth condition. We regard the covered pixel numbers as the weights to dynamically average the gradients from different views, such that the growth of large Gaussians can be prompted. As a result, points within the areas with insufficient initializing points can be grown more effectively, leading to a more accurate and detailed reconstruction. In addition, we propose a simple yet effective strategy to scale the gradient field according to the distance to the camera, to suppress the growth of floaters near the camera. Extensive experiments both qualitatively and quantitatively demonstrate that our method achieves state-of-the-art rendering quality while maintaining real-time rendering speed, on the challenging Mip-NeRF 360 and Tanks & Temples datasets.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/22bafec5-3805-41cf-91df-f4d0703efd96)

 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.15530) | [⌨️ Code](https://github.com/zhengzhang01/Pixel-GS) | [🌐 Project Page](https://pixelgs.github.io/)


#### <summary>Revising Densification in Gaussian Splatting
Authors: Samuel Rota Bulò, Lorenzo Porzi, Peter Kontschieder
<details span>
<summary><b>Abstract</b></summary>
In this paper, we address the limitations of Adaptive Density Control (ADC) in 3D Gaussian Splatting (3DGS), a scene representation method achieving high-quality, photorealistic results for novel view synthesis. ADC has been introduced for automatic 3D point primitive management, controlling densification and pruning, however, with certain limitations in the densification logic. Our main contribution is a more principled, pixel-error driven formulation for density control in 3DGS, leveraging an auxiliary, per-pixel error function as the criterion for densification. We further introduce a mechanism to control the total number of primitives generated per scene and correct a bias in the current opacity handling strategy of ADC during cloning operations. Our approach leads to consistent quality improvements across a variety of benchmark scenes, without sacrificing the method's efficiency.


![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/611d9108-0909-42c3-a946-4045fd8dd072)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.06109) | [⌨️ Code] | [🌐 Project Page]




#### <summary>AbsGS: Recovering Fine Details for 3D Gaussian Splatting
Authors: Zongxin Ye, Wenyu Li, Sidun Liu, Peng Qiao, Yong Dou
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3D-GS) technique couples 3D Gaussian primitives with differentiable rasterization to achieve high-quality novel view synthesis results while providing advanced real-time rendering performance. However, due to the flaw of its adaptive density control strategy in 3D-GS, it frequently suffers from over-reconstruction issue in intricate scenes containing high-frequency details, leading to blurry rendered images. The underlying reason for the flaw has still been under-explored. In this work, we present a comprehensive analysis of the cause of aforementioned artifacts, namely gradient collision, which prevents large Gaussians in over-reconstructed regions from splitting. To address this issue, we propose the novel homodirectional view-space positional gradient as the criterion for densification. Our strategy efficiently identifies large Gaussians in over-reconstructed regions, and recovers fine details by splitting. We evaluate our proposed method on various challenging datasets. The experimental results indicate that our approach achieves the best rendering quality with reduced or similar memory consumption. Our method is easy to implement and can be incorporated into a wide variety of most recent Gaussian Splatting-based methods. We will open source our codes upon formal publication.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/2195a2a1-1557-4d79-9ea8-77bc55e953db)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.10484.pdf) | [⌨️ Code](https://ty424.github.io/AbsGS.github.io) | [🌐 Project Page]

#### <summary>Spectrally Pruned Gaussian Fields with Neural Compensation
Authors: Runyi Yang, Zhenxin Zhu, Zhou Jiang, Baijun Ye, Xiaoxue Chen, Yifei Zhang, Yuantao Chen, Jian Zhao, Hao Zhao
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting, as a novel 3D representation, has garnered attention for its fast rendering speed and high rendering quality. However, this comes with high memory consumption, e.g., a well-trained Gaussian field may utilize three million Gaussian primitives and over 700 MB of memory. We credit this high memory footprint to the lack of consideration for the relationship between primitives. In this paper, we propose a memory-efficient Gaussian field named SUNDAE with spectral pruning and neural compensation. On one hand, we construct a graph on the set of Gaussian primitives to model their relationship and design a spectral down-sampling module to prune out primitives while preserving desired signals. On the other hand, to compensate for the quality loss of pruning Gaussians, we exploit a lightweight neural network head to mix splatted features, which effectively compensates for quality losses while capturing the relationship between primitives in its weights. We demonstrate the performance of SUNDAE with extensive results. For example, SUNDAE can achieve 26.80 PSNR at 145 FPS using 104 MB memory while the vanilla Gaussian splatting algorithm achieves 25.60 PSNR at 160 FPS using 523 MB memory, on the Mip-NeRF360 dataset.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a4d93065-0ce8-4986-8de0-3aea67d3b513)
 
</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.00676) | [⌨️ Code](https://github.com/RunyiYang/SUNDAE) | [🌐 Project Page](https://runyiyang.github.io/projects/SUNDAE/)





<br>
<br>

## Anti-Aliasing

#### <summary>Mip-Splatting: Alias-free 3D Gaussian Splatting
Authors: Zehao Yu, Anpei Chen, Binbin Huang, Torsten Sattler, Andreas Geiger
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting has demonstrated impressive novel view synthesis results, reaching high fidelity and efficiency. However, strong artifacts can be observed when changing the sampling rate, \eg, by changing focal length or camera distance. We find that the source for this phenomenon can be attributed to the lack of 3D frequency constraints and the usage of a 2D dilation filter. To address this problem, we introduce a 3D smoothing filter which constrains the size of the 3D Gaussian primitives based on the maximal sampling frequency induced by the input views, eliminating high-frequency artifacts when zooming in. Moreover, replacing 2D dilation with a 2D Mip filter, which simulates a 2D box filter, effectively mitigates aliasing and dilation issues. Our evaluation, including scenarios such a training on single-scale images and testing on multiple scales, validates the effectiveness of our approach.

![image](https://github.com/user-attachments/assets/be487436-a2df-4e4d-b389-523661371940)

</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.16493) | [⌨️ Code](https://github.com/autonomousvision/mip-splatting) | [🌐 Project Page](https://niujinshuchong.github.io/mip-splatting)

#### <summary>Multi-Scale 3D Gaussian Splatting for Anti-Aliased Rendering
Authors: Zhiwen Yan, Weng Fei Low, Yu Chen, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
3D Gaussians have recently emerged as a highly efficient representation for 3D reconstruction and rendering. Despite its high rendering quality and speed at high resolutions, they both deteriorate drastically when rendered at lower resolutions or from far away camera position. During low resolution or far away rendering, the pixel size of the image can fall below the Nyquist frequency compared to the screen size of each splatted 3D Gaussian and leads to aliasing effect. The rendering is also drastically slowed down by the sequential alpha blending of more splatted Gaussians per pixel. To address these issues, we propose a multi-scale 3D Gaussian splatting algorithm, which maintains Gaussians at different scales to represent the same scene. Higher-resolution images are rendered with more small Gaussians, and lower-resolution images are rendered with fewer larger Gaussians. With similar training time, our algorithm can achieve 13\%-66\% PSNR and 160\%-2400\% rendering speed improvement at 4×-128× scale rendering on Mip-NeRF360 dataset compared to the single scale 3D Gaussian splatting.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9c38b2b3-d229-4c27-9f85-22a0390b2a7b)


</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.17089) | [⌨️ Code](https://github.com/JokerYan/MS-GS/tree/main) | [🌐 Project Page](https://jokeryan.github.io/projects/ms-gs/)

#### <summary>Analytic-Splatting: Anti-Aliased 3D Gaussian Splatting via Analytic Integration
Authors: Zhihao Liang, Qi Zhang, Wenbo Hu, Ying Feng, Lei Zhu, Kui Jia
<details span>
<summary><b>Abstract</b></summary>
The 3D Gaussian Splatting (3DGS) gained its popularity recently by combining the advantages of both primitive-based and volumetric 3D representations, resulting in improved quality and efficiency for 3D scene rendering. However, 3DGS is not alias-free, and its rendering at varying resolutions could produce severe blurring or jaggies. This is because 3DGS treats each pixel as an isolated, single point rather than as an area, causing insensitivity to changes in the footprints of pixels. Consequently, this discrete sampling scheme inevitably results in aliasing, owing to the restricted sampling bandwidth. In this paper, we derive an analytical solution to address this issue. More specifically, we use a conditioned logistic function as the analytic approximation of the cumulative distribution function (CDF) in a one-dimensional Gaussian signal and calculate the Gaussian integral by subtracting the CDFs. We then introduce this approximation in the two-dimensional pixel shading, and present Analytic-Splatting, which analytically approximates the Gaussian integral within the 2D-pixel window area to better capture the intensity response of each pixel. Moreover, we use the approximated response of the pixel window integral area to participate in the transmittance calculation of volume rendering, making Analytic-Splatting sensitive to the changes in pixel footprint at different resolutions. Experiments on various datasets validate that our approach has better anti-aliasing capability that gives more details and better fidelity.

![image](https://github.com/user-attachments/assets/ef6b4b2c-ecae-4ec5-8ef0-ba5c81e0f230)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.11056) | [⌨️ Code](https://github.com/lzhnb/Analytic-Splatting) | [🌐 Project Page](https://lzhnb.github.io/project-pages/analytic-splatting/)



#### <summary>Mipmap-GS: Let Gaussians Deform with Scale-specific Mipmap for Anti-aliasing Rendering
Authors: Jiameng Li, Yue Shi, Jiezhang Cao, Bingbing Ni, Wenjun Zhang, Kai Zhang, Luc Van Gool
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has attracted great attention in novel view synthesis because of its superior rendering efficiency and high fidelity. However, the trained Gaussians suffer from severe zooming degradation due to non-adjustable representation derived from single-scale training. Though some methods attempt to tackle this problem via post-processing techniques such as selective rendering or filtering techniques towards primitives, the scale-specific information is not involved in Gaussians. In this paper, we propose a unified optimization method to make Gaussians adaptive for arbitrary scales by self-adjusting the primitive properties (e.g., color, shape and size) and distribution (e.g., position). Inspired by the mipmap technique, we design pseudo ground-truth for the target scale and propose a scale-consistency guidance loss to inject scale information into 3D Gaussians. Our method is a plug-in module, applicable for any 3DGS models to solve the zoom-in and zoom-out aliasing. Extensive experiments demonstrate the effectiveness of our method. Notably, our method outperforms 3DGS in PSNR by an average of 9.25 dB for zoom-in and 10.40 dB for zoom-out on the NeRF Synthetic dataset.

![image](https://github.com/user-attachments/assets/3c0cc5e8-bd0a-42ce-9273-7f14dedd04cd)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.06286) | [⌨️ Code](https://github.com/renaissanceee/Mipmap-GS) | [🌐 Project Page]


<br>
<br>



## Hyperspectral

#### <summary>SpectralGaussians: Semantic, spectral 3D Gaussian splatting for multi-spectral scene representation, visualization and analysis
Authors: Saptarshi Neil Sinha, Holger Graf, Michael Weinmann
<details span>
<summary><b>Abstract</b></summary>
We propose a novel cross-spectral rendering framework based on 3D Gaussian Splatting (3DGS) that generates realistic and semantically meaningful splats from registered multi-view spectrum and segmentation maps. This extension enhances the representation of scenes with multiple spectra, providing insights into the underlying materials and segmentation. We introduce an improved physically-based rendering approach for Gaussian splats, estimating reflectance and lights per spectra, thereby enhancing accuracy and realism. In a comprehensive quantitative and qualitative evaluation, we demonstrate the superior performance of our approach with respect to other recent learning-based spectral scene representation approaches (i.e., XNeRF and SpectralNeRF) as well as other non-spectral state-of-the-art learning-based approaches. Our work also demonstrates the potential of spectral scene understanding for precise scene editing techniques like style transfer, inpainting, and removal. Thereby, our contributions address challenges in multi-spectral scene representation, rendering, and editing, offering new possibilities for diverse applications.

![image](https://github.com/user-attachments/assets/305f29c4-69c1-4972-9d1d-7eea2bde8fae)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.06975) | [⌨️ Code] | [🌐 Project Page]


<br>
<br>

## Event Camera

#### <summary>Event3DGS: Event-based 3D Gaussian Splatting for Fast Egomotion
Authors: Tianyi Xiong, Jiayi Wu, Botao He, Cornelia Fermuller, Yiannis Aloimonos, Heng Huang, Christopher A. Metzler
<details span>
<summary><b>Abstract</b></summary>
The recent emergence of 3D Gaussian splatting (3DGS) leverages the advantage of explicit point-based representations, which significantly improves the rendering speed and quality of novel-view synthesis. However, 3D radiance field rendering in environments with high-dynamic motion or challenging illumination condition remains problematic in real-world robotic tasks. The reason is that fast egomotion is prevalent real-world robotic tasks, which induces motion blur, leading to inaccuracies and artifacts in the reconstructed structure. To alleviate this problem, we propose Event3DGS, the first method that learns Gaussian Splatting solely from raw event streams. By exploiting the high temporal resolution of event cameras and explicit point-based representation, Event3DGS can reconstruct high-fidelity 3D structures solely from the event streams under fast egomotion. Our sparsity-aware sampling and progressive training approaches allow for better reconstruction quality and consistency. To further enhance the fidelity of appearance, we explicitly incorporate the motion blur formation process into a differentiable rasterizer, which is used with a limited set of blurred RGB images to refine the appearance. Extensive experiments on multiple datasets validate the superior rendering quality of Event3DGS compared with existing approaches, with over 95% lower training time and faster rendering speed in orders of magnitude.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/7a9eae92-d15b-4f6e-9682-4bdfbcb3c270)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02972) | [⌨️ Code] | [🌐 Project Page]


#### <summary>E2GS: Event Enhanced Gaussian Splatting
Authors: Hiroyuki Deguchi, Mana Masuda, Takuya Nakabayashi, Hideo Saito
<details span>
<summary><b>Abstract</b></summary>
Event cameras, known for their high dynamic range, absence of motion blur, and low energy usage, have recently found a wide range of applications thanks to these attributes. In the past few years, the field of event-based 3D reconstruction saw remarkable progress, with the Neural Radiance Field (NeRF) based approach demonstrating photorealistic view synthesis results. However, the volume rendering paradigm of NeRF necessitates extensive training and rendering times. In this paper, we introduce Event Enhanced Gaussian Splatting (E2GS), a novel method that incorporates event data into Gaussian Splatting, which has recently made significant advances in the field of novel view synthesis. Our E2GS effectively utilizes both blurry images and event data, significantly improving image deblurring and producing high-quality novel view synthesis. Our comprehensive experiments on both synthetic and real-world datasets demonstrate our E2GS can generate visually appealing renderings while offering faster training and rendering speed (140 FPS).
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f7dacef0-5803-4207-b613-c701a4f42bb9)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.14978) | [⌨️ Code](https://github.com/deguchihiroyuki/E2GS) | [🌐 Project Page]


#### <summary>Ev-GS: Event-based Gaussian splatting for Efficient and Accurate Radiance Field Rendering
Authors: Jingqian Wu, Shuo Zhu, Chutian Wang, Edmund Y. Lam
<details span>
<summary><b>Abstract</b></summary>
Computational neuromorphic imaging (CNI) with event cameras offers advantages such as minimal motion blur and enhanced dynamic range, compared to conventional frame-based methods. Existing event-based radiance field rendering methods are built on neural radiance field, which is computationally heavy and slow in reconstruction speed. Motivated by the two aspects, we introduce Ev-GS, the first CNI-informed scheme to infer 3D Gaussian splatting from a monocular event camera, enabling efficient novel view synthesis. Leveraging 3D Gaussians with pure event-based supervision, Ev-GS overcomes challenges such as the detection of fast-moving objects and insufficient lighting. Experimental results show that Ev-GS outperforms the method that takes frame-based signals as input by rendering realistic views with reduced blurring and improved visual quality. Moreover, it demonstrates competitive reconstruction quality and reduced computing occupancy compared to existing methods, which paves the way to a highly efficient CNI approach for signal processing.

![image](https://github.com/user-attachments/assets/3241bc0a-534e-4a1b-8845-7aa04f35b032)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.11343) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Elite-EvGS: Learning Event-based 3D Gaussian Splatting by Distilling Event-to-Video Priors
Authors: Zixin Zhang, Kanghao Chen, Lin Wang
<details span>
<summary><b>Abstract</b></summary>
Event cameras are bio-inspired sensors that output asynchronous and sparse event streams, instead of fixed frames. Benefiting from their distinct advantages, such as high dynamic range and high temporal resolution, event cameras have been applied to address 3D reconstruction, important for robotic mapping. Recently, neural rendering techniques, such as 3D Gaussian splatting (3DGS), have been shown successful in 3D reconstruction. However, it still remains under-explored how to develop an effective event-based 3DGS pipeline. In particular, as 3DGS typically depends on high-quality initialization and dense multiview constraints, a potential problem appears for the 3DGS optimization with events given its inherent sparse property. To this end, we propose a novel event-based 3DGS framework, named Elite-EvGS. Our key idea is to distill the prior knowledge from the off-the-shelf event-to-video (E2V) models to effectively reconstruct 3D scenes from events in a coarse-to-fine optimization manner. Specifically, to address the complexity of 3DGS initialization from events, we introduce a novel warm-up initialization strategy that optimizes a coarse 3DGS from the frames generated by E2V models and then incorporates events to refine the details. Then, we propose a progressive event supervision strategy that employs the window-slicing operation to progressively reduce the number of events used for supervision. This subtly relives the temporal randomness of the event frames, benefiting the optimization of local textural and global structural details. Experiments on the benchmark datasets demonstrate that Elite-EvGS can reconstruct 3D scenes with better textural and structural details. Meanwhile, our method yields plausible performance on the captured real-world data, including diverse challenging conditions, such as fast motion and low light scenes.

![image](https://github.com/user-attachments/assets/f571cb01-dfa4-4eb0-9761-b8ae4aa3b74e)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.13392) | [⌨️ Code] | [🌐 Project Page]


<br>
<br>


## Others


#### <summary>Point-Based Neural Rendering with Per-View Optimization

>  *whats the diference between this paper and 3D gaussian splatting?*

Authors: Georgios Kopanas, Julien Philip, Thomas Leimkühler, George Drettakis
<details span>
<summary><b>Abstract</b></summary>
There has recently been great interest in neural rendering methods. Some approaches use 3D geometry reconstructed with Multi-View Stereo (MVS) but cannot recover from the errors of this process, while others directly learn a volumetric neural representation, but suffer from expensive training and inference. We introduce a general approach that is initialized with MVS, but allows further optimization of scene properties in the space of input views, including depth and reprojected features, resulting in improved novel-view synthesis. A key element of our approach is our new differentiable point-based pipeline, based on bi-directional Elliptical Weighted Average splatting, a probabilistic depth test and effective camera selection. We use these elements together in our neural renderer, that outperforms all previous methods both in quality and speed in almost all scenes we tested. Our pipeline can be applied to multi-view harmonization and stylization in addition to novel-view synthesis.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/79790b26-a993-4a5c-9c01-b5921c74bf39)


</details>

[📃 arXiv:2109](https://arxiv.org/pdf/2109.02369) | [⌨️ Code](https://github.com/daipengwa/Neural-Point-Cloud-Rendering-via-Multi-Plane-Projection) | [🌐 Project Page](https://daipengwa.github.io/NeuralPointCloudRendering_ProjectPage/)






#### <summary>SurfelNeRF: Neural Surfel Radiance Fields for Online Photorealistic Reconstruction of Indoor Scenes

Authors: Yiming Gao, Yan-Pei Cao, Ying Shan
<details span>
<summary><b>Abstract</b></summary>
Online reconstructing and rendering of large-scale indoor scenes is a long-standing challenge. SLAM-based methods can reconstruct 3D scene geometry progressively in real time but can not render photorealistic results. While NeRF-based methods produce promising novel view synthesis results, their long offline optimization time and lack of geometric constraints pose challenges to efficiently handling online input. Inspired by the complementary advantages of classical 3D reconstruction and NeRF, we thus investigate marrying explicit geometric representation with NeRF rendering to achieve efficient online reconstruction and high-quality rendering. We introduce SurfelNeRF, a variant of neural radiance field which employs a flexible and scalable neural surfel representation to store geometric attributes and extracted appearance features from input images. We further extend the conventional surfel-based fusion scheme to progressively integrate incoming input frames into the reconstructed global neural scene representation. In addition, we propose a highly-efficient differentiable rasterization scheme for rendering neural surfel radiance fields, which helps SurfelNeRF achieve 10× speedups in training and inference time, respectively. Experimental results show that our method achieves the state-of-the-art 23.82 PSNR and 29.58 PSNR on ScanNet in feedforward inference and per-scene optimization settings, respectively.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/47434049-c6ed-43ee-9e10-ac154179f977)


</details>

[📃 arXiv:2304](https://arxiv.org/pdf/2304.08971) | [⌨️ Code](https://github.com/TencentARC/SurfelNeRF) | [🌐 Project Page](https://gymat.github.io/SurfelNeRF-web/)







#### <summary>Feature 3DGS: Supercharging 3D Gaussian Splatting to Enable Distilled Feature Fields
Authors: Zhihao Li, Yufei Wang, Alex Kot, Bihan Wen
<details span>
<summary><b>Abstract</b></summary>
3D scene representations have gained immense popularity in recent years. Methods that use Neural Radiance fields are versatile for traditional tasks such as novel view synthesis. In recent times, some work has emerged that aims to extend the functionality of NeRF beyond view synthesis, for semantically aware tasks such as editing and segmentation using 3D feature field distillation from 2D foundation models. However, these methods have two major limitations: (a) they are limited by the rendering speed of NeRF pipelines, and (b) implicitly represented feature fields suffer from continuity artifacts reducing feature quality. Recently, 3D Gaussian Splatting has shown state-of-the-art performance on real-time radiance field rendering. In this work, we go one step further: in addition to radiance field rendering, we enable 3D Gaussian splatting on arbitrary-dimension semantic features via 2D foundation model distillation. This translation is not straightforward: naively incorporating feature fields in the 3DGS framework encounters significant challenges, notably the disparities in spatial resolution and channel consistency between RGB images and feature maps. We propose architectural and training changes to efficiently avert this problem. Our proposed method is general, and our experiments showcase novel view semantic segmentation, language-guided editing and segment anything through learning feature fields from state-of-the-art 2D foundation models such as SAM and CLIP-LSeg. Across experiments, our distillation method is able to provide comparable or better results, while being significantly faster to both train and render. Additionally, to the best of our knowledge, we are the first method to enable point and bounding-box prompting for radiance field manipulation, by leveraging the SAM model.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0b26f700-48c1-4a06-9550-e70d84e018a1)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.03203) | [⌨️ Code](https://github.com/ShijieZhou-UCLA/feature-3dgs) | [🌐 Project Page](https://feature-3dgs.github.io/)



#### <summary>COLMAP-Free 3D Gaussian Splatting
Authors: Yang Fu, Sifei Liu, Amey Kulkarni, Jan Kautz, Alexei A. Efros, Xiaolong Wang
<details span>
<summary><b>Abstract</b></summary>
While neural rendering has led to impressive advances in scene reconstruction and novel view synthesis, it relies heavily on accurately pre-computed camera poses. To relax this constraint, multiple efforts have been made to train Neural Radiance Fields (NeRFs) without pre-processed camera poses. However, the implicit representations of NeRFs provide extra challenges to optimize the 3D structure and camera poses at the same time. On the other hand, the recently proposed 3D Gaussian Splatting provides new opportunities given its explicit point cloud representations. This paper leverages both the explicit geometric representation and the continuity of the input video stream to perform novel view synthesis without any SfM preprocessing. We process the input frames in a sequential manner and progressively grow the 3D Gaussians set by taking one input frame at a time, without the need to pre-compute the camera poses. Our method significantly improves over previous approaches in view synthesis and camera pose estimation under large motion changes.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9c38b2b3-d229-4c27-9f85-22a0390b2a7b)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.07504) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Splatter Image: Ultra-Fast Single-View 3D Reconstruction

Authors: Stanislaw Szymanowicz, Christian Rupprecht, Andrea Vedaldi
<details span>
<summary><b>Abstract</b></summary>
We introduce the \method, an ultra-efficient approach for monocular 3D object reconstruction. Splatter Image is based on Gaussian Splatting, which allows fast and high-quality reconstruction of 3D scenes from multiple images. We apply Gaussian Splatting to monocular reconstruction by learning a neural network that, at test time, performs reconstruction in a feed-forward manner, at 38 FPS. Our main innovation is the surprisingly straightforward design of this network, which, using 2D operators, maps the input image to one 3D Gaussian per pixel. The resulting set of Gaussians thus has the form an image, the Splatter Image. We further extend the method take several images as input via cross-view attention. Owning to the speed of the renderer (588 FPS), we use a single GPU for training while generating entire images at each iteration to optimize perceptual metrics like LPIPS. On several synthetic, real, multi-category and large-scale benchmark datasets, we achieve better results in terms of PSNR, LPIPS, and other metrics while training and evaluating much faster than prior works. 

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a579032d-05f5-4b78-b276-bb1ad0fe7d65)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.13150) | [⌨️ Code](https://github.com/szymanowiczs/splatter-image) | [🌐 Project Page]

#### <summary>Spacetime Gaussian Feature Splatting for Real-Time Dynamic View Synthesis
Authors: Zhan Li, Zhang Chen, Zhong Li, Yi Xu
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis of dynamic scenes has been an intriguing yet challenging problem. Despite recent advancements, simultaneously achieving high-resolution photorealistic results, real-time rendering, and compact storage remains a formidable task. To address these challenges, we propose Spacetime Gaussian Feature Splatting as a novel dynamic scene representation, composed of three pivotal components. First, we formulate expressive Spacetime Gaussians by enhancing 3D Gaussians with temporal opacity and parametric motion/rotation. This enables Spacetime Gaussians to capture static, dynamic, as well as transient content within a scene. Second, we introduce splatted feature rendering, which replaces spherical harmonics with neural features. These features facilitate the modeling of view- and time-dependent appearance while maintaining small size. Third, we leverage the guidance of training error and coarse depth to sample new Gaussians in areas that are challenging to converge with existing pipelines. Experiments on several established real-world datasets demonstrate that our method achieves state-of-the-art rendering quality and speed, while retaining compact storage. At 8K resolution, our lite-version model can render at 60 FPS on an Nvidia RTX 4090 GPU.
 
![image](https://github.com/user-attachments/assets/cc88bd7a-2b87-4b8a-9b5d-da2b38990417)

 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.16812) | [⌨️ Code](https://github.com/oppo-us-research/SpacetimeGaussians) | [🌐 Project Page](https://oppo-us-research.github.io/SpacetimeGaussians-website/)




#### <summary>On the Error Analysis of 3D Gaussian Splatting and an Optimal Projection Strategy
Authors: Letian Huang, Jiayang Bai, Jie Guo, Yuanqi Li, Yanwen Guo
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting has garnered extensive attention and application in real-time neural rendering. Concurrently, concerns have been raised about the limitations of this technology in aspects such as point cloud storage, performance, and robustness in sparse viewpoints, leading to various improvements. However, there has been a notable lack of attention to the fundamental problem of projection errors introduced by the local affine approximation inherent in the splatting itself, and the consequential impact of these errors on the quality of photo-realistic rendering. This paper addresses the projection error function of 3D Gaussian Splatting, commencing with the residual error from the first-order Taylor expansion of the projection function. The analysis establishes a correlation between the error and the Gaussian mean position. Subsequently, leveraging function optimization theory, this paper analyzes the function's minima to provide an optimal projection strategy for Gaussian Splatting referred to Optimal Gaussian Splatting, which can accommodate a variety of camera models. Experimental validation further confirms that this projection methodology reduces artifacts, resulting in a more convincingly realistic rendering.

 
</details>

[📃 arXiv:2402](https://arxiv.org/pdf/2402.00752.pdf) | [⌨️ Code] | [🌐 Project Page]

#### <summary>StopThePop: Sorted Gaussian Splatting for View-Consistent Real-time Rendering
Authors: Lukas Radl, Michael Steiner, Mathias Parger, Alexander Weinrauch, Bernhard Kerbl, Markus Steinberger
<details span>
<summary><b>Abstract</b></summary>
Gaussian Splatting has emerged as a prominent model for constructing 3D representations from images across diverse domains. However, the efficiency of the 3D Gaussian Splatting rendering pipeline relies on several simplifications. Notably, reducing Gaussian to 2D splats with a single view-space depth introduces popping and blending artifacts during view rotation. Addressing this issue requires accurate per-pixel depth computation, yet a full per-pixel sort proves excessively costly compared to a global sort operation. In this paper, we present a novel hierarchical rasterization approach that systematically resorts and culls splats with minimal processing overhead. Our software rasterizer effectively eliminates popping artifacts and view inconsistencies, as demonstrated through both quantitative and qualitative measurements. Simultaneously, our method mitigates the potential for cheating view-dependent effects with popping, ensuring a more authentic representation. Despite the elimination of cheating, our approach achieves comparable quantitative results for test images, while increasing the consistency for novel view synthesis in motion. Due to its design, our hierarchical approach is only 4% slower on average than the original Gaussian Splatting. Notably, enforcing consistency enables a reduction in the number of Gaussians by approximately half with nearly identical quality and view-consistency. Consequently, rendering performance is nearly doubled, making our approach 1.6x faster than the original Gaussian Splatting, with a 50% reduction in memory requirements.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/54fc981c-aa01-4a99-8870-5085d6121e95)

 
</details>

[📃 arXiv:2402](https://arxiv.org/pdf/2402.00525) | [⌨️ Code](https://github.com/r4dl/StopThePop) | [🌐 Project Page](https://r4dl.github.io/StopThePop/)



#### <summary>GES: Generalized Exponential Splatting for Efficient Radiance Field Rendering

Authors: Abdullah Hamdi, Luke Melas-Kyriazi, Jinjie Mai, Guocheng Qian, Ruoshi Liu, Carl Vondrick, Bernard Ghanem, Andrea Vedaldi
<details span>
<summary><b>Abstract</b></summary>
Advancements in 3D Gaussian Splatting have significantly accelerated 3D reconstruction and generation. However, it may require a large number of Gaussians, which creates a substantial memory footprint. This paper introduces GES (Generalized Exponential Splatting), a novel representation that employs Generalized Exponential Function (GEF) to model 3D scenes, requiring far fewer particles to represent a scene and thus significantly outperforming Gaussian Splatting methods in efficiency with a plug-and-play replacement ability for Gaussian-based utilities. GES is validated theoretically and empirically in both principled 1D setup and realistic 3D scenes. It is shown to represent signals with sharp edges more accurately, which are typically challenging for Gaussians due to their inherent low-pass characteristics. Our empirical analysis demonstrates that GEF outperforms Gaussians in fitting natural-occurring signals (e.g. squares, triangles, and parabolic signals), thereby reducing the need for extensive splitting operations that increase the memory footprint of Gaussian Splatting. With the aid of a frequency-modulated loss, GES achieves competitive performance in novel-view synthesis benchmarks while requiring less than half the memory storage of Gaussian Splatting and increasing the rendering speed by up to 39%.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/518d0fc8-db05-408f-b1c4-27d444b1f34d)


</details>

[📃 arXiv:2402](https://arxiv.org/pdf/2402.10128) | [⌨️ Code](https://github.com/ajhamdi/ges-splatting) | [🌐 Project Page](https://abdullahamdi.com/ges/)


#### <summary>InstantSplat: Unbounded Sparse-view Pose-free Gaussian Splatting in 40 Seconds
Authors: Zhiwen Fan, Wenyan Cong, Kairun Wen, Kevin Wang, Jian Zhang, Xinghao Ding, Danfei Xu, Boris Ivanovic, Marco Pavone, Georgios Pavlakos, Zhangyang Wang, Yue Wang
<details span>
<summary><b>Abstract</b></summary>
While novel view synthesis (NVS) has made substantial progress in 3D computer vision, it typically requires an initial estimation of camera intrinsics and extrinsics from dense viewpoints. This pre-processing is usually conducted via a Structure-from-Motion (SfM) pipeline, a procedure that can be slow and unreliable, particularly in sparse-view scenarios with insufficient matched features for accurate reconstruction. In this work, we integrate the strengths of point-based representations (e.g., 3D Gaussian Splatting, 3D-GS) with end-to-end dense stereo models (DUSt3R) to tackle the complex yet unresolved issues in NVS under unconstrained settings, which encompasses pose-free and sparse view challenges. Our framework, InstantSplat, unifies dense stereo priors with 3D-GS to build 3D Gaussians of large-scale scenes from sparseview & pose-free images in less than 1 minute. Specifically, InstantSplat comprises a Coarse Geometric Initialization (CGI) module that swiftly establishes a preliminary scene structure and camera parameters across all training views, utilizing globally-aligned 3D point maps derived from a pre-trained dense stereo pipeline. This is followed by the Fast 3D-Gaussian Optimization (F-3DGO) module, which jointly optimizes the 3D Gaussian attributes and the initialized poses with pose regularization. Experiments conducted on the large-scale outdoor Tanks & Temples datasets demonstrate that InstantSplat significantly improves SSIM (by 32%) while concurrently reducing Absolute Trajectory Error (ATE) by 80%. These establish InstantSplat as a viable solution for scenarios involving posefree and sparse-view conditions.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/be988f2c-5843-41b1-8a28-a2a03a8f1a7b)

 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.20309.pdf) | [⌨️ Code] | [🌐 Project Page](https://instantsplat.github.io/)

#### <summary>FDGaussian: Fast Gaussian Splatting from Single Image via Geometric-aware Diffusion Model
Authors: Qijun Feng, Zhen Xing, Zuxuan Wu, Yu-Gang Jiang
<details span>
<summary><b>Abstract</b></summary>
Reconstructing detailed 3D objects from single-view images remains a challenging task due to the limited information available. In this paper, we introduce FDGaussian, a novel two-stage framework for single-image 3D reconstruction. Recent methods typically utilize pre-trained 2D diffusion models to generate plausible novel views from the input image, yet they encounter issues with either multi-view inconsistency or lack of geometric fidelity. To overcome these challenges, we propose an orthogonal plane decomposition mechanism to extract 3D geometric features from the 2D input, enabling the generation of consistent multi-view images. Moreover, we further accelerate the state-of-the-art Gaussian Splatting incorporating epipolar attention to fuse images from different viewpoints. We demonstrate that FDGaussian generates images with high consistency across different views and reconstructs high-quality 3D objects, both qualitatively and quantitatively.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ab99e8a7-63ae-4597-a7dd-97d8dc5051c5)

 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.10242) | [⌨️ Code] | [🌐 Project Page](https://qjfeng.net/FDGaussian/)






#### <summary>3DGS-Calib: 3D Gaussian Splatting for Multimodal SpatioTemporal Calibration
Authors: Quentin Herau, Moussab Bennehar, Arthur Moreau, Nathan Piasco, Luis Roldao, Dzmitry Tsishkou, Cyrille Migniot, Pascal Vasseur, Cédric Demonceaux
<details span>
<summary><b>Abstract</b></summary>
Reliable multimodal sensor fusion algorithms require accurate spatiotemporal calibration. Recently, targetless calibration techniques based on implicit neural representations have proven to provide precise and robust results. Nevertheless, such methods are inherently slow to train given the high computational overhead caused by the large number of sampled points required for volume rendering. With the recent introduction of 3D Gaussian Splatting as a faster alternative to implicit representation methods, we propose to leverage this new rendering approach to achieve faster multi-sensor calibration. We introduce 3DGS-Calib, a new calibration method that relies on the speed and rendering accuracy of 3D Gaussian Splatting to achieve multimodal spatiotemporal calibration that is accurate, robust, and with a substantial speed-up compared to methods relying on implicit neural representations. We demonstrate the superiority of our proposal with experimental results on sequences from KITTI-360, a widely used driving dataset.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/08f7bcc0-f92a-4f9c-b17e-5c0bc7276ea4)


</details>


[📃 arXiv:2403](https://arxiv.org/pdf/2403.11577) | [⌨️ Code] | [🌐 Project Page]





#### <summary>RadSplat: Radiance Field-Informed Gaussian Splatting for Robust Real-Time Rendering with 900+ FPS
Authors: Michael Niemeyer, Fabian Manhardt, Marie-Julie Rakotosaona, Michael Oechsle, Daniel Duckworth, Rama Gosula, Keisuke Tateno, John Bates, Dominik Kaeser, Federico Tombari
<details span>
<summary><b>Abstract</b></summary>
Recent advances in view synthesis and real-time rendering have achieved photorealistic quality at impressive rendering speeds. While Radiance Field-based methods achieve state-of-the-art quality in challenging scenarios such as in-the-wild captures and large-scale scenes, they often suffer from excessively high compute requirements linked to volumetric rendering. Gaussian Splatting-based methods, on the other hand, rely on rasterization and naturally achieve real-time rendering but suffer from brittle optimization heuristics that underperform on more challenging scenes. In this work, we present RadSplat, a lightweight method for robust real-time rendering of complex scenes. Our main contributions are threefold. First, we use radiance fields as a prior and supervision signal for optimizing point-based scene representations, leading to improved quality and more robust optimization. Next, we develop a novel pruning technique reducing the overall point count while maintaining high quality, leading to smaller and more compact scene representations with faster inference speeds. Finally, we propose a novel test-time filtering approach that further accelerates rendering and allows to scale to larger, house-sized scenes. We find that our method enables state-of-the-art synthesis of complex captures at 900+ FPS.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f79836ac-ec64-4b5b-b3c8-fa08e3e4782f)

</details>


[📃 arXiv:2403](https://arxiv.org/pdf/2403.13806) | [⌨️ Code] | [🌐 Project Page](https://m-niemeyer.github.io/radsplat/)

#### <summary>Analytic-Splatting: Anti-Aliased 3D Gaussian Splatting via Analytic Integration
Authors: Zhihao Liang, Qi Zhang, Wenbo Hu, Ying Feng, Lei Zhu, Kui Jia
<details span>
<summary><b>Abstract</b></summary>
The 3D Gaussian Splatting (3DGS) gained its popularity recently by combining the advantages of both primitive-based and volumetric 3D representations, resulting in improved quality and efficiency for 3D scene rendering. However, 3DGS is not alias-free, and its rendering at varying resolutions could produce severe blurring or jaggies. This is because 3DGS treats each pixel as an isolated, single point rather than as an area, causing insensitivity to changes in the footprints of pixels. Consequently, this discrete sampling scheme inevitably results in aliasing, owing to the restricted sampling bandwidth. In this paper, we derive an analytical solution to address this issue. More specifically, we use a conditioned logistic function as the analytic approximation of the cumulative distribution function (CDF) in a one-dimensional Gaussian signal and calculate the Gaussian integral by subtracting the CDFs. We then introduce this approximation in the two-dimensional pixel shading, and present Analytic-Splatting, which analytically approximates the Gaussian integral within the 2D-pixel window area to better capture the intensity response of each pixel. Moreover, we use the approximated response of the pixel window integral area to participate in the transmittance calculation of volume rendering, making Analytic-Splatting sensitive to the changes in pixel footprint at different resolutions. Experiments on various datasets validate that our approach has better anti-aliasing capability that gives more details and better fidelity.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/53bce85b-bcba-4997-9729-e692fce4fa42)


</details>


[📃 arXiv:2403](https://arxiv.org/pdf/2403.11056) | [⌨️ Code](https://github.com/lzhnb/Analytic-Splatting) | [🌐 Project Page](https://lzhnb.github.io/project-pages/analytic-splatting/)


#### <summary>EGGS: Edge Guided Gaussian Splatting for Radiance Fields
Authors: Yuanhao Gong
<details span>
<summary><b>Abstract</b></summary>
The Gaussian splatting methods are getting popular. However, their loss function only contains the ℓ1 norm and the structural similarity between the rendered and input images, without considering the edges in these images. It is well-known that the edges in an image provide important information. Therefore, in this paper, we propose an Edge Guided Gaussian Splatting (EGGS) method that leverages the edges in the input images. More specifically, we give the edge region a higher weight than the flat region. With such edge guidance, the resulting Gaussian particles focus more on the edges instead of the flat regions. Moreover, such edge guidance does not crease the computation cost during the training and rendering stage. The experiments confirm that such simple edge-weighted loss function indeed improves about 1 ∼ 2 dB on several difference data sets. With simply plugging in the edge guidance, the proposed method can improve all Gaussian splatting methods in different scenarios, such as human head modeling, building 3D reconstruction, etc.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/7b2ce10d-d422-4c21-83ce-01b9805ef2e7)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.09105.pdf) | [⌨️ Code] | [🌐 Project Page]


#### <summary>InFusion: Inpainting 3D Gaussians via Learning Depth Completion from Diffusion Prior
Authors: Zhiheng Liu, Hao Ouyang, Qiuyu Wang, Ka Leong Cheng, Jie Xiao, Kai Zhu, Nan Xue, Yu Liu, Yujun Shen, Yang Cao
<details span>
<summary><b>Abstract</b></summary>
3D Gaussians have recently emerged as an efficient representation for novel view synthesis. This work studies its editability with a particular focus on the inpainting task, which aims to supplement an incomplete set of 3D Gaussians with additional points for visually harmonious rendering. Compared to 2D inpainting, the crux of inpainting 3D Gaussians is to figure out the rendering-relevant properties of the introduced points, whose optimization largely benefits from their initial 3D positions. To this end, we propose to guide the point initialization with an image-conditioned depth completion model, which learns to directly restore the depth map based on the observed image. Such a design allows our model to fill in depth values at an aligned scale with the original depth, and also to harness strong generalizability from largescale diffusion prior. Thanks to the more accurate depth completion, our approach, dubbed InFusion, surpasses existing alternatives with sufficiently better fidelity and efficiency under various complex scenarios. We further demonstrate the effectiveness of InFusion with several practical applications, such as inpainting with user-specific texture or with novel object insertion.
 
![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/b77098e6-16ae-4adb-b16e-46b94569feb8)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.11613.pdf) | [⌨️ Code](https://github.com/ali-vilab/infusion) | [🌐 Project Page](https://johanan528.github.io/Infusion/)





#### <summary>Dynamic Gaussians Mesh: Consistent Mesh Reconstruction from Monocular Videos
Authors: Isabella Liu, Hao Su, Xiaolong Wang
<details span>
<summary><b>Abstract</b></summary>
Modern 3D engines and graphics pipelines require mesh as a memory-efficient representation, which allows efficient rendering, geometry processing, texture editing, and many other downstream operations. However, it is still highly difficult to obtain high-quality mesh in terms of structure and detail from monocular visual observations. The problem becomes even more challenging for dynamic scenes and objects. To this end, we introduce Dynamic Gaussians Mesh (DG-Mesh), a framework to reconstruct a high-fidelity and time-consistent mesh given a single monocular video. Our work leverages the recent advancement in 3D Gaussian Splatting to construct the mesh sequence with temporal consistency from a video. Building on top of this representation, DG-Mesh recovers high-quality meshes from the Gaussian points and can track the mesh vertices over time, which enables applications such as texture editing on dynamic objects. We introduce the Gaussian-Mesh Anchoring, which encourages evenly distributed Gaussians, resulting better mesh reconstruction through mesh-guided densification and pruning on the deformed Gaussians. By applying cycle-consistent deformation between the canonical and the deformed space, we can project the anchored Gaussian back to the canonical space and optimize Gaussians across all time frames. During the evaluation on different datasets, DG-Mesh provides significantly better mesh reconstruction and rendering than baselines.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e60ae628-a057-4c7f-abac-1eb981815a8c)

</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.12379) | [⌨️ Code](https://github.com/Isabella98Liu/DG-Mesh) | [🌐 Project Page](https://www.liuisabella.com/DG-Mesh/)



#### <summary>Bootstrap 3D Reconstructed Scenes from 3D Gaussian Splatting
Authors: Yifei Gao, Jie Ou, Lei Wang, Jun Cheng
<details span>
<summary><b>Abstract</b></summary>
Recent developments in neural rendering techniques have greatly enhanced the rendering of photo-realistic 3D scenes across both academic and commercial fields. The latest method, known as 3D Gaussian Splatting (3D-GS), has set new benchmarks for rendering quality and speed. Nevertheless, the limitations of 3D-GS become pronounced in synthesizing new viewpoints, especially for views that greatly deviate from those seen during training. Additionally, issues such as dilation and aliasing arise when zooming in or out. These challenges can all be traced back to a single underlying issue: insufficient sampling. In our paper, we present a bootstrapping method that significantly addresses this problem. This approach employs a diffusion model to enhance the rendering of novel views using trained 3D-GS, thereby streamlining the training process. Our results indicate that bootstrapping effectively reduces artifacts, as well as clear enhancements on the evaluation metrics. Furthermore, we show that our method is versatile and can be easily integrated, allowing various 3D reconstruction projects to benefit from our approach.


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.18669) | [⌨️ Code] | [🌐 Project Page]




#### <summary>GS-LRM: Large Reconstruction Model for 3D Gaussian Splatting
Authors: Kai Zhang, Sai Bi, Hao Tan, Yuanbo Xiangli, Nanxuan Zhao, Kalyan Sunkavalli, Zexiang Xu
<details span>
<summary><b>Abstract</b></summary>
We propose GS-LRM, a scalable large reconstruction model that can predict high-quality 3D Gaussian primitives from 2-4 posed sparse images in 0.23 seconds on single A100 GPU. Our model features a very simple transformer-based architecture; we patchify input posed images, pass the concatenated multi-view image tokens through a sequence of transformer blocks, and decode final per-pixel Gaussian parameters directly from these tokens for differentiable rendering. In contrast to previous LRMs that can only reconstruct objects, by predicting per-pixel Gaussians, GS-LRM naturally handles scenes with large variations in scale and complexity. We show that our model can work on both object and scene captures by training it on Objaverse and RealEstate10K respectively. In both scenarios, the models outperform state-of-the-art baselines by a wide margin. We also demonstrate applications of our model in downstream 3D generation tasks.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9b7f67c4-0a7e-4b65-9534-e554135e8029)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.19702) | [⌨️ Code] | [🌐 Project Page](https://sai-bi.github.io/project/gs-lrm/)


#### <summary>3D Gaussian Splatting as Markov Chain Monte Carlo
Authors: Shakiba Kheradmand, Daniel Rebain, Gopal Sharma, Weiwei Sun, Jeff Tseng, Hossam Isack, Abhishek Kar, Andrea Tagliasacchi, Kwang Moo Yi
<details span>
<summary><b>Abstract</b></summary>
While 3D Gaussian Splatting has recently become popular for neural rendering, current methods rely on carefully engineered cloning and splitting strategies for placing Gaussians, which does not always generalize and may lead to poor-quality renderings. In addition, for real-world scenes, they rely on a good initial point cloud to perform well. In this work, we rethink 3D Gaussians as random samples drawn from an underlying probability distribution describing the physical representation of the scene -- in other words, Markov Chain Monte Carlo (MCMC) samples. Under this view, we show that the 3D Gaussian updates are strikingly similar to a Stochastic Langevin Gradient Descent (SGLD) update. As with MCMC, samples are nothing but past visit locations, adding new Gaussians under our framework can simply be realized without heuristics as placing Gaussians at existing Gaussian locations. To encourage using fewer Gaussians for efficiency, we introduce an L1-regularizer on the Gaussians. On various standard evaluation scenes, we show that our method provides improved rendering quality, easy control over the number of Gaussians, and robustness to initialization.



</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.09591) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Splat-MOVER: Multi-Stage, Open-Vocabulary Robotic Manipulation via Editable Gaussian Splatting
Authors: Ola Shorinwa, Johnathan Tucker, Aliyah Smith, Aiden Swann, Timothy Chen, Roya Firoozi, Monroe Kennedy III, Mac Schwager
<details span>
<summary><b>Abstract</b></summary>
We present Splat-MOVER, a modular robotics stack for open-vocabulary robotic manipulation, which leverages the editability of Gaussian Splatting (GSplat) scene representations to enable multi-stage manipulation tasks. Splat-MOVER consists of: (i) ASK-Splat, a GSplat representation that distills latent codes for language semantics and grasp affordance into the 3D scene. ASK-Splat enables geometric, semantic, and affordance understanding of 3D scenes, which is critical for many robotics tasks; (ii) SEE-Splat, a real-time scene-editing module using 3D semantic masking and infilling to visualize the motions of objects that result from robot interactions in the real-world. SEE-Splat creates a "digital twin" of the evolving environment throughout the manipulation task; and (iii) Grasp-Splat, a grasp generation module that uses ASK-Splat and SEE-Splat to propose candidate grasps for open-world objects. ASK-Splat is trained in real-time from RGB images in a brief scanning phase prior to operation, while SEE-Splat and Grasp-Splat run in real-time during operation. We demonstrate the superior performance of Splat-MOVER in hardware experiments on a Kinova robot compared to two recent baselines in four single-stage, open-vocabulary manipulation tasks, as well as in four multi-stage manipulation tasks using the edited scene to reflect scene changes due to prior manipulation stages, which is not possible with the existing baselines. Code for this project and a link to the project page will be made available soon.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/7ce29b02-e9f7-462b-8b37-905028751777)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.04378) | [⌨️ Code] | [🌐 Project Page]


#### <summary>GDGS: Gradient Domain Gaussian Splatting for Sparse Representation of Radiance Fields
Authors: Yuanhao Gong
<details span>
<summary><b>Abstract</b></summary>
The 3D Gaussian splatting methods are getting popular. However, they work directly on the signal, leading to a dense representation of the signal. Even with some techniques such as pruning or distillation, the results are still dense. In this paper, we propose to model the gradient of the original signal. The gradients are much sparser than the original signal. Therefore, the gradients use much less Gaussian splats, leading to the more efficient storage and thus higher computational performance during both training and rendering. Thanks to the sparsity, during the view synthesis, only a small mount of pixels are needed, leading to much higher computational performance (100∼1000× faster). And the 2D image can be recovered from the gradients via solving a Poisson equation with linear computation complexity. Several experiments are performed to confirm the sparseness of the gradients and the computation performance of the proposed method. The method can be applied various applications, such as human body modeling and indoor environment modeling.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d9ea9da8-fb06-4f00-9e39-5ed5e548178e)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.05446) | [⌨️ Code] | [🌐 Project Page]

#### <summary>I3DGS: Improve 3D Gaussian Splatting from Multiple Dimensions
Authors: Jinwei Lin
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting is a novel method for 3D view synthesis, which can gain an implicit neural learning rendering result than the traditional neural rendering technology but keep the more high-definition fast rendering speed. But it is still difficult to achieve a fast enough efficiency on 3D Gaussian Splatting for the practical applications. To Address this issue, we propose the I3DS, a synthetic model performance improvement evaluation solution and experiments test. From multiple and important levels or dimensions of the original 3D Gaussian Splatting, we made more than two thousand various kinds of experiments to test how the selected different items and components can make an impact on the training efficiency of the 3D Gaussian Splatting model. In this paper, we will share abundant and meaningful experiences and methods about how to improve the training, performance and the impacts caused by different items of the model. A special but normal Integer compression in base 95 and a floating-point compression in base 94 with ASCII encoding and decoding mechanism is presented. Many real and effective experiments and test results or phenomena will be recorded. After a series of reasonable fine-tuning, I3DS can gain excellent performance improvements than the previous one. The project code is available as open source.


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.06408) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Toon3D: Seeing Cartoons from a New Perspective
Authors: Ethan Weber, Riley Peterlinz, Rohan Mathur, Frederik Warburg, Alexei A. Efros, Angjoo Kanazawa
<details span>
<summary><b>Abstract</b></summary>
In this work, we recover the underlying 3D structure of non-geometrically consistent scenes. We focus our analysis on hand-drawn images from cartoons and anime. Many cartoons are created by artists without a 3D rendering engine, which means that any new image of a scene is hand-drawn. The hand-drawn images are usually faithful representations of the world, but only in a qualitative sense, since it is difficult for humans to draw multiple perspectives of an object or scene 3D consistently. Nevertheless, people can easily perceive 3D scenes from inconsistent inputs! In this work, we correct for 2D drawing inconsistencies to recover a plausible 3D structure such that the newly warped drawings are consistent with each other. Our pipeline consists of a user-friendly annotation tool, camera pose estimation, and image deformation to recover a dense structure. Our method warps images to obey a perspective camera model, enabling our aligned results to be plugged into novel-view synthesis reconstruction methods to experience cartoons from viewpoints never drawn before.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a5fc1f90-cfc1-4508-a21a-16380efb7682)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.10320) | [⌨️ Code](https://github.com/ethanweber/toon3d) | [🌐 Project Page](https://toon3d.studio/)


#### <summary>From NeRFs to Gaussian Splats, and Back
Authors: Siming He, Zach Osman, Pratik Chaudhari
<details span>
<summary><b>Abstract</b></summary>
For robotics applications where there is a limited number of (typically ego-centric) views, parametric representations such as neural radiance fields (NeRFs) generalize better than non-parametric ones such as Gaussian splatting (GS) to views that are very different from those in the training data; GS however can render much faster than NeRFs. We develop a procedure to convert back and forth between the two. Our approach achieves the best of both NeRFs (superior PSNR, SSIM, and LPIPS on dissimilar views, and a compact representation) and GS (real-time rendering and ability for easily modifying the representation); the computational cost of these conversions is minor compared to training the two from scratch.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/560d207a-149a-4830-985f-5e45132f712b)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.09717) | [⌨️ Code](https://github.com/grasp-lyrl/NeRFtoGSandBack) | [🌐 Project Page]

#### <summary>MirrorGaussian: Reflecting 3D Gaussians for Reconstructing Mirror Reflections
Authors: Jiayue Liu, Xiao Tang, Freeman Cheng, Roy Yang, Zhihao Li, Jianzhuang Liu, Yi Huang, Jiaqi Lin, Shiyong Liu, Xiaofei Wu, Songcen Xu, Chun Yuan
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting showcases notable advancements in photo-realistic and real-time novel view synthesis. However, it faces challenges in modeling mirror reflections, which exhibit substantial appearance variations from different viewpoints. To tackle this problem, we present MirrorGaussian, the first method for mirror scene reconstruction with real-time rendering based on 3D Gaussian Splatting. The key insight is grounded on the mirror symmetry between the real-world space and the virtual mirror space. We introduce an intuitive dual-rendering strategy that enables differentiable rasterization of both the real-world 3D Gaussians and the mirrored counterpart obtained by reflecting the former about the mirror plane. All 3D Gaussians are jointly optimized with the mirror plane in an end-to-end framework. MirrorGaussian achieves high-quality and real-time rendering in scenes with mirrors, empowering scene editing like adding new mirrors and objects. Comprehensive experiments on multiple datasets demonstrate that our approach significantly outperforms existing methods, achieving state-of-the-art results.

![image]()

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.11921) | [⌨️ Code] | [🌐 Project Page](https://mirror-gaussian.github.io/)


#### <summary>MotionGS: Compact Gaussian Splatting SLAM by Motion Filter
Authors: Xinli Guo, Peng Han, Weidong Zhang, Hongtian Chen
<details span>
<summary><b>Abstract</b></summary>
With their high-fidelity scene representation capability, the attention of SLAM field is deeply attracted by the Neural Radiation Field (NeRF) and 3D Gaussian Splatting (3DGS). Recently, there has been a Surge in NeRF-based SLAM, while 3DGS-based SLAM is sparse. A novel 3DGS-based SLAM approach with a fusion of deep visual feature, dual keyframe selection and 3DGS is presented in this paper. Compared with the existing methods, the proposed selectively tracking is achieved by feature extraction and motion filter on each frame. The joint optimization of pose and 3D Gaussian runs through the entire mapping process. Additionally, the coarse-to-fine pose estimation and compact Gaussian scene representation are implemented by dual keyfeature selection and novel loss functions. Experimental results demonstrate that the proposed algorithm not only outperforms the existing methods in tracking and mapping, but also has less memory usage.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/96902341-c270-4797-a390-01cf276ff717)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.11129) | [⌨️ Code](https://github.com/Antonio521/MotionGS) | [🌐 Project Page]



#### <summary>GarmentDreamer: 3DGS Guided Garment Synthesis with Diverse Geometry and Texture Details
Authors: Boqian Li, Xuan Li, Ying Jiang, Tianyi Xie, Feng Gao, Huamin Wang, Yin Yang, Chenfanfu Jiang
<details span>
<summary><b>Abstract</b></summary>
Traditional 3D garment creation is labor-intensive, involving sketching, modeling, UV mapping, and texturing, which are time-consuming and costly. Recent advances in diffusion-based generative models have enabled new possibilities for 3D garment generation from text prompts, images, and videos. However, existing methods either suffer from inconsistencies among multi-view images or require additional processes to separate cloth from the underlying human model. In this paper, we propose GarmentDreamer, a novel method that leverages 3D Gaussian Splatting (GS) as guidance to generate wearable, simulation-ready 3D garment meshes from text prompts. In contrast to using multi-view images directly predicted by generative models as guidance, our 3DGS guidance ensures consistent optimization in both garment deformation and texture synthesis. Our method introduces a novel garment augmentation module, guided by normal and RGBA information, and employs implicit Neural Texture Fields (NeTF) combined with Score Distillation Sampling (SDS) to generate diverse geometric and texture details. We validate the effectiveness of our approach through comprehensive qualitative and quantitative experiments, showcasing the superior performance of GarmentDreamer over state-of-the-art alternatives.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3815dd96-e2f6-4294-aae1-d4bb4868112e)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12420) | [⌨️ Code] | [🌐 Project Page](https://xuan-li.github.io/GarmentDreamerDemo/)


#### <summary>Gaussian Control with Hierarchical Semantic Graphs in 3D Human Recovery
Authors: Hongsheng Wang, Weiyue Zhang, Sihao Liu, Xinrui Zhou, Shengyu Zhang, Fei Wu, Feng Lin
<details span>
<summary><b>Abstract</b></summary>
Although 3D Gaussian Splatting (3DGS) has recently made progress in 3D human reconstruction, it primarily relies on 2D pixel-level supervision, overlooking the geometric complexity and topological relationships of different body parts. To address this gap, we introduce the Hierarchical Graph Human Gaussian Control (HUGS) framework for achieving high-fidelity 3D human reconstruction. Our approach involves leveraging explicitly semantic priors of body parts to ensure the consistency of geometric topology, thereby enabling the capture of the complex geometrical and topological associations among body parts. Additionally, we disentangle high-frequency features from global human features to refine surface details in body parts. Extensive experiments demonstrate that our method exhibits superior performance in human body reconstruction, particularly in enhancing surface details and accurately reconstructing body part junctions.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/012023eb-2fd6-4172-b112-1786a9a760c4)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12477) | [⌨️ Code](https://github.com/3DHumanRehab/SemanticGraph-Gaussian) | [🌐 Project Page](https://wanghongsheng01.github.io/HUGS/)


#### <summary>LAGA: Layered 3D Avatar Generation and Customization via Gaussian Splatting
Authors: Jia Gong, Shenyu Ji, Lin Geng Foo, Kang Chen, Hossein Rahmani, Jun Liu
<details span>
<summary><b>Abstract</b></summary>
Creating and customizing a 3D clothed avatar from textual descriptions is a critical and challenging task. Traditional methods often treat the human body and clothing as inseparable, limiting users' ability to freely mix and match garments. In response to this limitation, we present LAyered Gaussian Avatar (LAGA), a carefully designed framework enabling the creation of high-fidelity decomposable avatars with diverse garments. By decoupling garments from avatar, our framework empowers users to conviniently edit avatars at the garment level. Our approach begins by modeling the avatar using a set of Gaussian points organized in a layered structure, where each layer corresponds to a specific garment or the human body itself. To generate high-quality garments for each layer, we introduce a coarse-to-fine strategy for diverse garment generation and a novel dual-SDS loss function to maintain coherence between the generated garments and avatar components, including the human body and other garments. Moreover, we introduce three regularization losses to guide the movement of Gaussians for garment transfer, allowing garments to be freely transferred to various avatars. Extensive experimentation demonstrates that our approach surpasses existing methods in the generation of 3D clothed humans.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0970f45a-e7ae-4ba0-aab2-d64cc122e9c9)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12663) | [⌨️ Code] | [🌐 Project Page](https://gongjia0208.github.io/LAGA/)



#### <summary>N-Dimensional Gaussians for Fitting of High Dimensional
Authors: Stavros Diolatzis, Tobias Zirr1, Alexandr Kuznetsov1, Georgios Kopanas, Anton Kaplanyan1
<details span>
<summary><b>Abstract</b></summary>
In the wake of many new ML-inspired approaches for reconstruct ing and representing high-quality 3D content, recent hybrid and explicitly learned representations exhibit promising performance and quality characteristics. However, their scaling to higher dimen sions is challenging, e.g. when accounting for dynamic content with respect to additional parameters such as material properties, illumination, or time. In this paper, we tackle these challenges for an explicit representations based on Gaussian mixture models. With oursolutions, wearriveatefficientfittingofcompactN-dimensional Gaussian mixtures and enable efficient evaluation at render time: For fast fitting and evaluation, we introduce a high-dimensional culling scheme that efficiently bounds N-D Gaussians, inspired by Locality Sensitive Hashing. For adaptive refinement yet com pact representation, we introduce a loss-adaptive density control scheme that incrementally guides the use of additional capacity towards missing details. With these tools we can for the first time represent complex appearance that depends on many input dimen sions beyond position or viewing angle within a compact, explicit representation optimized in minutes and rendered in milliseconds. 

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/1d5fb305-a161-4347-9b31-c068c3edfb5b)


</details>

[📃 arXiv:24xx](https://www.sdiolatz.info/ndg-fitting/static/files/ngd-paper-compressed.pdf) | [⌨️ Code] | [🌐 Project Page](https://www.sdiolatz.info/ndg-fitting/)


#### <summary>RoGS: Large Scale Road Surface Reconstruction based on 2D Gaussian Splatting
Authors: Zhiheng Feng, Wenhua Wu, Hesheng Wang
<details span>
<summary><b>Abstract</b></summary>
Road surface reconstruction plays a crucial role in autonomous driving, which can be used for road lane perception and autolabeling tasks. Recently, mesh-based road surface reconstruction algorithms show promising reconstruction results. However, these mesh-based methods suffer from slow speed and poor rendering quality. In contrast, the 3D Gaussian Splatting (3DGS) shows superior rendering speed and quality. Although 3DGS employs explicit Gaussian spheres to represent the scene, it lacks the ability to directly represent the geometric information of the scene. To address this limitation, we propose a novel large-scale road surface reconstruction approach based on 2D Gaussian Splatting (2DGS), named RoGS. The geometric shape of the road is explicitly represented using 2D Gaussian surfels, where each surfel stores color, semantics, and geometric information. Compared to Gaussian spheres, the Gaussian surfels aligns more closely with the physical reality of the road. Distinct from previous initialization methods that rely on point clouds for Gaussian spheres, we introduce a trajectory-based initialization for Gaussian surfels. Thanks to the explicit representation of the Gaussian surfels and a good initialization, our method achieves a significant acceleration while improving reconstruction quality. We achieve excellent results in reconstruction of roads surfaces in a variety of challenging real-world scenes.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4ec82687-3f42-4146-b35a-533110de7d7d)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.14342) | [⌨️ Code] | [🌐 Project Page]





#### <summary>Gaussian Time Machine: A Real-Time Rendering Methodology for Time-Variant Appearances
Authors: Licheng Shen, Ho Ngai Chow, Lingyun Wang, Tong Zhang, Mengqiu Wang, Yuxing Han
<details span>
<summary><b>Abstract</b></summary>
Recent advancements in neural rendering techniques have significantly enhanced the fidelity of 3D reconstruction. Notably, the emergence of 3D Gaussian Splatting (3DGS) has marked a significant milestone by adopting a discrete scene representation, facilitating efficient training and real-time rendering. Several studies have successfully extended the real-time rendering capability of 3DGS to dynamic scenes. However, a challenge arises when training images are captured under vastly differing weather and lighting conditions. This scenario poses a challenge for 3DGS and its variants in achieving accurate reconstructions. Although NeRF-based methods (NeRF-W, CLNeRF) have shown promise in handling such challenging conditions, their computational demands hinder real-time rendering capabilities. In this paper, we present Gaussian Time Machine (GTM) which models the time-dependent attributes of Gaussian primitives with discrete time embedding vectors decoded by a lightweight Multi-Layer-Perceptron(MLP). By adjusting the opacity of Gaussian primitives, we can reconstruct visibility changes of objects. We further propose a decomposed color model for improved geometric consistency. GTM achieved state-of-the-art rendering fidelity on 3 datasets and is 100 times faster than NeRF-based counterparts in rendering. Moreover, GTM successfully disentangles the appearance changes and renders smooth appearance interpolation.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9eaa762d-48bf-4d2d-b208-20ddded9a3b3)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.13694) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Feature Splatting for Better Novel View Synthesis with Low Overlap
Authors: T. Berriel Martins, Javier Civera
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting has emerged as a very promising scene representation, achieving state-of-the-art quality in novel view synthesis significantly faster than competing alternatives. However, its use of spherical harmonics to represent scene colors limits the expressivity of 3D Gaussians and, as a consequence, the capability of the representation to generalize as we move away from the training views. In this paper, we propose to encode the color information of 3D Gaussians into per-Gaussian feature vectors, which we denote as Feature Splatting (FeatSplat). To synthesize a novel view, Gaussians are first "splatted" into the image plane, then the corresponding feature vectors are alpha-blended, and finally the blended vector is decoded by a small MLP to render the RGB pixel values. To further inform the model, we concatenate a camera embedding to the blended feature vector, to condition the decoding also on the viewpoint information. Our experiments show that these novel model for encoding the radiance considerably improves novel view synthesis for low overlap views that are distant from the training views. Finally, we also show the capacity and convenience of our feature vector representation, demonstrating its capability not only to generate RGB values for novel views, but also their per-pixel semantic labels. We will release the code upon acceptance.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e6a694f0-bb51-45c7-8e89-ac7d71dcd2d6)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.15518) | [⌨️ Code] | [🌐 Project Page]


#### <summary>GSDeformer: Direct Cage-based Deformation for 3D Gaussian Splatting
Authors: Jiajun Huang, Hongchuan Yu
<details span>
<summary><b>Abstract</b></summary>
We present GSDeformer, a method that achieves free-form deformation on 3D Gaussian Splatting(3DGS) without requiring any architectural changes. Our method extends cage-based deformation, a traditional mesh deformation method, to 3DGS. This is done by converting 3DGS into a novel proxy point cloud representation, where its deformation can be used to infer the transformations to apply on the 3D gaussians making up 3DGS. We also propose an automatic cage construction algorithm for 3DGS to minimize manual work. Our method does not modify the underlying architecture of 3DGS. Therefore, any existing trained vanilla 3DGS can be easily edited by our method. We compare the deformation capability of our method against other existing methods, demonstrating the ease of use and comparable quality of our method, despite being more direct and thus easier to integrate with other concurrent developments on 3DGS.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/dab08d8a-d7ba-4443-996c-3a6f55d1672d)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.15491) | [⌨️ Code] | [🌐 Project Page](https://jhuangbu.github.io/gsdeformer/)


#### <summary>DisC-GS: Discontinuity-aware Gaussian Splatting
Authors: Haoxuan Qu, Zhuoling Li, Hossein Rahmani, Yujun Cai, Jun Liu
<details span>
<summary><b>Abstract</b></summary>
Recently, Gaussian Splatting, a method that represents a 3D scene as a collection of Gaussian distributions, has gained significant attention in addressing the task of novel view synthesis. In this paper, we highlight a fundamental limitation of Gaussian Splatting: its inability to accurately render discontinuities and boundaries in images due to the continuous nature of Gaussian distributions. To address this issue, we propose a novel framework enabling Gaussian Splatting to perform discontinuity-aware image rendering. Additionally, we introduce a Bézier-boundary gradient approximation strategy within our framework to keep the ``differentiability'' of the proposed discontinuity-aware rendering process. Extensive experiments demonstrate the efficacy of our framework.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/2b0f2624-d8f6-4741-b198-d8937491b686)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.15196) | [⌨️ Code] | [🌐 Project Page]


#### <summary>GS-Hider: Hiding Messages into 3D Gaussian Splatting
Authors: Xuanyu Zhang, Jiarui Meng, Runyi Li, Zhipei Xu, Yongbing Zhang, Jian Zhang
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has already become the emerging research focus in the fields of 3D scene reconstruction and novel view synthesis. Given that training a 3DGS requires a significant amount of time and computational cost, it is crucial to protect the copyright, integrity, and privacy of such 3D assets. Steganography, as a crucial technique for encrypted transmission and copyright protection, has been extensively studied. However, it still lacks profound exploration targeted at 3DGS. Unlike its predecessor NeRF, 3DGS possesses two distinct features: 1) explicit 3D representation; and 2) real-time rendering speeds. These characteristics result in the 3DGS point cloud files being public and transparent, with each Gaussian point having a clear physical significance. Therefore, ensuring the security and fidelity of the original 3D scene while embedding information into the 3DGS point cloud files is an extremely challenging task. To solve the above-mentioned issue, we first propose a steganography framework for 3DGS, dubbed GS-Hider, which can embed 3D scenes and images into original GS point clouds in an invisible manner and accurately extract the hidden messages. Specifically, we design a coupled secured feature attribute to replace the original 3DGS's spherical harmonics coefficients and then use a scene decoder and a message decoder to disentangle the original RGB scene and the hidden message. Extensive experiments demonstrated that the proposed GS-Hider can effectively conceal multimodal messages without compromising rendering quality and possesses exceptional security, robustness, capacity, and flexibility.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/89e79416-e05a-414a-b62c-80fa30fe7702)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.15118) | [⌨️ Code] | [🌐 Project Page](https://xuanyuzhang21.github.io/project/gshider/)


#### <summary>Neural Directional Encoding for Efficient and Accurate View-Dependent Appearance Modeling
Authors: Liwen Wu, Sai Bi, Zexiang Xu, Fujun Luan, Kai Zhang, Iliyan Georgiev, Kalyan Sunkavalli, Ravi Ramamoorthi
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has already become the emerging research focus in the fields of 3D scene reconstruction and novel view synthesis. Given that training a 3DGS requires a significant amount of time and computational cost, it is crucial to protect the copyright, integrity, and privacy of such 3D assets. Steganography, as a crucial technique for encrypted transmission and copyright protection, has been extensively studied. However, it still lacks profound exploration targeted at 3DGS. Unlike its predecessor NeRF, 3DGS possesses two distinct features: 1) explicit 3D representation; and 2) real-time rendering speeds. These characteristics result in the 3DGS point cloud files being public and transparent, with each Gaussian point having a clear physical significance. Therefore, ensuring the security and fidelity of the original 3D scene while embedding information into the 3DGS point cloud files is an extremely challenging task. To solve the above-mentioned issue, we first propose a steganography framework for 3DGS, dubbed GS-Hider, which can embed 3D scenes and images into original GS point clouds in an invisible manner and accurately extract the hidden messages. Specifically, we design a coupled secured feature attribute to replace the original 3DGS's spherical harmonics coefficients and then use a scene decoder and a message decoder to disentangle the original RGB scene and the hidden message. Extensive experiments demonstrated that the proposed GS-Hider can effectively conceal multimodal messages without compromising rendering quality and possesses exceptional security, robustness, capacity, and flexibility.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/c217d630-4080-43e3-bc91-418d0ee8fcab)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.14847) | [⌨️ Code](https://github.com/lwwu2/nde) | [🌐 Project Page](https://lwwu2.github.io/nde/)


#### <summary>GaussianFormer: Scene as Gaussians for Vision-Based 3D Semantic Occupancy Prediction
Authors: Yuanhui Huang, Wenzhao Zheng, Yunpeng Zhang, Jie Zhou, Jiwen Lu
<details span>
<summary><b>Abstract</b></summary>
3D semantic occupancy prediction aims to obtain 3D fine-grained geometry and semantics of the surrounding scene and is an important task for the robustness of vision-centric autonomous driving. Most existing methods employ dense grids such as voxels as scene representations, which ignore the sparsity of occupancy and the diversity of object scales and thus lead to unbalanced allocation of resources. To address this, we propose an object-centric representation to describe 3D scenes with sparse 3D semantic Gaussians where each Gaussian represents a flexible region of interest and its semantic features. We aggregate information from images through the attention mechanism and iteratively refine the properties of 3D Gaussians including position, covariance, and semantics. We then propose an efficient Gaussian-to-voxel splatting method to generate 3D occupancy predictions, which only aggregates the neighboring Gaussians for a certain position. We conduct extensive experiments on the widely adopted nuScenes and KITTI-360 datasets. Experimental results demonstrate that GaussianFormer achieves comparable performance with state-of-the-art methods with only 17.8% - 24.8% of their memory consumption.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/c217d630-4080-43e3-bc91-418d0ee8fcab)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17429) | [⌨️ Code] | [🌐 Project Page](https://wzzheng.net/GaussianFormer/)

#### <summary>MoSca: Dynamic Gaussian Fusion from Casual Videos via 4D Motion Scaffolds
Authors: Jiahui Lei, Yijia Weng, Adam Harley, Leonidas Guibas, Kostas Daniilidis
<details span>
<summary><b>Abstract</b></summary>
We introduce 4D Motion Scaffolds (MoSca), a neural information processing system designed to reconstruct and synthesize novel views of dynamic scenes from monocular videos captured casually in the wild. To address such a challenging and ill-posed inverse problem, we leverage prior knowledge from foundational vision models, lift the video data to a novel Motion Scaffold (MoSca) representation, which compactly and smoothly encodes the underlying motions / deformations. The scene geometry and appearance are then disentangled from the deformation field, and are encoded by globally fusing the Gaussians anchored onto the MoSca and optimized via Gaussian Splatting. Additionally, camera poses can be seamlessly initialized and refined during the dynamic rendering process, without the need for other pose estimation tools. Experiments demonstrate state-of-the-art performance on dynamic rendering benchmarks.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4e3073cc-469a-4d6a-b4f0-99c126bb8dce)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17421) | [⌨️ Code] | [🌐 Project Page](https://www.cis.upenn.edu/~leijh/projects/mosca/)

#### <summary>DOF-GS: Adjustable Depth-of-Field 3D Gaussian Splatting for Refocusing, Defocus Rendering and Blur Removal
Authors: Yujie Wang, Praneeth Chakravarthula, Baoquan Chen
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting-based techniques have recently advanced 3D scene reconstruction and novel view synthesis, achieving high-quality real-time rendering. However, these approaches are inherently limited by the underlying pinhole camera assumption in modeling the images and hence only work for All-in-Focus (AiF) sharp image inputs. This severely affects their applicability in real-world scenarios where images often exhibit defocus blur due to the limited depth-of-field (DOF) of imaging devices. Additionally, existing 3D Gaussian Splatting (3DGS) methods also do not support rendering of DOF effects.
To address these challenges, we introduce DOF-GS that allows for rendering adjustable DOF effects, removing defocus blur as well as refocusing of 3D scenes, all from multi-view images degraded by defocus blur. To this end, we re-imagine the traditional Gaussian Splatting pipeline by employing a finite aperture camera model coupled with explicit, differentiable defocus rendering guided by the Circle-of-Confusion (CoC). The proposed framework provides for dynamic adjustment of DOF effects by changing the aperture and focal distance of the underlying camera model on-demand. It also enables rendering varying DOF effects of 3D scenes post-optimization, and generating AiF images from defocused training images. Furthermore, we devise a joint optimization strategy to further enhance details in the reconstructed scenes by jointly optimizing rendered defocused and AiF images. Our experimental results indicate that DOF-GS produces high-quality sharp all-in-focus renderings conditioned on inputs compromised by defocus blur, with the training process incurring only a modest increase in GPU memory consumption. We further demonstrate the applications of the proposed method for adjustable defocus rendering and refocusing of the 3D scene from input images degraded by defocus blur.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0b30e9ac-eabf-4d07-b138-4cfb5f83666a)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17351) | [⌨️ Code] | [🌐 Project Page]


#### <summary>F-3DGS: Factorized Coordinates and Representations for 3D Gaussian Splatting
Authors: Xiangyu Sun, Joo Chan Lee, Daniel Rho, Jong Hwan Ko, Usman Ali, Eunbyung Park
<details span>
<summary><b>Abstract</b></summary>
The neural radiance field (NeRF) has made significant strides in representing 3D scenes and synthesizing novel views. Despite its advancements, the high computational costs of NeRF have posed challenges for its deployment in resource-constrained environments and real-time applications. As an alternative to NeRF-like neural rendering methods, 3D Gaussian Splatting (3DGS) offers rapid rendering speeds while maintaining excellent image quality. However, as it represents objects and scenes using a myriad of Gaussians, it requires substantial storage to achieve high-quality representation. To mitigate the storage overhead, we propose Factorized 3D Gaussian Splatting (F-3DGS), a novel approach that drastically reduces storage requirements while preserving image quality. Inspired by classical matrix and tensor factorization techniques, our method represents and approximates dense clusters of Gaussians with significantly fewer Gaussians through efficient factorization. We aim to efficiently represent dense 3D Gaussians by approximating them with a limited amount of information for each axis and their combinations. This method allows us to encode a substantially large number of Gaussians along with their essential attributes -- such as color, scale, and rotation -- necessary for rendering using a relatively small number of elements. Extensive experimental results demonstrate that F-3DGS achieves a significant reduction in storage costs while maintaining comparable quality in rendered images.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e7e24118-a938-4eb1-b697-fd52926dd08a)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17083) | [⌨️ Code] | [🌐 Project Page]






#### <summary>3D StreetUnveiler with Semantic-Aware 2DGS
Authors: Jingwei Xu, Yikai Wang, Yiqun Zhao, Yanwei Fu, Shenghua Gao
<details span>
<summary><b>Abstract</b></summary>
Unveiling an empty street from crowded observations captured by in-car cameras is crucial for autonomous driving. However, removing all temporary static objects, such as stopped vehicles and standing pedestrians, presents a significant challenge. Unlike object-centric 3D inpainting, which relies on thorough observation in a small scene, street scenes involve long trajectories that differ from previous 3D inpainting tasks. The camera-centric moving environment of captured videos further complicates the task due to the limited degree and time duration of object observation. To address these obstacles, we introduce StreetUnveiler to reconstruct an empty street. StreetUnveiler learns a 3D representation of the empty street from crowded observations. Our representation is based on the hard-label semantic 2D Gaussian Splatting (2DGS) for its scalability and ability to identify Gaussians to be removed. We inpaint rendered image after removing unwanted Gaussians to provide pseudo-labels and subsequently re-optimize the 2DGS. Given its temporal continuous movement, we divide the empty street scene into observed, partial-observed, and unobserved regions, which we propose to locate through a rendered alpha map. This decomposition helps us to minimize the regions that need to be inpainted. To enhance the temporal consistency of the inpainting, we introduce a novel time-reversal framework to inpaint frames in reverse order and use later frames as references for earlier frames to fully utilize the long-trajectory observations. Our experiments conducted on the street scene dataset successfully reconstructed a 3D representation of the empty street. The mesh representation of the empty street can be extracted for further applications.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0dec50e5-4307-42f2-9b9e-60df2157d45c)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.18416) | [⌨️ Code](https://github.com/DavidXu-JJ/StreetUnveiler) | [🌐 Project Page](https://streetunveiler.github.io/)

#### <summary>RT-GS2: Real-Time Generalizable Semantic Segmentation for 3D Gaussian Representations of Radiance Fields
Authors: Mihnea-Bogdan Jurca, Remco Royen, Ion Giosan, Adrian Munteanu
<details span>
<summary><b>Abstract</b></summary>
Gaussian Splatting has revolutionized the world of novel view synthesis by achieving high rendering performance in real-time. Recently, studies have focused on enriching these 3D representations with semantic information for downstream tasks. In this paper, we introduce RT-GS2, the first generalizable semantic segmentation method employing Gaussian Splatting. While existing Gaussian Splatting-based approaches rely on scene-specific training, RT-GS2 demonstrates the ability to generalize to unseen scenes. Our method adopts a new approach by first extracting view-independent 3D Gaussian features in a self-supervised manner, followed by a novel View-Dependent / View-Independent (VDVI) feature fusion to enhance semantic consistency over different views. Extensive experimentation on three different datasets showcases RT-GS2's superiority over the state-of-the-art methods in semantic segmentation quality, exemplified by a 8.01% increase in mIoU on the Replica dataset. Moreover, our method achieves real-time performance of 27.03 FPS, marking an astonishing 901 times speedup compared to existing approaches. This work represents a significant advancement in the field by introducing, to the best of our knowledge, the first real-time generalizable semantic segmentation method for 3D Gaussian representations of radiance fields.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e3fe86c4-5f0b-4b6d-82f1-9fd85c97aa52)


</details>

[📃 arXiv:2405](https://export.arxiv.org/pdf/2405.18033) | [⌨️ Code] | [🌐 Project Page]


#### <summary>A Refined 3D Gaussian Representation for High-Quality Dynamic Scene Reconstruction
Authors: Bin Zhang, Bi Zeng, Zexin Peng
<details span>
<summary><b>Abstract</b></summary>
In recent years, Neural Radiance Fields (NeRF) has revolutionized three-dimensional (3D) reconstruction with its implicit representation. Building upon NeRF, 3D Gaussian Splatting (3D-GS) has departed from the implicit representation of neural networks and instead directly represents scenes as point clouds with Gaussian-shaped distributions. While this shift has notably elevated the rendering quality and speed of radiance fields but inevitably led to a significant increase in memory usage. Additionally, effectively rendering dynamic scenes in 3D-GS has emerged as a pressing challenge. To address these concerns, this paper purposes a refined 3D Gaussian representation for high-quality dynamic scene reconstruction. Firstly, we use a deformable multi-layer perceptron (MLP) network to capture the dynamic offset of Gaussian points and express the color features of points through hash encoding and a tiny MLP to reduce storage requirements. Subsequently, we introduce a learnable denoising mask coupled with denoising loss to eliminate noise points from the scene, thereby further compressing 3D Gaussian model. Finally, motion noise of points is mitigated through static constraints and motion consistency constraints. Experimental results demonstrate that our method surpasses existing approaches in rendering quality and speed, while significantly reducing the memory usage associated with 3D-GS, making it highly suitable for various tasks such as novel view synthesis, and dynamic mapping.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/18024421-4ee6-47d0-b37b-07a5d2bf3a00)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17891) | [⌨️ Code] | [🌐 Project Page]


#### <summary>SafeguardGS: 3D Gaussian Primitive Pruning While Avoiding Catastrophic Scene Destruction
Authors: Yongjae Lee, Zhaoliang Zhang, Deliang Fan
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has made a significant stride in novel view synthesis, demonstrating top-notch rendering quality while achieving real-time rendering speed. However, the excessively large number of Gaussian primitives resulting from 3DGS' suboptimal densification process poses a major challenge, slowing down frame-per-second (FPS) and demanding considerable memory cost, making it unfavorable for low-end devices. To cope with this issue, many follow-up studies have suggested various pruning techniques, often in combination with different score functions, to optimize rendering performance. Nonetheless, a comprehensive discussion regarding their effectiveness and implications across all techniques is missing. In this paper, we first categorize 3DGS pruning techniques into two types: Cross-view pruning and pixel-wise pruning, which differ in their approaches to rank primitives. Our subsequent experiments reveal that while cross-view pruning leads to disastrous quality drops under extreme Gaussian primitives decimation, the pixel-wise pruning technique not only sustains relatively high rendering quality with minuscule performance degradation but also provides a reasonable minimum boundary for pruning. Building on this observation, we further propose multiple variations of score functions and empirically discover that the color-weighted score function outperforms others for discriminating insignificant primitives for rendering. We believe our research provides valuable insights for optimizing 3DGS pruning strategies for future works.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a3b84696-75d4-4c67-a780-b2b03decd532)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17793) | [⌨️ Code] | [🌐 Project Page]



#### <summary>DC-Gaussian: Improving 3D Gaussian Splatting for Reflective Dash Cam Videos
Authors: Linhan Wang, Kai Cheng, Shuo Lei, Shengkun Wang, Wei Yin, Chenyang Lei, Xiaoxiao Long, Chang-Tien Lu
<details span>
<summary><b>Abstract</b></summary>
We present DC-Gaussian, a new method for generating novel views from in-vehicle dash cam videos. While neural rendering techniques have made significant strides in driving scenarios, existing methods are primarily designed for videos collected by autonomous vehicles. However, these videos are limited in both quantity and diversity compared to dash cam videos, which are more widely used across various types of vehicles and capture a broader range of scenarios. Dash cam videos often suffer from severe obstructions such as reflections and occlusions on the windshields, which significantly impede the application of neural rendering techniques. To address this challenge, we develop DC-Gaussian based on the recent real-time neural rendering technique 3D Gaussian Splatting (3DGS). Our approach includes an adaptive image decomposition module to model reflections and occlusions in a unified manner. Additionally, we introduce illumination-aware obstruction modeling to manage reflections and occlusions under varying lighting conditions. Lastly, we employ a geometry-guided Gaussian enhancement strategy to improve rendering details by incorporating additional geometry priors. Experiments on self-captured and public dash cam videos show that our method not only achieves state-of-the-art performance in novel view synthesis, but also accurately reconstructing captured scenes getting rid of obstructions.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/bfe756fb-bc69-4e02-87b1-bde4c69e745a)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17705) | [⌨️ Code](https://github.com/linhanwang/DC-Gaussian) | [🌐 Project Page](https://linhanwang.github.io/dcgaussian/)


#### <summary>Mani-GS: Gaussian Splatting Manipulation with Triangular Mesh
Authors: Xiangjun Gao, Xiaoyu Li, Yiyu Zhuang, Qi Zhang, Wenbo Hu, Chaopeng Zhang, Yao Yao, Ying Shan, Long Quan
<details span>
<summary><b>Abstract</b></summary>
Neural 3D representations such as Neural Radiance Fields (NeRF), excel at producing photo-realistic rendering results but lack the flexibility for manipulation and editing which is crucial for content creation. Previous works have attempted to address this issue by deforming a NeRF in canonical space or manipulating the radiance field based on an explicit mesh. However, manipulating NeRF is not highly controllable and requires a long training and inference time. With the emergence of 3D Gaussian Splatting (3DGS), extremely high-fidelity novel view synthesis can be achieved using an explicit point-based 3D representation with much faster training and rendering speed. However, there is still a lack of effective means to manipulate 3DGS freely while maintaining rendering quality. In this work, we aim to tackle the challenge of achieving manipulable photo-realistic rendering. We propose to utilize a triangular mesh to manipulate 3DGS directly with self-adaptation. This approach reduces the need to design various algorithms for different types of Gaussian manipulation. By utilizing a triangle shape-aware Gaussian binding and adapting method, we can achieve 3DGS manipulation and preserve high-fidelity rendering after manipulation. Our approach is capable of handling large deformations, local manipulations, and soft body simulations while keeping high-quality rendering. Furthermore, we demonstrate that our method is also effective with inaccurate meshes extracted from 3DGS. Experiments conducted demonstrate the effectiveness of our method and its superiority over baseline approaches.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/6b776e2e-1ed4-4eae-8345-bf1425fc06da)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17811) | [⌨️ Code](https://github.com/gaoxiangjun/Mani-GS) | [🌐 Project Page](https://gaoxiangjun.github.io/mani_gs/)

#### <summary>DGD: Dynamic 3D Gaussians Distillation
Authors: Isaac Labe, Noam Issachar, Itai Lang, Sagie Benaim
<details span>
<summary><b>Abstract</b></summary>
We tackle the task of learning dynamic 3D semantic radiance fields given a single monocular video as input. Our learned semantic radiance field captures per-point semantics as well as color and geometric properties for a dynamic 3D scene, enabling the generation of novel views and their corresponding semantics. This enables the segmentation and tracking of a diverse set of 3D semantic entities, specified using a simple and intuitive interface that includes a user click or a text prompt. To this end, we present DGD, a unified 3D representation for both the appearance and semantics of a dynamic 3D scene, building upon the recently proposed dynamic 3D Gaussians representation. Our representation is optimized over time with both color and semantic information. Key to our method is the joint optimization of the appearance and semantic attributes, which jointly affect the geometric properties of the scene. We evaluate our approach in its ability to enable dense semantic 3D object tracking and demonstrate high-quality results that are fast to render, for a diverse set of scenes.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/958228dc-b761-4172-998c-dde812fd7912)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.19321) | [⌨️ Code](https://github.com/Isaaclabe/DGD-Dynamic-3D-Gaussians-Distillation) | [🌐 Project Page](https://isaaclabe.github.io/DGD-Website/)




#### <summary>LP-3DGS: Learning to Prune 3D Gaussian Splatting
Authors: Zhaoliang Zhang, Tianchen Song, Yongjae Lee, Li Yang, Cheng Peng, Rama Chellappa, Deliang Fan
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has become one of the mainstream methodologies for novel view synthesis (NVS) due to its high quality and fast rendering speed. However, as a point-based scene representation, 3DGS potentially generates a large number of Gaussians to fit the scene, leading to high memory usage. Improvements that have been proposed require either an empirical and preset pruning ratio or importance score threshold to prune the point cloud. Such hyperparamter requires multiple rounds of training to optimize and achieve the maximum pruning ratio, while maintaining the rendering quality for each scene. In this work, we propose learning-to-prune 3DGS (LP-3DGS), where a trainable binary mask is applied to the importance score that can find optimal pruning ratio automatically. Instead of using the traditional straight-through estimator (STE) method to approximate the binary mask gradient, we redesign the masking function to leverage the Gumbel-Sigmoid method, making it differentiable and compatible with the existing training process of 3DGS. Extensive experiments have shown that LP-3DGS consistently produces a good balance that is both efficient and high quality.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/bc7f074e-7dd4-4abb-95dc-53fafad5d6af)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.18784) | [⌨️ Code] | [🌐 Project Page]





#### <summary>A Pixel Is Worth More Than One 3D Gaussians in Single-View 3D Reconstruction
Authors: Jianghao Shen, Xue Nan, Tianfu Wu
<details span>
<summary><b>Abstract</b></summary>
Learning 3D scene representation from a single-view image is a long-standing fundamental problem in computer vision, with the inherent ambiguity in predicting contents unseen from the input view. Built on the recently proposed 3D Gaussian Splatting (3DGS), the Splatter Image method has made promising progress on fast single-image novel view synthesis via learning a single 3D Gaussian for each pixel based on the U-Net feature map of an input image. However, it has limited expressive power to represent occluded components that are not observable in the input view. To address this problem, this paper presents a Hierarchical Splatter Image method in which a pixel is worth more than one 3D Gaussians. Specifically, each pixel is represented by a parent 3D Gaussian and a small number of child 3D Gaussians. Parent 3D Gaussians are learned as done in the vanilla Splatter Image. Child 3D Gaussians are learned via a lightweight Multi-Layer Perceptron (MLP) which takes as input the projected image features of a parent 3D Gaussian and the embedding of a target camera view. Both parent and child 3D Gaussians are learned end-to-end in a stage-wise way. The joint condition of input image features from eyes of the parent Gaussians and the target camera position facilitates learning to allocate child Gaussians to ``see the unseen'', recovering the occluded details that are often missed by parent Gaussians.
In experiments, the proposed method is tested on the ShapeNet-SRN and CO3D datasets with state-of-the-art performance obtained, especially showing promising capabilities of reconstructing occluded contents in the input view.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0efd709d-4fe7-4594-a049-386281612742)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20310) | [⌨️ Code] | [🌐 Project Page]



#### <summary>GaussianPrediction: Dynamic 3D Gaussian Prediction for Motion Extrapolation and Free View Synthesis
Authors: Boming Zhao, Yuan Li, Ziyu Sun, Lin Zeng, Yujun Shen, Rui Ma, Yinda Zhang, Hujun Bao, Zhaopeng Cui
<details span>
<summary><b>Abstract</b></summary>
Forecasting future scenarios in dynamic environments is essential for intelligent decision-making and navigation, a challenge yet to be fully realized in computer vision and robotics. Traditional approaches like video prediction and novel-view synthesis either lack the ability to forecast from arbitrary viewpoints or to predict temporal dynamics. In this paper, we introduce GaussianPrediction, a novel framework that empowers 3D Gaussian representations with dynamic scene modeling and future scenario synthesis in dynamic environments. GaussianPrediction can forecast future states from any viewpoint, using video observations of dynamic scenes. To this end, we first propose a 3D Gaussian canonical space with deformation modeling to capture the appearance and geometry of dynamic scenes, and integrate the lifecycle property into Gaussians for irreversible deformations. To make the prediction feasible and efficient, a concentric motion distillation approach is developed by distilling the scene motion with key points. Finally, a Graph Convolutional Network is employed to predict the motions of key points, enabling the rendering of photorealistic images of future scenarios. Our framework shows outstanding performance on both synthetic and real-world datasets, demonstrating its efficacy in predicting and rendering future environments.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/424b3998-ce1f-46e5-80d4-c1a3338ff5e2)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.19745) | [⌨️ Code] | [🌐 Project Page]






#### <summary>Neural Gaussian Scale-Space Fields
Authors: Felix Mujkanovic, Ntumba Elie Nsampi, Christian Theobalt, Hans-Peter Seidel, Thomas Leimkühler
<details span>
<summary><b>Abstract</b></summary>
Gaussian scale spaces are a cornerstone of signal representation and processing, with applications in filtering, multiscale analysis, anti-aliasing, and many more. However, obtaining such a scale space is costly and cumbersome, in particular for continuous representations such as neural fields. We present an efficient and lightweight method to learn the fully continuous, anisotropic Gaussian scale space of an arbitrary signal. Based on Fourier feature modulation and Lipschitz bounding, our approach is trained self-supervised, i.e., training does not require any manual filtering. Our neural Gaussian scale-space fields faithfully capture multiscale representations across a broad range of modalities, and support a diverse set of applications. These include images, geometry, light-stage data, texture anti-aliasing, and multiscale optimization.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/792da5e6-d8dd-40c0-8a81-023d18962d6a)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20980) | [⌨️ Code](https://github.com/LoadingByte/neural-gaussian-scale-space-fields) | [🌐 Project Page](https://neural-gaussian-scale-space-fields.mpi-inf.mpg.de/)



#### <summary>R2-Gaussian: Rectifying Radiative Gaussian Splatting for Tomographic Reconstruction
Authors: Ruyi Zha, Tao Jun Lin, Yuanhao Cai, Jiwen Cao, Yanhao Zhang, Hongdong Li
<details span>
<summary><b>Abstract</b></summary>
Gaussian scale spaces are a cornerstone of signal representation and processing, with applications in filtering, multiscale analysis, anti-aliasing, and many more. However, obtaining such a scale space is costly and cumbersome, in particular for continuous representations such as neural fields. We present an efficient and lightweight method to learn the fully continuous, anisotropic Gaussian scale space of an arbitrary signal. Based on Fourier feature modulation and Lipschitz bounding, our approach is trained self-supervised, i.e., training does not require any manual filtering. Our neural Gaussian scale-space fields faithfully capture multiscale representations across a broad range of modalities, and support a diverse set of applications. These include images, geometry, light-stage data, texture anti-aliasing, and multiscale optimization.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e430065b-d5cc-44c7-bf10-01ddf09a41b0)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20693) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Don't Splat your Gaussians: Volumetric Ray-Traced Primitives for Modeling and Rendering Scattering and Emissive Media
Authors: Jorge Condor, Sebastien Speierer, Lukas Bode, Aljaz Bozic, Simon Green, Piotr Didyk, Adrian Jarabo
<details span>
<summary><b>Abstract</b></summary>
Efficient scene representations are essential for many computer graphics applications. A general unified representation that can handle both surfaces and volumes simultaneously, remains a research challenge. Inspired by recent methods for scene reconstruction that leverage mixtures of 3D Gaussians to model radiance fields, we formalize and generalize the modeling of scattering and emissive media using mixtures of simple kernel-based volumetric primitives. We introduce closed-form solutions for transmittance and free-flight distance sampling for different kernels, and propose several optimizations to use our method efficiently within any off-the-shelf volumetric path tracer. We demonstrate our method as a compact and efficient alternative to other forms of volume modeling for forward and inverse rendering of scattering media. Furthermore, we adapt and showcase our method in radiance field optimization and rendering, providing additional flexibility compared to current state of the art given its ray-tracing formulation. We also introduce the Epanechnikov kernel and demonstrate its potential as an efficient alternative to the traditionally-used Gaussian kernel in scene reconstruction tasks. The versatility and physically-based nature of our approach allows us to go beyond radiance fields and bring to kernel-based modeling and rendering any path-tracing enabled functionality such as scattering, relighting and complex camera models.
 
![image](https://github.com/user-attachments/assets/028a708f-805c-4cbb-861c-b14a44523aa8)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.15425) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Tetrahedron Splatting for 3D Generation
Authors: Chun Gu, Zeyu Yang, Zijie Pan, Xiatian Zhu, Li Zhang
<details span>
<summary><b>Abstract</b></summary>
3D representation is essential to the significant advance of 3D generation with 2D diffusion priors. As a flexible representation, NeRF has been first adopted for 3D representation. With density-based volumetric rendering, it however suffers both intensive computational overhead and inaccurate mesh extraction. Using a signed distance field and Marching Tetrahedra, DMTet allows for precise mesh extraction and real-time rendering but is limited in handling large topological changes in meshes, leading to optimization challenges. Alternatively, 3D Gaussian Splatting (3DGS) is favored in both training and rendering efficiency while falling short in mesh extraction. In this work, we introduce a novel 3D representation, Tetrahedron Splatting (TeT-Splatting), that supports easy convergence during optimization, precise mesh extraction, and real-time rendering simultaneously. This is achieved by integrating surface-based volumetric rendering within a structured tetrahedral grid while preserving the desired ability of precise mesh extraction, and a tile-based differentiable tetrahedron rasterizer. Furthermore, we incorporate eikonal and normal consistency regularization terms for the signed distance field to improve generation quality and stability. Critically, our representation can be trained without mesh extraction, making the optimization process easier to converge. Our TeT-Splatting can be readily integrated in existing 3D generation pipelines, along with polygonal mesh for texture optimization. Extensive experiments show that our TeT-Splatting strikes a superior tradeoff among convergence speed, render efficiency, and mesh quality as compared to previous alternatives under varying 3D generation settings.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e8ae569d-9242-47e4-ba2c-b6184fe6ef69)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.01579) | [⌨️ Code](https://github.com/fudan-zvg/tet-splatting) | [🌐 Project Page]



#### <summary>SuperGaussian: Repurposing Video Models for 3D Super Resolution
Authors: Yuan Shen, Duygu Ceylan, Paul Guerrero, Zexiang Xu, Niloy J. Mitra, Shenlong Wang, Anna Früstück
<details span>
<summary><b>Abstract</b></summary>
We present a simple, modular, and generic method that upsamples coarse 3D models by adding geometric and appearance details. While generative 3D models now exist, they do not yet match the quality of their counterparts in image and video domains. We demonstrate that it is possible to directly repurpose existing (pretrained) video models for 3D super-resolution and thus sidestep the problem of the shortage of large repositories of high-quality 3D training models. We describe how to repurpose video upsampling models, which are not 3D consistent, and combine them with 3D consolidation to produce 3D-consistent results. As output, we produce high quality Gaussian Splat models, which are object centric and effective. Our method is category agnostic and can be easily incorporated into existing 3D workflows. We evaluate our proposed SuperGaussian on a variety of 3D inputs, which are diverse both in terms of complexity and representation (e.g., Gaussian Splats or NeRFs), and demonstrate that our simple method significantly improves the fidelity of the final 3D models.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/25c557de-1883-4fd9-b760-b1f600c0be90)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.00609) | [⌨️ Code] | [🌐 Project Page](https://supergaussian.github.io/)



#### <summary>MoDGS: Dynamic Gaussian Splatting from Causually-captured Monocular Videos
Authors: Qingming Liu, Yuan Liu, Jiepeng Wang, Xianqiang Lv, Peng Wang, Wenping Wang, Junhui Hou
<details span>
<summary><b>Abstract</b></summary>
In this paper, we propose MoDGS, a new pipeline to render novel-view images in dynamic scenes using only casually captured monocular videos. Previous monocular dynamic NeRF or Gaussian Splatting methods strongly rely on the rapid movement of input cameras to construct multiview consistency but fail to reconstruct dynamic scenes on casually captured input videos whose cameras are static or move slowly. To address this challenging task, MoDGS adopts recent single-view depth estimation methods to guide the learning of the dynamic scene. Then, a novel 3D-aware initialization method is proposed to learn a reasonable deformation field and a new robust depth loss is proposed to guide the learning of dynamic scene geometry. Comprehensive experiments demonstrate that MoDGS is able to render high-quality novel view images of dynamic scenes from just a casually captured monocular video, which outperforms baseline methods by a significant margin.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/69188581-68ff-4ffe-ab5c-62e35a7a3713)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.00434) | [⌨️ Code] | [🌐 Project Page](https://modgs.github.io/)




#### <summary>Enhancing Temporal Consistency in Video Editing by Reconstructing Videos with 3D Gaussian Splatting
Authors: Inkyu Shin, Qihang Yu, Xiaohui Shen, In So Kweon, Kuk-Jin Yoon, Liang-Chieh Chen
<details span>
<summary><b>Abstract</b></summary>
Recent advancements in zero-shot video diffusion models have shown promise for text-driven video editing, but challenges remain in achieving high temporal consistency. To address this, we introduce Video-3DGS, a 3D Gaussian Splatting (3DGS)-based video refiner designed to enhance temporal consistency in zero-shot video editors. Our approach utilizes a two-stage 3D Gaussian optimizing process tailored for editing dynamic monocular videos. In the first stage, Video-3DGS employs an improved version of COLMAP, referred to as MC-COLMAP, which processes original videos using a Masked and Clipped approach. For each video clip, MC-COLMAP generates the point clouds for dynamic foreground objects and complex backgrounds. These point clouds are utilized to initialize two sets of 3D Gaussians (Frg-3DGS and Bkg-3DGS) aiming to represent foreground and background views. Both foreground and background views are then merged with a 2D learnable parameter map to reconstruct full views. In the second stage, we leverage the reconstruction ability developed in the first stage to impose the temporal constraints on the video diffusion model. To demonstrate the efficacy of Video-3DGS on both stages, we conduct extensive experiments across two related tasks: Video Reconstruction and Video Editing. Video-3DGS trained with 3k iterations significantly improves video reconstruction quality (+3 PSNR, +7 PSNR increase) and training efficiency (x1.9, x4.5 times faster) over NeRF-based and 3DGS-based state-of-art methods on DAVIS dataset, respectively. Moreover, it enhances video editing by ensuring temporal consistency across 58 dynamic monocular videos.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/80510b95-071d-4cb8-b845-4ae10275e700)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02541) | [⌨️ Code] | [🌐 Project Page](https://video-3dgs-project.github.io/)



#### <summary>WE-GS: An In-the-wild Efficient 3D Gaussian Representation for Unconstrained Photo Collections
Authors: Yuze Wang, Junyi Wang, Yue Qi
<details span>
<summary><b>Abstract</b></summary>
Novel View Synthesis (NVS) from unconstrained photo collections is challenging in computer graphics. Recently, 3D Gaussian Splatting (3DGS) has shown promise for photorealistic and real-time NVS of static scenes. Building on 3DGS, we propose an efficient point-based differentiable rendering framework for scene reconstruction from photo collections. Our key innovation is a residual-based spherical harmonic coefficients transfer module that adapts 3DGS to varying lighting conditions and photometric post-processing. This lightweight module can be pre-computed and ensures efficient gradient propagation from rendered images to 3D Gaussian attributes. Additionally, we observe that the appearance encoder and the transient mask predictor, the two most critical parts of NVS from unconstrained photo collections, can be mutually beneficial. We introduce a plug-and-play lightweight spatial attention module to simultaneously predict transient occluders and latent appearance representation for each image. After training and preprocessing, our method aligns with the standard 3DGS format and rendering pipeline, facilitating seamlessly integration into various 3DGS applications. Extensive experiments on diverse datasets show our approach outperforms existing approaches on the rendering quality of novel view and appearance synthesis with high converge and rendering speed.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4c6ef8c7-ddab-4da9-a3ee-816267af4d76)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02407) | [⌨️ Code] | [🌐 Project Page](https://yuzewang1998.github.io/we-gs.github.io/)


#### <summary>OpenGaussian: Towards Point-Level 3D Gaussian-based Open Vocabulary Understanding
Authors: Yanmin Wu, Jiarui Meng, Haijie Li, Chenming Wu, Yahao Shi, Xinhua Cheng, Chen Zhao, Haocheng Feng, Errui Ding, Jingdong Wang, Jian Zhang
<details span>
<summary><b>Abstract</b></summary>
This paper introduces OpenGaussian, a method based on 3D Gaussian Splatting (3DGS) capable of 3D point-level open vocabulary understanding. Our primary motivation stems from observing that existing 3DGS-based open vocabulary methods mainly focus on 2D pixel-level parsing. These methods struggle with 3D point-level tasks due to weak feature expressiveness and inaccurate 2D-3D feature associations. To ensure robust feature presentation and 3D point-level understanding, we first employ SAM masks without cross-frame associations to train instance features with 3D consistency. These features exhibit both intra-object consistency and inter-object distinction. Then, we propose a two-stage codebook to discretize these features from coarse to fine levels. At the coarse level, we consider the positional information of 3D points to achieve location-based clustering, which is then refined at the fine level. Finally, we introduce an instance-level 3D-2D feature association method that links 3D points to 2D masks, which are further associated with 2D CLIP features. Extensive experiments, including open vocabulary-based 3D object selection, 3D point cloud understanding, click-based 3D object selection, and ablation studies, demonstrate the effectiveness of our proposed method.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/6a25a8b4-78ca-4277-a2ae-05c01b03fcde)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02058) | [⌨️ Code] | [🌐 Project Page](https://3d-aigc.github.io/OpenGaussian/)

#### <summary>FastLGS: Speeding up Language Embedded Gaussians with Feature Grid Mapping
Authors: Yuzhou Ji, He Zhu, Junshu Tang, Wuyi Liu, Zhizhong Zhang, Yuan Xie, Lizhuang Ma, Xin Tan
<details span>
<summary><b>Abstract</b></summary>
The semantically interactive radiance field has always been an appealing task for its potential to facilitate user-friendly and automated real-world 3D scene understanding applications. However, it is a challenging task to achieve high quality, efficiency and zero-shot ability at the same time with semantics in radiance fields. In this work, we present FastLGS, an approach that supports real-time open-vocabulary query within 3D Gaussian Splatting (3DGS) under high resolution. We propose the semantic feature grid to save multi-view CLIP features which are extracted based on Segment Anything Model (SAM) masks, and map the grids to low dimensional features for semantic field training through 3DGS. Once trained, we can restore pixel-aligned CLIP embeddings through feature grids from rendered features for open-vocabulary queries. Comparisons with other state-of-the-art methods prove that FastLGS can achieve the first place performance concerning both speed and accuracy, where FastLGS is 98x faster than LERF and 4x faster than LangSplat. Meanwhile, experiments show that FastLGS is adaptive and compatible with many downstream tasks, such as 3D segmentation and 3D object inpainting, which can be easily applied to other 3D manipulation systems.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e7524948-f1e0-4237-b719-00fe0f34cc2b)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.01916) | [⌨️ Code] | [🌐 Project Page](https://george-attano.github.io/FastLGS/)


#### <summary>End-to-End Rate-Distortion Optimized 3D Gaussian Representation
Authors: Henan Wang, Hanxin Zhu, Tianyu He, Runsen Feng, Jiajun Deng, Jiang Bian, Zhibo Chen
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has become an emerging technique with remarkable potential in 3D representation and image rendering. However, the substantial storage overhead of 3DGS significantly impedes its practical applications. In this work, we formulate the compact 3D Gaussian learning as an end-to-end Rate-Distortion Optimization (RDO) problem and propose RDO-Gaussian that can achieve flexible and continuous rate control. RDO-Gaussian addresses two main issues that exist in current schemes: 1) Different from prior endeavors that minimize the rate under the fixed distortion, we introduce dynamic pruning and entropy-constrained vector quantization (ECVQ) that optimize the rate and distortion at the same time. 2) Previous works treat the colors of each Gaussian equally, while we model the colors of different regions and materials with learnable numbers of parameters. We verify our method on both real and synthetic scenes, showcasing that RDO-Gaussian greatly reduces the size of 3D Gaussian over 40x, and surpasses existing methods in rate-distortion performance.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/660d9847-1f6f-48fb-bdca-ac251dd52d66)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.01597) | [⌨️ Code](https://github.com/USTC-IMCL/RDO-Gaussian) | [🌐 Project Page]





#### <summary>3D-HGS: 3D Half-Gaussian Splatting
Authors: Haolin Li, Jinyang Liu, Mario Sznaier, Octavia Camps
<details span>
<summary><b>Abstract</b></summary>
Photo-realistic 3D Reconstruction is a fundamental problem in 3D computer vision. This domain has seen considerable advancements owing to the advent of recent neural rendering techniques. These techniques predominantly aim to focus on learning volumetric representations of 3D scenes and refining these representations via loss functions derived from rendering. Among these, 3D Gaussian Splatting (3D-GS) has emerged as a significant method, surpassing Neural Radiance Fields (NeRFs). 3D-GS uses parameterized 3D Gaussians for modeling both spatial locations and color information, combined with a tile-based fast rendering technique. Despite its superior rendering performance and speed, the use of 3D Gaussian kernels has inherent limitations in accurately representing discontinuous functions, notably at edges and corners for shape discontinuities, and across varying textures for color discontinuities. To address this problem, we propose to employ 3D Half-Gaussian (3D-HGS) kernels, which can be used as a plug-and-play kernel. Our experiments demonstrate their capability to improve the performance of current 3D-GS related methods and achieve state-of-the-art rendering performance on various datasets without compromising rendering speed.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e737cfb0-2afd-4f05-9b6e-73cdcfa86c42)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02720) | [⌨️ Code] | [🌐 Project Page]




#### <summary>Lighting Every Darkness with 3DGS: Fast Training and Real-Time Rendering for HDR View Synthesis
Authors: Xin Jin, Pengyi Jiao, Zheng-Peng Duan, Xingchao Yang, Chun-Le Guo, Bo Ren, Chongyi Li
<details span>
<summary><b>Abstract</b></summary>
Volumetric rendering based methods, like NeRF, excel in HDR view synthesis from RAWimages, especially for nighttime scenes. While, they suffer from long training times and cannot perform real-time rendering due to dense sampling requirements. The advent of 3D Gaussian Splatting (3DGS) enables real-time rendering and faster training. However, implementing RAW image-based view synthesis directly using 3DGS is challenging due to its inherent drawbacks: 1) in nighttime scenes, extremely low SNR leads to poor structure-from-motion (SfM) estimation in distant views; 2) the limited representation capacity of spherical harmonics (SH) function is unsuitable for RAW linear color space; and 3) inaccurate scene structure hampers downstream tasks such as refocusing. To address these issues, we propose LE3D (Lighting Every darkness with 3DGS). Our method proposes Cone Scatter Initialization to enrich the estimation of SfM, and replaces SH with a Color MLP to represent the RAW linear color space. Additionally, we introduce depth distortion and near-far regularizations to improve the accuracy of scene structure for downstream tasks. These designs enable LE3D to perform real-time novel view synthesis, HDR rendering, refocusing, and tone-mapping changes. Compared to previous volumetric rendering based methods, LE3D reduces training time to 1% and improves rendering speed by up to 4,000 times for 2K resolution images in terms of FPS.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0b2677d7-2915-4959-9f57-8ac55969fd68)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.06216) | [⌨️ Code](https://github.com/Srameo/LE3D) | [🌐 Project Page](https://srameo.github.io/projects/le3d/)



#### <summary>RefGaussian: Disentangling Reflections from 3D Gaussian Splatting for Realistic Rendering
Authors: Rui Zhang, Tianyue Luo, Weidong Yang, Ben Fei, Jingyi Xu, Qingyuan Zhou, Keyi Liu, Ying He
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3D-GS) has made a notable advancement in the field of neural rendering, 3D scene reconstruction, and novel view synthesis. Nevertheless, 3D-GS encounters the main challenge when it comes to accurately representing physical reflections, especially in the case of total reflection and semi-reflection that are commonly found in real-world scenes. This limitation causes reflections to be mistakenly treated as independent elements with physical presence, leading to imprecise reconstructions. Herein, to tackle this challenge, we propose RefGaussian to disentangle reflections from 3D-GS for realistically modeling reflections. Specifically, we propose to split a scene into transmitted and reflected components and represent these components using two Spherical Harmonics (SH). Given that this decomposition is not fully determined, we employ local regularization techniques to ensure local smoothness for both the transmitted and reflected components, thereby achieving more plausible decomposition outcomes than 3D-GS. Experimental results demonstrate that our approach achieves superior novel view synthesis and accurate depth estimation outcomes. Furthermore, it enables the utilization of scene editing applications, ensuring both high-quality results and physical coherence.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/562e128f-6d93-42e2-bf8e-5c1d1136316f)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.05852) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Cinematic Gaussians: Real-Time HDR Radiance Fields with Depth of Field
Authors: Chao Wang, Krzysztof Wolski, Bernhard Kerbl, Ana Serrano, Mojtaba Bemana, Hans-Peter Seidel, Karol Myszkowski, Thomas Leimkühler
<details span>
<summary><b>Abstract</b></summary>
Radiance field methods represent the state of the art in reconstructing complex scenes from multi-view photos. However, these reconstructions often suffer from one or both of the following limitations: First, they typically represent scenes in low dynamic range (LDR), which restricts their use to evenly lit environments and hinders immersive viewing experiences. Secondly, their reliance on a pinhole camera model, assuming all scene elements are in focus in the input images, presents practical challenges and complicates refocusing during novel-view synthesis. Addressing these limitations, we present a lightweight method based on 3D Gaussian Splatting that utilizes multi-view LDR images of a scene with varying exposure times, apertures, and focus distances as input to reconstruct a high-dynamic-range (HDR) radiance field. By incorporating analytical convolutions of Gaussians based on a thin-lens camera model as well as a tonemapping module, our reconstructions enable the rendering of HDR content with flexible refocusing capabilities. We demonstrate that our combined treatment of HDR and depth of field facilitates real-time cinematic rendering, outperforming the state of the art.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d952b2ff-132f-4ce4-b9d5-aad3ef76e64a)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07329) | [⌨️ Code] | [🌐 Project Page]


#### <summary>From Chaos to Clarity: 3DGS in the Dark
Authors: Zhihao Li, Yufei Wang, Alex Kot, Bihan Wen
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis from raw images provides superior high dynamic range (HDR) information compared to reconstructions from low dynamic range RGB images. However, the inherent noise in unprocessed raw images compromises the accuracy of 3D scene representation. Our study reveals that 3D Gaussian Splatting (3DGS) is particularly susceptible to this noise, leading to numerous elongated Gaussian shapes that overfit the noise, thereby significantly degrading reconstruction quality and reducing inference speed, especially in scenarios with limited views. To address these issues, we introduce a novel self-supervised learning framework designed to reconstruct HDR 3DGS from a limited number of noisy raw images. This framework enhances 3DGS by integrating a noise extractor and employing a noise-robust reconstruction loss that leverages a noise distribution prior. Experimental results show that our method outperforms LDR/HDR 3DGS and previous state-of-the-art (SOTA) self-supervised and supervised pre-trained models in both reconstruction quality and inference speed on the RawNeRF dataset across a broad range of training views.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3837ecae-1c62-4dbc-b580-7240197432b2)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.08300) | [⌨️ Code] | [🌐 Project Page]




#### <summary>Physically Embodied Gaussian Splatting: A Realtime Correctable World Model for Robotics
Authors: Anonymous 
<details span>
<summary><b>Abstract</b></summary>
For robots to robustly understand and interact with the physical world, it is highly beneficial to have a comprehensive representation - modelling geometry, physics, and visual observations - that informs perception, planning, and control algorithms. We propose a novel dual "Gaussian-Particle" representation that models the physical world while (i) enabling predictive simulation of future states and (ii) allowing online correction from visual observations in a dynamic world. Our representation comprises particles that capture the geometrical aspect of objects in the world and can be used alongside a particle-based physics system to anticipate physically plausible future states. Attached to these particles are 3D Gaussians that render images from any viewpoint through a splatting process thus capturing the visual state. By comparing the predicted and observed images, our approach generates "visual forces" that correct the particle positions while respecting known physical constraints. By integrating predictive physical modeling with continuous visually-derived corrections, our unified representation reasons about the present and future while synchronizing with reality. We validate our approach on 2D and 3D tracking tasks as well as photometric reconstruction quality. Our system runs in realtime at 30Hz using only 3 cameras.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/32a17335-576f-4afb-937a-03ca7507495f)


</details>

[📃 arXiv:24xx]| [⌨️ Code] | [🌐 Project Page](https://embodied-gaussians.github.io/)



#### <summary>SV-Gaussians: 4D Gaussian Splatting for High-Fidelity Dynamic Reconstruction of Single-View Scenes
Authors: Anonymous 
<details span>
<summary><b>Abstract</b></summary>
With the introduction of differentiable rendering frameworks, many advanced reconstruction techniques are proposed for both static and dynamic scenes, such as NeRFs and 3D Gaussian Splatting methods. However, there is a type of video on social platforms that is shot by users through fixed monocular cameras. For the reconstruction of such dynamic scenes under single-view observation, existing reconstruction techniques are difficult to produce satisfactory results. The problems include reconstruction blur in high-frequency details of objects and inaccurate estimation of geometry. These issues motivate us to study high-quality reconstruction method for single-view videos. Inspired by 3D Gaussian Splatting, we propose a framework specifically designed for single-view dynamic scene reconstruction and editing, SV-Gaussians. Our method utilizes sparse point cloud of the scene as initialization for 3D Gaussians, and designs a deformation module to model the changes in Gaussian properties over time. We propose deformation regularization to ensure the consistency of adjacent Gaussian motions. To remove obstacles in the scene during reconstruction, we define color constraints based on obstacle mask to help Gaussians learn the true appearance of invisible regions. We conduct extensive experiments to evaluate our method and compare it with SOTA single-view reconstruction methods. Experiments show that our method has strong advantages in reconstruction quality and can achieve real-time rendering.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9052cb4e-be5b-4e24-9198-21d431398257)


</details>

[📃 arXiv:24xx]| [⌨️ Code] | [🌐 Project Page](https://embodied-gaussians.github.io/)



#### <summary>3D-Aware Manipulation with Object-Centric Gaussian Splatting
Authors: Anonymous 
<details span>
<summary><b>Abstract</b></summary>
3D Understanding of the environment is critical for the robustness and performance of robot learning systems. As an example, 2D image-based policies can easily fail due to a slight change in camera viewpoints. However, when constructing a 3D representation, previous approaches often either sacriﬁce the rich semantic abilities of 2D foundation models or a fast update rate that is crucial real-time robotic manipulation. In this work, we propose a 3D representation based on 3D Gaussians that is both semantic and dynamic. With only a single or a few camera views, our proposed representation is able to capture a dynamic scene at 30 Hz in real-time in response to robot and object movements, which is sufﬁcient for most manipulation tasks. Our key insight in achieving this fast update frequency is to make object-centric updates to the representation. Semantic information can be extracted at the initial step from pretrained foundation models, thus circumventing the inference bottleneck of large models during policy rollouts. Leveraging our object-centric Gaussian representation, we demonstrate a straightforward yet effective way to achieve view-robustness for visuomotor policies. Our representation also enables language-conditioned dynamic grasping, for which the robot perform geometric grasp of moving objects speciﬁed by open vocabulary queries.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/7492a206-ef44-47d1-a0bb-a0bd9204f923)


</details>

[📃 arXiv:24xx]| [⌨️ Code] | [🌐 Project Page](https://object-aware-gaussian.github.io/)


#### <summary>PUP 3D-GS: Principled Uncertainty Pruning for 3D Gaussian Splatting
Authors: Alex Hanson, Allen Tu, Vasu Singla, Mayuka Jayawardhana, Matthias Zwicker, Tom Goldstein 
<details span>
<summary><b>Abstract</b></summary>
Recent advancements in novel view synthesis have enabled real-time rendering speeds and high reconstruction accuracy. 3D Gaussian Splatting (3D-GS), a foundational point-based parametric 3D scene representation, models scenes as large sets of 3D Gaussians. Complex scenes can comprise of millions of Gaussians, amounting to large storage and memory requirements that limit the viability of 3D-GS on devices with limited resources. Current techniques for compressing these pretrained models by pruning Gaussians rely on combining heuristics to determine which ones to remove. In this paper, we propose a principled spatial sensitivity pruning score that outperforms these approaches. It is computed as a second-order approximation of the reconstruction error on the training views with respect to the spatial parameters of each Gaussian. Additionally, we propose a multi-round prune-refine pipeline that can be applied to any pretrained 3D-GS model without changing the training pipeline. After pruning 88.44% of the Gaussians, we observe that our PUP 3D-GS pipeline increases the average rendering speed of 3D-GS by 2.65× while retaining more salient foreground information and achieving higher image quality metrics than previous pruning techniques on scenes from the Mip-NeRF 360, Tanks & Temples, and Deep Blending datasets.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/b706ab8e-74b4-43d2-bc3b-16cc7ba138d5)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.10219) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Wild-GS: Real-Time Novel View Synthesis from Unconstrained Photo Collections
Authors: Jiacong Xu, Yiqun Mei, Vishal M. Patel
<details span>
<summary><b>Abstract</b></summary>
Photographs captured in unstructured tourist environments frequently exhibit variable appearances and transient occlusions, challenging accurate scene reconstruction and inducing artifacts in novel view synthesis. Although prior approaches have integrated the Neural Radiance Field (NeRF) with additional learnable modules to handle the dynamic appearances and eliminate transient objects, their extensive training demands and slow rendering speeds limit practical deployments. Recently, 3D Gaussian Splatting (3DGS) has emerged as a promising alternative to NeRF, offering superior training and inference efficiency along with better rendering quality. This paper presents Wild-GS, an innovative adaptation of 3DGS optimized for unconstrained photo collections while preserving its efficiency benefits. Wild-GS determines the appearance of each 3D Gaussian by their inherent material attributes, global illumination and camera properties per image, and point-level local variance of reflectance. Unlike previous methods that model reference features in image space, Wild-GS explicitly aligns the pixel appearance features to the corresponding local Gaussians by sampling the triplane extracted from the reference image. This novel design effectively transfers the high-frequency detailed appearance of the reference view to 3D space and significantly expedites the training process. Furthermore, 2D visibility maps and depth regularization are leveraged to mitigate the transient effects and constrain the geometry, respectively. Extensive experiments demonstrate that Wild-GS achieves state-of-the-art rendering performance and the highest efficiency in both training and inference among all the existing techniques.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/51841d20-81f2-4bba-aa5d-6ff70123153e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.10373) | [⌨️ Code] | [🌐 Project Page]


#### <summary>L4GM: Large 4D Gaussian Reconstruction Model
Authors: Jiawei Ren, Kevin Xie, Ashkan Mirzaei, Hanxue Liang, Xiaohui Zeng, Karsten Kreis, Ziwei Liu, Antonio Torralba, Sanja Fidler, Seung Wook Kim, Huan Ling
<details span>
<summary><b>Abstract</b></summary>
We present L4GM, the first 4D Large Reconstruction Model that produces animated objects from a single-view video input -- in a single feed-forward pass that takes only a second. Key to our success is a novel dataset of multiview videos containing curated, rendered animated objects from Objaverse. This dataset depicts 44K diverse objects with 110K animations rendered in 48 viewpoints, resulting in 12M videos with a total of 300M frames. We keep our L4GM simple for scalability and build directly on top of LGM, a pretrained 3D Large Reconstruction Model that outputs 3D Gaussian ellipsoids from multiview image input. L4GM outputs a per-frame 3D Gaussian Splatting representation from video frames sampled at a low fps and then upsamples the representation to a higher fps to achieve temporal smoothness. We add temporal self-attention layers to the base LGM to help it learn consistency across time, and utilize a per-timestep multiview rendering loss to train the model. The representation is upsampled to a higher framerate by training an interpolation model which produces intermediate 3D Gaussian representations. We showcase that L4GM that is only trained on synthetic data generalizes extremely well on in-the-wild videos, producing high quality animated 3D assets.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/51841d20-81f2-4bba-aa5d-6ff70123153e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.10324) | [⌨️ Code] | [🌐 Project Page](https://research.nvidia.com/labs/toronto-ai/l4gm)

#### <summary>Modeling Ambient Scene Dynamics for Free-view Synthesis
Authors: Meng-Li Shih, Jia-Bin Huang, Changil Kim, Rajvi Shah, Johannes Kopf, Chen Gao
<details span>
<summary><b>Abstract</b></summary>
We introduce a novel method for dynamic free-view synthesis of an ambient scenes from a monocular capture bringing a immersive quality to the viewing experience. Our method builds upon the recent advancements in 3D Gaussian Splatting (3DGS) that can faithfully reconstruct complex static scenes. Previous attempts to extend 3DGS to represent dynamics have been confined to bounded scenes or require multi-camera captures, and often fail to generalize to unseen motions, limiting their practical application. Our approach overcomes these constraints by leveraging the periodicity of ambient motions to learn the motion trajectory model, coupled with careful regularization. We also propose important practical strategies to improve the visual quality of the baseline 3DGS static reconstructions and to improve memory efficiency critical for GPU-memory intensive learning. We demonstrate high-quality photorealistic novel view synthesis of several ambient natural scenes with intricate textures and fine structural elements.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a2aa2b78-6e76-4514-9705-56b8bf25162e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.09395) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Unified Gaussian Primitives for Scene Representation and Rendering
Authors: Yang Zhou, Songyin Wu, Ling-Qi Yan
<details span>
<summary><b>Abstract</b></summary>
Searching for a unified scene representation remains a research challenge in computer graphics. Traditional mesh-based representations are unsuitable for dense, fuzzy elements, and introduce additional complexity for filtering and differentiable rendering. Conversely, voxel-based representations struggle to model hard surfaces and suffer from intensive memory requirement. We propose a general-purpose rendering primitive based on 3D Gaussian distribution for unified scene representation, featuring versatile appearance ranging from glossy surfaces to fuzzy elements, as well as physically based scattering to enable accurate global illumination. We formulate the rendering theory for the primitive based on non-exponential transport and derive efficient rendering operations to be compatible with Monte Carlo path tracing. The new representation can be converted from different sources, including meshes and 3D Gaussian splatting, and further refined via transmittance optimization thanks to its differentiability. We demonstrate the versatility of our representation in various rendering applications such as global illumination and appearance editing, while supporting arbitrary lighting conditions by nature. Additionally, we compare our representation to existing volumetric representations, highlighting its efficiency to reproduce details.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a2aa2b78-6e76-4514-9705-56b8bf25162e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.09733v1) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Splatter a Video: Video Gaussian Representation for Versatile Processing
Authors: Yang-Tian Sun, Yi-Hua Huang, Lin Ma, Xiaoyang Lyu, Yan-Pei Cao, Xiaojuan Qi
<details span>
<summary><b>Abstract</b></summary>
Video representation is a long-standing problem that is crucial for various down-stream tasks, such as tracking,depth prediction,segmentation,view synthesis,and editing. However, current methods either struggle to model complex motions due to the absence of 3D structure or rely on implicit 3D representations that are ill-suited for manipulation tasks. To address these challenges, we introduce a novel explicit 3D representation-video Gaussian representation -- that embeds a video into 3D Gaussians. Our proposed representation models video appearance in a 3D canonical space using explicit Gaussians as proxies and associates each Gaussian with 3D motions for video motion. This approach offers a more intrinsic and explicit representation than layered atlas or volumetric pixel matrices. To obtain such a representation, we distill 2D priors, such as optical flow and depth, from foundation models to regularize learning in this ill-posed setting. Extensive applications demonstrate the versatility of our new video representation. It has been proven effective in numerous video processing tasks, including tracking, consistent video depth and feature refinement, motion and appearance editing, and stereoscopic video generation.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9113df61-e81c-43d0-aa6b-a9438d05e678)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.13870) | [⌨️ Code](https://github.com/SunYangtian/Splatter_A_Video) | [🌐 Project Page](https://sunyangtian.github.io/spatter_a_video_web/)



#### <summary>GeoLRM: Geometry-Aware Large Reconstruction Model for High-Quality 3D Gaussian Generation
Authors: Chubin Zhang, Hongliang Song, Yi Wei, Yu Chen, Jiwen Lu, Yansong Tang
<details span>
<summary><b>Abstract</b></summary>
In this work, we introduce the Geometry-Aware Large Reconstruction Model (GeoLRM), an approach which can predict high-quality assets with 512k Gaussians and 21 input images in only 11 GB GPU memory. Previous works neglect the inherent sparsity of 3D structure and do not utilize explicit geometric relationships between 3D and 2D images. This limits these methods to a low-resolution representation and makes it difficult to scale up to the dense views for better quality. GeoLRM tackles these issues by incorporating a novel 3D-aware transformer structure that directly processes 3D points and uses deformable cross-attention mechanisms to effectively integrate image features into 3D representations. We implement this solution through a two-stage pipeline: initially, a lightweight proposal network generates a sparse set of 3D anchor points from the posed image inputs; subsequently, a specialized reconstruction transformer refines the geometry and retrieves textural details. Extensive experimental results demonstrate that GeoLRM significantly outperforms existing models, especially for dense view inputs. We also demonstrate the practical applicability of our model with 3D generation tasks, showcasing its versatility and potential for broader adoption in real-world applications.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a49b356c-53e4-4494-8694-4481f1bdb646)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.15333) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Taming 3DGS: High-Quality Radiance Fields with Limited Resources
Authors: Saswat Subhajyoti Mallick, Rahul Goel, Bernhard Kerbl, Francisco Vicente Carrasco, Markus Steinberger, Fernando De La Torre
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has transformed novel-view synthesis with its fast, interpretable, and high-fidelity rendering. However, its resource requirements limit its usability. Especially on constrained devices, training performance degrades quickly and often cannot complete due to excessive memory consumption of the model. The method converges with an indefinite number of Gaussians -- many of them redundant -- making rendering unnecessarily slow and preventing its usage in downstream tasks that expect fixed-size inputs. To address these issues, we tackle the challenges of training and rendering 3DGS models on a budget. We use a guided, purely constructive densification process that steers densification toward Gaussians that raise the reconstruction quality. Model size continuously increases in a controlled manner towards an exact budget, using score-based densification of Gaussians with training-time priors that measure their contribution. We further address training speed obstacles: following a careful analysis of 3DGS' original pipeline, we derive faster, numerically equivalent solutions for gradient computation and attribute updates, including an alternative parallelization for efficient backpropagation. We also propose quality-preserving approximations where suitable to reduce training time even further. Taken together, these enhancements yield a robust, scalable solution with reduced training times, lower compute and memory requirements, and high quality. Our evaluation shows that in a budgeted setting, we obtain competitive quality metrics with 3DGS while achieving a 4--5x reduction in both model size and training time. With more generous budgets, our measured quality surpasses theirs. These advances open the door for novel-view synthesis in constrained environments, e.g., mobile devices.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/417f9b6a-b0ee-478e-9df8-0e76c3895b21)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.15643) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Reducing the Memory Footprint of 3D Gaussian Splatting
Authors: Panagiotis Papantonakis, Georgios Kopanas, Bernhard Kerbl, Alexandre Lanvin, George Drettakis
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian splatting provides excellent visual quality for novel view synthesis, with fast training and real-time rendering; unfortunately, the memory requirements of this method for storing and transmission are unreasonably high. We first analyze the reasons for this, identifying three main areas where storage can be reduced: the number of 3D Gaussian primitives used to represent a scene, the number of coefficients for the spherical harmonics used to represent directional radiance, and the precision required to store Gaussian primitive attributes. We present a solution to each of these issues. First, we propose an efficient, resolution-aware primitive pruning approach, reducing the primitive count by half. Second, we introduce an adaptive adjustment method to choose the number of coefficients used to represent directional radiance for each Gaussian primitive, and finally a codebook-based quantization method, together with a half-float representation for further memory reduction. Taken together, these three components result in a 27 reduction in overall size on disk on the standard datasets we tested, along with a 1.7 speedup in rendering speed. We demonstrate our method on standard datasets and show how our solution results in significantly reduced download times when using the method on a mobile device.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9840e8f6-ab3d-40b5-a2eb-2fc92697b83c)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.17074) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Trimming the Fat: Efficient Compression of 3D Gaussian Splats through Pruning
Authors: Muhammad Salman Ali, Maryam Qamar, Sung-Ho Bae, Enzo Tartaglione
<details span>
<summary><b>Abstract</b></summary>
In recent times, the utilization of 3D models has gained traction, owing to the capacity for end-to-end training initially offered by Neural Radiance Fields and more recently by 3D Gaussian Splatting (3DGS) models. The latter holds a significant advantage by inherently easing rapid convergence during training and offering extensive editability. However, despite rapid advancements, the literature still lives in its infancy regarding the scalability of these models. In this study, we take some initial steps in addressing this gap, showing an approach that enables both the memory and computational scalability of such models. Specifically, we propose "Trimming the fat", a post-hoc gradient-informed iterative pruning technique to eliminate redundant information encoded in the model. Our experimental findings on widely acknowledged benchmarks attest to the effectiveness of our approach, revealing that up to 75% of the Gaussians can be removed while maintaining or even improving upon baseline performance. Our approach achieves around 50× compression while preserving performance similar to the baseline model, and is able to speed-up computation up to 600~FPS.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/dae15c6b-fe33-4f28-91a8-3d9eb3bce701)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.18214) | [⌨️ Code] | [🌐 Project Page]




#### <summary>SpotlessSplats: Ignoring Distractors in 3D Gaussian Splatting
Authors: Muhammad Salman Ali, Maryam Qamar, Sung-Ho Bae, Enzo Tartaglione
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) is a promising technique for 3D reconstruction, offering efficient training and rendering speeds, making it suitable for real-time applications.However, current methods require highly controlled environments (no moving people or wind-blown elements, and consistent lighting) to meet the inter-view consistency assumption of 3DGS. This makes reconstruction of real-world captures problematic. We present SpotlessSplats, an approach that leverages pre-trained and general-purpose features coupled with robust optimization to effectively ignore transient distractors. Our method achieves state-of-the-art reconstruction quality both visually and quantitatively, on casual captures.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/47e61d0c-43ac-4bf4-85bd-045a70f44a2d)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.20055) | [⌨️ Code] | [🌐 Project Page](https://spolesssplats.github.io/)



#### <summary>EgoGaussian: Dynamic Scene Understanding from Egocentric Video with 3D Gaussian Splatting
Authors: Daiwei Zhang, Gengyan Li, Jiajie Li, Mickaël Bressieux, Otmar Hilliges, Marc Pollefeys, Luc Van Gool, Xi Wang
<details span>
<summary><b>Abstract</b></summary>
Human activities are inherently complex, and even simple household tasks involve numerous object interactions. To better understand these activities and behaviors, it is crucial to model their dynamic interactions with the environment. The recent availability of affordable head-mounted cameras and egocentric data offers a more accessible and efficient means to understand dynamic human-object interactions in 3D environments. However, most existing methods for human activity modeling either focus on reconstructing 3D models of hand-object or human-scene interactions or on mapping 3D scenes, neglecting dynamic interactions with objects. The few existing solutions often require inputs from multiple sources, including multi-camera setups, depth-sensing cameras, or kinesthetic sensors. To this end, we introduce EgoGaussian, the first method capable of simultaneously reconstructing 3D scenes and dynamically tracking 3D object motion from RGB egocentric input alone. We leverage the uniquely discrete nature of Gaussian Splatting and segment dynamic interactions from the background. Our approach employs a clip-level online learning pipeline that leverages the dynamic nature of human activities, allowing us to reconstruct the temporal evolution of the scene in chronological order and track rigid object motion. Additionally, our method automatically segments object and background Gaussians, providing 3D representations for both static scenes and dynamic objects. EgoGaussian outperforms previous NeRF and Dynamic Gaussian methods in challenging in-the-wild videos and we also qualitatively demonstrate the high quality of the reconstructed models.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e0ffec64-9f8a-4675-9095-0c76271991fd)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.19811) | [⌨️ Code] | [🌐 Project Page](https://zdwww.github.io/egogs.github.io/)


#### <summary>Generative Lifting of Multiview to 3D from Unknown Pose: Wrapping NeRF inside Diffusion
Authors: Xin Yuan, Rana Hanocka, Michael Maire
<details span>
<summary><b>Abstract</b></summary>
We cast multiview reconstruction from unknown pose as a generative modeling problem. From a collection of unannotated 2D images of a scene, our approach simultaneously learns both a network to predict camera pose from 2D image input, as well as the parameters of a Neural Radiance Field (NeRF) for the 3D scene. To drive learning, we wrap both the pose prediction network and NeRF inside a Denoising Diffusion Probabilistic Model (DDPM) and train the system via the standard denoising objective. Our framework requires the system accomplish the task of denoising an input 2D image by predicting its pose and rendering the NeRF from that pose. Learning to denoise thus forces the system to concurrently learn the underlying 3D NeRF representation and a mapping from images to camera extrinsic parameters. To facilitate the latter, we design a custom network architecture to represent pose as a distribution, granting implicit capacity for discovering view correspondences when trained end-to-end for denoising alone. This technique allows our system to successfully build NeRFs, without pose knowledge, for challenging scenes where competing methods fail. At the conclusion of training, our learned NeRF can be extracted and used as a 3D scene model; our full system can be used to sample novel camera poses and generate novel-view images.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/dff892ae-98e8-456b-b9ea-554d05c1be3e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.06972) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Image-GS: Content-Adaptive Image Representation via 2D Gaussians
Authors: Yunxiang Zhang, Alexandr Kuznetsov, Akshay Jindal, Kenneth Chen, Anton Sochenov, Anton Kaplanyan, Qi Sun
<details span>
<summary><b>Abstract</b></summary>
Neural image representations have recently emerged as a promising technique for storing, streaming, and rendering visual data. Coupled with learning-based workflows, these novel representations have demonstrated remarkable visual fidelity and memory efficiency. However, existing neural image representations often rely on explicit uniform data structures without content adaptivity or computation-intensive implicit models, limiting their adoption in real-time graphics applications.
Inspired by recent advances in radiance field rendering, we propose Image-GS, a content-adaptive image representation. Using anisotropic 2D Gaussians as the basis, Image-GS shows high memory efficiency, supports fast random access, and offers a natural level of detail stack. Leveraging a tailored differentiable renderer, Image-GS fits a target image by adaptively allocating and progressively optimizing a set of 2D Gaussians. The generalizable efficiency and fidelity of Image-GS are validated against several recent neural image representations and industry-standard texture compressors on a diverse set of images. Notably, its memory and computation requirements solely depend on and linearly scale with the number of 2D Gaussians, providing flexible controls over the trade-off between visual fidelity and run-time efficiency. We hope this research offers insights for developing new applications that require adaptive quality and resource control, such as machine perception, asset streaming, and content generation.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/727dc6c1-86bc-4dc0-92ba-e1727e779b23)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.01866) | [⌨️ Code] | [🌐 Project Page]

#### <summary>VEGS: View Extrapolation of Urban Scenes in 3D Gaussian Splatting using Learned Priors
Authors: Sungwon Hwang, Min-Jung Kim, Taewoong Kang, Jayeon Kang, Jaegul Choo
<details span>
<summary><b>Abstract</b></summary>
Neural rendering-based urban scene reconstruction methods commonly rely on images collected from driving vehicles with cameras facing and moving forward. Although these methods can successfully synthesize from views similar to training camera trajectory, directing the novel view outside the training camera distribution does not guarantee on-par performance. In this paper, we tackle the Extrapolated View Synthesis (EVS) problem by evaluating the reconstructions on views such as looking left, right or downwards with respect to training camera distributions. To improve rendering quality for EVS, we initialize our model by constructing dense LiDAR map, and propose to leverage prior scene knowledge such as surface normal estimator and large-scale diffusion model. Qualitative and quantitative comparisons demonstrate the effectiveness of our methods on EVS. To the best of our knowledge, we are the first to address the EVS problem in urban scene reconstruction.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3ae1e9e5-1878-48e7-80a0-6f0b4b49cc5a)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.02945) | [⌨️ Code](https://github.com/deepshwang/vegs) | [🌐 Project Page](https://vegs3d.github.io/)

#### <summary>Free-SurGS: SfM-Free 3D Gaussian Splatting for Surgical Scene Reconstruction
Authors: Jiaxin Guo, Jiangliu Wang, Di Kang, Wenzhen Dong, Wenting Wang, Yun-hui Liu
<details span>
<summary><b>Abstract</b></summary>
Real-time 3D reconstruction of surgical scenes plays a vital role in computer-assisted surgery, holding a promise to enhance surgeons' visibility. Recent advancements in 3D Gaussian Splatting (3DGS) have shown great potential for real-time novel view synthesis of general scenes, which relies on accurate poses and point clouds generated by Structure-from-Motion (SfM) for initialization. However, 3DGS with SfM fails to recover accurate camera poses and geometry in surgical scenes due to the challenges of minimal textures and photometric inconsistencies. To tackle this problem, in this paper, we propose the first SfM-free 3DGS-based method for surgical scene reconstruction by jointly optimizing the camera poses and scene representation. Based on the video continuity, the key of our method is to exploit the immediate optical flow priors to guide the projection flow derived from 3D Gaussians. Unlike most previous methods relying on photometric loss only, we formulate the pose estimation problem as minimizing the flow loss between the projection flow and optical flow. A consistency check is further introduced to filter the flow outliers by detecting the rigid and reliable points that satisfy the epipolar geometry. During 3D Gaussian optimization, we randomly sample frames to optimize the scene representations to grow the 3D Gaussian progressively. Experiments on the SCARED dataset demonstrate our superior performance over existing methods in novel view synthesis and pose estimation with high efficiency.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e201a87d-001e-423a-af66-8700c4b6f36a)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.02918) | [⌨️ Code](https://github.com/wrld/Free-SurGS) | [🌐 Project Page]

#### <summary>Gaussian Eigen Models for Human Heads
Authors: Wojciech Zielonka, Timo Bolkart, Thabo Beeler, Justus Thies
<details span>
<summary><b>Abstract</b></summary>
We present personalized Gaussian Eigen Models (GEMs) for human heads, a novel method that compresses dynamic 3D Gaussians into low-dimensional linear spaces. Our approach is inspired by the seminal work of Blanz and Vetter, where a mesh-based 3D morphable model (3DMM) is constructed from registered meshes. Based on dynamic 3D Gaussians, we create a lower-dimensional representation of primitives that applies to most 3DGS head avatars. Specifically, we propose a universal method to distill the appearance of a mesh-controlled UNet Gaussian avatar using an ensemble of linear eigenbasis. We replace heavy CNN-based architectures with a single linear layer improving speed and enabling a range of real-time downstream applications. To create a particular facial expression, one simply needs to perform a dot product between the eigen coefficients and the distilled basis. This efficient method removes the requirement for an input mesh during testing, enhancing simplicity and speed in expression generation. This process is highly efficient and supports real-time rendering on everyday devices, leveraging the effectiveness of standard Gaussian Splatting. In addition, we demonstrate how the GEM can be controlled using a ResNet-based regression architecture. We show and compare self-reenactment and cross-person reenactment to state-of-the-art 3D avatar methods, demonstrating higher quality and better control. A real-time demo showcases the applicability of the GEM representation.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0b34bebb-6e58-4356-9f86-bb7cc702311d)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.04545) | [⌨️ Code] | [🌐 Project Page](https://zielon.github.io/gem/)

#### <summary>GSD: View-Guided Gaussian Splatting Diffusion for 3D Reconstruction
Authors: Yuxuan Mu, Xinxin Zuo, Chuan Guo, Yilin Wang, Juwei Lu, Xiaofeng Wu, Songcen Xu, Peng Dai, Youliang Yan, Li Cheng
<details span>
<summary><b>Abstract</b></summary>
We present GSD, a diffusion model approach based on Gaussian Splatting (GS) representation for 3D object reconstruction from a single view. Prior works suffer from inconsistent 3D geometry or mediocre rendering quality due to improper representations. We take a step towards resolving these shortcomings by utilizing the recent state-of-the-art 3D explicit representation, Gaussian Splatting, and an unconditional diffusion model. This model learns to generate 3D objects represented by sets of GS ellipsoids. With these strong generative 3D priors, though learning unconditionally, the diffusion model is ready for view-guided reconstruction without further model fine-tuning. This is achieved by propagating fine-grained 2D features through the efficient yet flexible splatting function and the guided denoising sampling process. In addition, a 2D diffusion model is further employed to enhance rendering fidelity, and improve reconstructed GS quality by polishing and re-using the rendered images. The final reconstructed objects explicitly come with high-quality 3D structure and texture, and can be efficiently rendered in arbitrary views. Experiments on the challenging real-world CO3D dataset demonstrate the superiority of our approach.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/fa359089-2cc8-48f3-8c5c-25ca5ccb9c9f)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.04237) | [⌨️ Code] | [🌐 Project Page]



#### <summary>CRiM-GS: Continuous Rigid Motion-Aware Gaussian Splatting from Motion Blur Images
Authors: Junghe Lee, Donghyeong Kim, Dogyoon Lee, Suhwan Cho, Sangyoun Lee
<details span>
<summary><b>Abstract</b></summary>
Neural radiance fields (NeRFs) have received significant attention due to their high-quality novel view rendering ability, prompting research to address various real-world cases. One critical challenge is the camera motion blur caused by camera movement during exposure time, which prevents accurate 3D scene reconstruction. In this study, we propose continuous rigid motion-aware gaussian splatting (CRiM-GS) to reconstruct accurate 3D scene from blurry images with real-time rendering speed. Considering the actual camera motion blurring process, which consists of complex motion patterns, we predict the continuous movement of the camera based on neural ordinary differential equations (ODEs). Specifically, we leverage rigid body transformations to model the camera motion with proper regularization, preserving the shape and size of the object. Furthermore, we introduce a continuous deformable 3D transformation in the \textit{SE(3)} field to adapt the rigid body transformation to real-world problems by ensuring a higher degree of freedom. By revisiting fundamental camera theory and employing advanced neural network training techniques, we achieve accurate modeling of continuous camera trajectories. We conduct extensive experiments, demonstrating state-of-the-art performance both quantitatively and qualitatively on benchmark datasets.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/58dca935-df48-4ef2-a217-edda4ea97f42)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.03923) | [⌨️ Code](https://github.com/Jho-Yonsei/CRiM-GS) | [🌐 Project Page](https://jho-yonsei.github.io/CRiM-Gaussian/)



#### <summary>PFGS: High Fidelity Point Cloud Rendering via Feature Splatting
Authors: Jiaxu Wang, Ziyi Zhang, Junhao He, Renjing Xu
<details span>
<summary><b>Abstract</b></summary>
Rendering high-fidelity images from sparse point clouds is still challenging. Existing learning-based approaches suffer from either hole artifacts, missing details, or expensive computations. In this paper, we propose a novel framework to render high-quality images from sparse points. This method first attempts to bridge the 3D Gaussian Splatting and point cloud rendering, which includes several cascaded modules. We first use a regressor to estimate Gaussian properties in a point-wise manner, the estimated properties are used to rasterize neural feature descriptors into 2D planes which are extracted from a multiscale extractor. The projected feature volume is gradually decoded toward the final prediction via a multiscale and progressive decoder. The whole pipeline experiences a two-stage training and is driven by our well-designed progressive and multiscale reconstruction loss. Experiments on different benchmarks show the superiority of our method in terms of rendering qualities and the necessities of our main components.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/57f2151e-68f1-41cd-96c4-2a0ce8163d70)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.03857) | [⌨️ Code](https://github.com/Mercerai/PFGS) | [🌐 Project Page]

#### <summary>GaussReg: Fast 3D Registration with Gaussian Splatting
Authors: Jiahao Chang, Yinglin Xu, Yihao Li, Yuantao Chen, Xiaoguang Han
<details span>
<summary><b>Abstract</b></summary>
Point cloud registration is a fundamental problem for large-scale 3D scene scanning and reconstruction. With the help of deep learning, registration methods have evolved significantly, reaching a nearly-mature stage. As the introduction of Neural Radiance Fields (NeRF), it has become the most popular 3D scene representation as its powerful view synthesis capabilities. Regarding NeRF representation, its registration is also required for large-scale scene reconstruction. However, this topic extremly lacks exploration. This is due to the inherent challenge to model the geometric relationship among two scenes with implicit representations. The existing methods usually convert the implicit representation to explicit representation for further registration. Most recently, Gaussian Splatting (GS) is introduced, employing explicit 3D Gaussian. This method significantly enhances rendering speed while maintaining high rendering quality. Given two scenes with explicit GS representations, in this work, we explore the 3D registration task between them. To this end, we propose GaussReg, a novel coarse-to-fine framework, both fast and accurate. The coarse stage follows existing point cloud registration methods and estimates a rough alignment for point clouds from GS. We further newly present an image-guided fine registration approach, which renders images from GS to provide more detailed geometric information for precise alignment. To support comprehensive evaluation, we carefully build a scene-level dataset called ScanNet-GSReg with 1379 scenes obtained from the ScanNet dataset and collect an in-the-wild dataset called GSReg. Experimental results demonstrate our method achieves state-of-the-art performance on multiple datasets. Our GaussReg is 44 times faster than HLoc (SuperPoint as the feature extractor and SuperGlue as the matcher) with comparable accuracy.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/7dcdb111-d2b3-4869-8685-52aa620fea74)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.05254) | [⌨️ Code] | [🌐 Project Page](https://jiahao620.github.io/gaussreg/)

#### <summary>3D Gaussian Ray Tracing: Fast Tracing of Particle Scenes
Authors: Nicolas Moenne-Loccoz, Ashkan Mirzaei, Or Perel, Riccardo de Lutio, Janick Martinez Esturo, Gavriel State, Sanja Fidler, Nicholas Sharp, Zan Gojcic
<details span>
<summary><b>Abstract</b></summary>
Particle-based representations of radiance fields such as 3D Gaussian Splatting have found great success for reconstructing and re-rendering of complex scenes. Most existing methods render particles via rasterization, projecting them to screen space tiles for processing in a sorted order. This work instead considers ray tracing the particles, building a bounding volume hierarchy and casting a ray for each pixel using high-performance GPU ray tracing hardware. To efficiently handle large numbers of semi-transparent particles, we describe a specialized rendering algorithm which encapsulates particles with bounding meshes to leverage fast ray-triangle intersections, and shades batches of intersections in depth-order. The benefits of ray tracing are well-known in computer graphics: processing incoherent rays for secondary lighting effects such as shadows and reflections, rendering from highly-distorted cameras common in robotics, stochastically sampling rays, and more. With our renderer, this flexibility comes at little cost compared to rasterization. Experiments demonstrate the speed and accuracy of our approach, as well as several applications in computer graphics and vision. We further propose related improvements to the basic Gaussian representation, including a simple use of generalized kernel functions which significantly reduces particle hit counts.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/fc269f8f-46cd-4cf4-9a2e-0ddcb9a64fc5)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.07090) | [⌨️ Code] | [🌐 Project Page]


#### <summary>WildGaussians: 3D Gaussian Splatting in the Wild
Authors: Jonas Kulhanek, Songyou Peng, Zuzana Kukelova, Marc Pollefeys, Torsten Sattler
<details span>
<summary><b>Abstract</b></summary>
While the field of 3D scene reconstruction is dominated by NeRFs due to their photorealistic quality, 3D Gaussian Splatting (3DGS) has recently emerged, offering similar quality with real-time rendering speeds. However, both methods primarily excel with well-controlled 3D scenes, while in-the-wild data - characterized by occlusions, dynamic objects, and varying illumination - remains challenging. NeRFs can adapt to such conditions easily through per-image embedding vectors, but 3DGS struggles due to its explicit representation and lack of shared parameters. To address this, we introduce WildGaussians, a novel approach to handle occlusions and appearance changes with 3DGS. By leveraging robust DINO features and integrating an appearance modeling module within 3DGS, our method achieves state-of-the-art results. We demonstrate that WildGaussians matches the real-time rendering speed of 3DGS while surpassing both 3DGS and NeRF baselines in handling in-the-wild data, all within a simple architectural framework.
 
![image](https://github.com/user-attachments/assets/57b7aad8-afa8-4eb3-a546-cf94131fe605)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.08447) | [⌨️ Code](https://github.com/jkulhanek/wild-gaussians/) | [🌐 Project Page](https://wild-gaussians.github.io/)


#### <summary>Textured-GS: Gaussian Splatting with Spatially Defined Color and Opacity
Authors: Zhentao Huang, Minglun Gong
<details span>
<summary><b>Abstract</b></summary>
In this paper, we introduce Textured-GS, an innovative method for rendering Gaussian splatting that incorporates spatially defined color and opacity variations using Spherical Harmonics (SH). This approach enables each Gaussian to exhibit a richer representation by accommodating varying colors and opacities across its surface, significantly enhancing rendering quality compared to traditional methods. To demonstrate the merits of our approach, we have adapted the Mini-Splatting architecture to integrate textured Gaussians without increasing the number of Gaussians. Our experiments across multiple real-world datasets show that Textured-GS consistently outperforms both the baseline Mini-Splatting and standard 3DGS in terms of visual fidelity. The results highlight the potential of Textured-GS to advance Gaussian-based rendering technologies, promising more efficient and high-quality scene reconstructions.
 
![image](https://github.com/user-attachments/assets/56d9bcc8-7e8b-42dd-b6ae-e6c51251d1c8)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.09733) | [⌨️ Code] | [🌐 Project Page]

#### <summary>3DGS.zip: A survey on 3D Gaussian Splatting Compression Methods
Authors: Milena T. Bagdasarian, Paul Knoll, Florian Barthel, Wieland Morgenstern
<details span>
<summary><b>Abstract</b></summary>
We present a work-in-progress survey on 3D Gaussian Splatting compression methods, focusing on their statistical performance across various benchmarks. This survey aims to facilitate comparability by summarizing key statistics of different compression approaches in a tabulated format. The datasets evaluated include TanksAndTemples, MipNeRF360, DeepBlending, and SyntheticNeRF. For each method, we report the Peak Signal-to-Noise Ratio (PSNR), Structural Similarity Index (SSIM), Learned Perceptual Image Patch Similarity (LPIPS), and the resultant size in megabytes (MB), as provided by the respective authors. This is an ongoing, open project, and we invite contributions from the research community as GitHub issues or pull requests. Please visit this http URL for more information and a sortable version of the table.

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.09510) | [⌨️ Code](https://github.com/w-m/3dgs-compression-survey) | [🌐 Project Page](https://w-m.github.io/3dgs-compression-survey/)


#### <summary>Click-Gaussian: Interactive Segmentation to Any 3D Gaussians
Authors: Seokhun Choi, Hyeonseop Song, Jaechul Kim, Taehyeong Kim, Hoseok Do
<details span>
<summary><b>Abstract</b></summary>
Interactive segmentation of 3D Gaussians opens a great opportunity for real-time manipulation of 3D scenes thanks to the real-time rendering capability of 3D Gaussian Splatting. However, the current methods suffer from time-consuming post-processing to deal with noisy segmentation output. Also, they struggle to provide detailed segmentation, which is important for fine-grained manipulation of 3D scenes. In this study, we propose Click-Gaussian, which learns distinguishable feature fields of two-level granularity, facilitating segmentation without time-consuming post-processing. We delve into challenges stemming from inconsistently learned feature fields resulting from 2D segmentation obtained independently from a 3D scene. 3D segmentation accuracy deteriorates when 2D segmentation results across the views, primary cues for 3D segmentation, are in conflict. To overcome these issues, we propose Global Feature-guided Learning (GFL). GFL constructs the clusters of global feature candidates from noisy 2D segments across the views, which smooths out noises when training the features of 3D Gaussians. Our method runs in 10 ms per click, 15 to 130 times as fast as the previous methods, while also significantly improving segmentation accuracy.

![image](https://github.com/user-attachments/assets/08a07fc6-4309-46ce-b886-9955b7803086)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.11793) | [⌨️ Code] | [🌐 Project Page](https://seokhunchoi.github.io/Click-Gaussian/)




#### <summary>Gaussian Splatting LK
Authors: Liuyue Xie, Joel Julin, Koichiro Niinuma, Laszlo A. Jeni
<details span>
<summary><b>Abstract</b></summary>
Reconstructing dynamic 3D scenes from 2D images and generating diverse views over time presents a significant challenge due to the inherent complexity and temporal dynamics involved. While recent advancements in neural implicit models and dynamic Gaussian Splatting have shown promise, limitations persist, particularly in accurately capturing the underlying geometry of highly dynamic scenes. Some approaches address this by incorporating strong semantic and geometric priors through diffusion models. However, we explore a different avenue by investigating the potential of regularizing the native warp field within the dynamic Gaussian Splatting framework. Our method is grounded on the key intuition that an accurate warp field should produce continuous space-time motions. While enforcing the motion constraints on warp fields is non-trivial, we show that we can exploit knowledge innate to the forward warp field network to derive an analytical velocity field, then time integrate for scene flows to effectively constrain both the 2D motion and 3D positions of the Gaussians. This derived Lucas-Kanade style analytical regularization enables our method to achieve superior performance in reconstructing highly dynamic scenes, even under minimal camera movement, extending the boundaries of what existing dynamic Gaussian Splatting frameworks can achieve.

![image](https://github.com/user-attachments/assets/50bf8e84-85bb-484a-9473-a41674e9ac76)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.11309) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Splatfacto-W: A Nerfstudio Implementation of Gaussian Splatting for Unconstrained Photo Collections
Authors: Congrong Xu, Justin Kerr, Angjoo Kanazawa
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis from unconstrained in-the-wild image collections remains a significant yet challenging task due to photometric variations and transient occluders that complicate accurate scene reconstruction. Previous methods have approached these issues by integrating per-image appearance features embeddings in Neural Radiance Fields (NeRFs). Although 3D Gaussian Splatting (3DGS) offers faster training and real-time rendering, adapting it for unconstrained image collections is non-trivial due to the substantially different architecture. In this paper, we introduce Splatfacto-W, an approach that integrates per-Gaussian neural color features and per-image appearance embeddings into the rasterization process, along with a spherical harmonics-based background model to represent varying photometric appearances and better depict backgrounds. Our key contributions include latent appearance modeling, efficient transient object handling, and precise background modeling. Splatfacto-W delivers high-quality, real-time novel view synthesis with improved scene consistency in in-the-wild scenarios. Our method improves the Peak Signal-to-Noise Ratio (PSNR) by an average of 5.3 dB compared to 3DGS, enhances training speed by 150 times compared to NeRF-based methods, and achieves a similar rendering speed to 3DGS.

![image](https://github.com/user-attachments/assets/8c35b82a-0f5c-49ef-9c60-04f112b8bd64)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12306) | [⌨️ Code](https://github.com/KevinXu02/splatfacto-w) | [🌐 Project Page](https://kevinxu02.github.io/splatfactow/)


#### <summary>GaussianBeV: 3D Gaussian Representation meets Perception Models for BeV Segmentation
Authors: Florian Chabot, Nicolas Granger, Guillaume Lapouge
<details span>
<summary><b>Abstract</b></summary>
The Bird's-eye View (BeV) representation is widely used for 3D perception from multi-view camera images. It allows to merge features from different cameras into a common space, providing a unified representation of the 3D scene. The key component is the view transformer, which transforms image views into the BeV. However, actual view transformer methods based on geometry or cross-attention do not provide a sufficiently detailed representation of the scene, as they use a sub-sampling of the 3D space that is non-optimal for modeling the fine structures of the environment. In this paper, we propose GaussianBeV, a novel method for transforming image features to BeV by finely representing the scene using a set of 3D gaussians located and oriented in 3D space. This representation is then splattered to produce the BeV feature map by adapting recent advances in 3D representation rendering based on gaussian splatting. GaussianBeV is the first approach to use this 3D gaussian modeling and 3D scene rendering process online, i.e. without optimizing it on a specific scene and directly integrated into a single stage model for BeV scene understanding. Experiments show that the proposed representation is highly effective and place GaussianBeV as the new state-of-the-art on the BeV semantic segmentation task on the nuScenes dataset.

![image](https://github.com/user-attachments/assets/005469fb-024a-42dd-b115-5ac666ba2bf3)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.14108) | [⌨️ Code] | [🌐 Project Page]



#### <summary>6DGS: 6D Pose Estimation from a Single Image and a 3D Gaussian Splatting Model
Authors: Matteo Bortolon, Theodore Tsesmelis, Stuart James, Fabio Poiesi, Alessio Del Bue
<details span>
<summary><b>Abstract</b></summary>
We propose 6DGS to estimate the camera pose of a target RGB image given a 3D Gaussian Splatting (3DGS) model representing the scene. 6DGS avoids the iterative process typical of analysis-by-synthesis methods (e.g. iNeRF) that also require an initialization of the camera pose in order to converge. Instead, our method estimates a 6DoF pose by inverting the 3DGS rendering process. Starting from the object surface, we define a radiant Ellicell that uniformly generates rays departing from each ellipsoid that parameterize the 3DGS model. Each Ellicell ray is associated with the rendering parameters of each ellipsoid, which in turn is used to obtain the best bindings between the target image pixels and the cast rays. These pixel-ray bindings are then ranked to select the best scoring bundle of rays, which their intersection provides the camera center and, in turn, the camera rotation. The proposed solution obviates the necessity of an "a priori" pose for initialization, and it solves 6DoF pose estimation in closed form, without the need for iterations. Moreover, compared to the existing Novel View Synthesis (NVS) baselines for pose estimation, 6DGS can improve the overall average rotational accuracy by 12% and translation accuracy by 22% on real scenes, despite not requiring any initialization pose. At the same time, our method operates near real-time, reaching 15fps on consumer hardware.

![image](https://github.com/user-attachments/assets/0a15b55d-0d93-430f-855c-5d319675b42c)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.15484) | [⌨️ Code](https://github.com/mbortolon97/6dgs) | [🌐 Project Page](https://mbortolon97.github.io/6dgs/)


#### <summary>3D Gaussian Splatting: Survey, Technologies, Challenges, and Opportunities
Authors: Yanqi Bao, Tianyu Ding, Jing Huo, Yaoli Liu, Yuxin Li, Wenbin Li, Yang Gao, Jiebo Luo
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has emerged as a prominent technique with the potential to become a mainstream method for 3D representations. It can effectively transform multi-view images into explicit 3D Gaussian representations through efficient training, and achieve real-time rendering of novel views. This survey aims to analyze existing 3DGS-related works from multiple intersecting perspectives, including related tasks, technologies, challenges, and opportunities. The primary objective is to provide newcomers with a rapid understanding of the field and to assist researchers in methodically organizing existing technologies and challenges. Specifically, we delve into the optimization, application, and extension of 3DGS, categorizing them based on their focuses or motivations. Additionally, we summarize and classify nine types of technical modules and corresponding improvements identified in existing works. Based on these analyses, we further examine the common challenges and technologies across various tasks, proposing potential research opportunities.

![image](https://github.com/user-attachments/assets/d59eba55-1d28-4f95-b566-ea37cc589ff6)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.17418) | [⌨️ Code] | [🌐 Project Page]


#### <summary>ScalingGaussian: Enhancing 3D Content Creation with Generative Gaussian Splatting
Authors: Shen Chen, Jiale Zhou, Zhongyu Jiang, Tianfang Zhang, Zongkai Wu, Jenq-Neng Hwang, Lei Li
<details span>
<summary><b>Abstract</b></summary>
The creation of high-quality 3D assets is paramount for applications in digital heritage preservation, entertainment, and robotics. Traditionally, this process necessitates skilled professionals and specialized software for the modeling, texturing, and rendering of 3D objects. However, the rising demand for 3D assets in gaming and virtual reality (VR) has led to the creation of accessible image-to-3D technologies, allowing non-professionals to produce 3D content and decreasing dependence on expert input. Existing methods for 3D content generation struggle to simultaneously achieve detailed textures and strong geometric consistency. We introduce a novel 3D content creation framework, ScalingGaussian, which combines 3D and 2D diffusion models to achieve detailed textures and geometric consistency in generated 3D assets. Initially, a 3D diffusion model generates point clouds, which are then densified through a process of selecting local regions, introducing Gaussian noise, followed by using local density-weighted selection. To refine the 3D gaussians, we utilize a 2D diffusion model with Score Distillation Sampling (SDS) loss, guiding the 3D Gaussians to clone and split. Finally, the 3D Gaussians are converted into meshes, and the surface textures are optimized using Mean Square Error(MSE) and Gradient Profile Prior(GPP) losses. Our method addresses the common issue of sparse point clouds in 3D diffusion, resulting in improved geometric structure and detailed textures. Experiments on image-to-3D tasks demonstrate that our approach efficiently generates high-quality 3D assets.

![image](https://github.com/user-attachments/assets/81caff75-261c-4689-89f2-cd27ec2e7492)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.19035) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Forecasting Future Videos from Novel Views via Disentangled 3D Scene Representation
Authors: Sudhir Yarram, Junsong Yuan
<details span>
<summary><b>Abstract</b></summary>
Video extrapolation in space and time (VEST) enables viewers to forecast a 3D scene into the future and view it from novel viewpoints. Recent methods propose to learn an entangled representation, aiming to model layered scene geometry, motion forecasting and novel view synthesis together, while assuming simplified affine motion and homography-based warping at each scene layer, leading to inaccurate video extrapolation. Instead of entangled scene representation and rendering, our approach chooses to disentangle scene geometry from scene motion, via lifting the 2D scene to 3D point clouds, which enables high quality rendering of future videos from novel views. To model future 3D scene motion, we propose a disentangled two-stage approach that initially forecasts ego-motion and subsequently the residual motion of dynamic objects (e.g., cars, people). This approach ensures more precise motion predictions by reducing inaccuracies from entanglement of ego-motion with dynamic object motion, where better ego-motion forecasting could significantly enhance the visual outcomes. Extensive experimental analysis on two urban scene datasets demonstrate superior performance of our proposed method in comparison to strong baselines.

![image](https://github.com/user-attachments/assets/1cb7333c-c0bc-4fc7-a67d-105ff143262c)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.21450) | [⌨️ Code] | [🌐 Project Page](https://skrya.github.io/projects/ffn-dsr/)


#### <summary>Localized Gaussian Splatting Editing with Contextual Awareness
>  *how to localize? using LangSplat!*

Authors: Hanyuan Xiao, Yingshu Chen, Huajian Huang, Haolin Xiong, Jing Yang, Pratusha Prasad, Yajie Zhao
<details span>
<summary><b>Abstract</b></summary>
Recent text-guided generation of individual 3D object has achieved great success using diffusion priors. However, these methods are not suitable for object insertion and replacement tasks as they do not consider the background, leading to illumination mismatches within the environment. To bridge the gap, we introduce an illumination-aware 3D scene editing pipeline for 3D Gaussian Splatting (3DGS) representation. Our key observation is that inpainting by the state-of-the-art conditional 2D diffusion model is consistent with background in lighting. To leverage the prior knowledge from the well-trained diffusion models for 3D object generation, our approach employs a coarse-to-fine objection optimization pipeline with inpainted views. In the first coarse step, we achieve image-to-3D lifting given an ideal inpainted view. The process employs 3D-aware diffusion prior from a view-conditioned diffusion model, which preserves illumination present in the conditioning image. To acquire an ideal inpainted image, we introduce an Anchor View Proposal (AVP) algorithm to find a single view that best represents the scene illumination in target region. In the second Texture Enhancement step, we introduce a novel Depth-guided Inpainting Score Distillation Sampling (DI-SDS), which enhances geometry and texture details with the inpainting diffusion prior, beyond the scope of the 3D-aware diffusion prior knowledge in the first coarse step. DI-SDS not only provides fine-grained texture enhancement, but also urges optimization to respect scene lighting. Our approach efficiently achieves local editing with global illumination consistency without explicitly modeling light transport. We demonstrate robustness of our method by evaluating editing in real scenes containing explicit highlight and shadows, and compare against the state-of-the-art text-to-3D editing methods.

![image](https://github.com/user-attachments/assets/e0663407-dedf-4aae-b8c8-066b31daf7bf)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.00083) | [⌨️ Code] | [🌐 Project Page]





#### <summary>Compact 3D Gaussian Splatting for Static and Dynamic Radiance Fields
Authors: Joo Chan Lee, Daniel Rho, Xiangyu Sun, Jong Hwan Ko, Eunbyung Park
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian splatting (3DGS) has recently emerged as an alternative representation that leverages a 3D Gaussian-based representation and introduces an approximated volumetric rendering, achieving very fast rendering speed and promising image quality. Furthermore, subsequent studies have successfully extended 3DGS to dynamic 3D scenes, demonstrating its wide range of applications. However, a significant drawback arises as 3DGS and its following methods entail a substantial number of Gaussians to maintain the high fidelity of the rendered images, which requires a large amount of memory and storage. To address this critical issue, we place a specific emphasis on two key objectives: reducing the number of Gaussian points without sacrificing performance and compressing the Gaussian attributes, such as view-dependent color and covariance. To this end, we propose a learnable mask strategy that significantly reduces the number of Gaussians while preserving high performance. In addition, we propose a compact but effective representation of view-dependent color by employing a grid-based neural field rather than relying on spherical harmonics. Finally, we learn codebooks to compactly represent the geometric and temporal attributes by residual vector quantization. With model compression techniques such as quantization and entropy coding, we consistently show over 25x reduced storage and enhanced rendering speed compared to 3DGS for static scenes, while maintaining the quality of the scene representation. For dynamic scenes, our approach achieves more than 12x storage efficiency and retains a high-quality reconstruction compared to the existing state-of-the-art methods. Our work provides a comprehensive framework for 3D scene representation, achieving high performance, fast training, compactness, and real-time rendering.

![image](https://github.com/user-attachments/assets/8385c947-f738-4ad3-9ad1-20dea8f51a20)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.03822) | [⌨️ Code] | [🌐 Project Page](https://maincold2.github.io/c3dgs/)


#### <summary>3iGS: Factorised Tensorial Illumination for 3D Gaussian Splatting
Authors: Zhe Jun Tang, Tat-Jen Cham
<details span>
<summary><b>Abstract</b></summary>
The use of 3D Gaussians as representation of radiance fields has enabled high quality novel view synthesis at real-time rendering speed. However, the choice of optimising the outgoing radiance of each Gaussian independently as spherical harmonics results in unsatisfactory view dependent effects. In response to these limitations, our work, Factorised Tensorial Illumination for 3D Gaussian Splatting, or 3iGS, improves upon 3D Gaussian Splatting (3DGS) rendering quality. Instead of optimising a single outgoing radiance parameter, 3iGS enhances 3DGS view-dependent effects by expressing the outgoing radiance as a function of a local illumination field and Bidirectional Reflectance Distribution Function (BRDF) features. We optimise a continuous incident illumination field through a Tensorial Factorisation representation, while separately fine-tuning the BRDF features of each 3D Gaussian relative to this illumination field. Our methodology significantly enhances the rendering quality of specular view-dependent effects of 3DGS, while maintaining rapid training and rendering speeds.

![image](https://github.com/user-attachments/assets/c74cbdb2-d7cf-413f-becb-f90450c76053)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.03753) | [⌨️ Code] | [🌐 Project Page]

#### <summary>RayGauss: Volumetric Gaussian-Based Ray Casting for Photorealistic Novel View Synthesis
Authors: Hugo Blanc, Jean-Emmanuel Deschaud, Alexis Paljic
<details span>
<summary><b>Abstract</b></summary>
Differentiable volumetric rendering-based methods made significant progress in novel view synthesis. On one hand, innovative methods have replaced the Neural Radiance Fields (NeRF) network with locally parameterized structures, enabling high-quality renderings in a reasonable time. On the other hand, approaches have used differentiable splatting instead of NeRF's ray casting to optimize radiance fields rapidly using Gaussian kernels, allowing for fine adaptation to the scene. However, differentiable ray casting of irregularly spaced kernels has been scarcely explored, while splatting, despite enabling fast rendering times, is susceptible to clearly visible artifacts.
Our work closes this gap by providing a physically consistent formulation of the emitted radiance c and density {\sigma}, decomposed with Gaussian functions associated with Spherical Gaussians/Harmonics for all-frequency colorimetric representation. We also introduce a method enabling differentiable ray casting of irregularly distributed Gaussians using an algorithm that integrates radiance fields slab by slab and leverages a BVH structure. This allows our approach to finely adapt to the scene while avoiding splatting artifacts. As a result, we achieve superior rendering quality compared to the state-of-the-art while maintaining reasonable training times and achieving inference speeds of 25 FPS on the Blender dataset.

![image](https://github.com/user-attachments/assets/a3168f69-8c53-4eb5-bf87-4ec4442107b7)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.03356) | [⌨️ Code] | [🌐 Project Page](https://raygauss.github.io/)

#### <summary>Evaluating Modern Approaches in 3D Scene Reconstruction: NeRF vs Gaussian-Based Methods
Authors: Yiming Zhou, Zixuan Zeng, Andi Chen, Xiaofan Zhou, Haowei Ni, Shiyao Zhang, Panfeng Li, Liangxi Liu, Mengyao Zheng, Xupeng Chen
<details span>
<summary><b>Abstract</b></summary>
Exploring the capabilities of Neural Radiance Fields (NeRF) and Gaussian-based methods in the context of 3D scene reconstruction, this study contrasts these modern approaches with traditional Simultaneous Localization and Mapping (SLAM) systems. Utilizing datasets such as Replica and ScanNet, we assess performance based on tracking accuracy, mapping fidelity, and view synthesis. Findings reveal that NeRF excels in view synthesis, offering unique capabilities in generating new perspectives from existing data, albeit at slower processing speeds. Conversely, Gaussian-based methods provide rapid processing and significant expressiveness but lack comprehensive scene completion. Enhanced by global optimization and loop closure techniques, newer methods like NICE-SLAM and SplaTAM not only surpass older frameworks such as ORB-SLAM2 in terms of robustness but also demonstrate superior performance in dynamic and complex environments. This comparative analysis bridges theoretical research with practical implications, shedding light on future developments in robust 3D scene reconstruction across various real-world applications.


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.04268) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Novel View Synthesis from a Single Image with Pretrained Diffusion Guidance
Authors: Taewon Kang, Divya Kothandaraman, Dinesh Manocha, Ming C. Lin
<details span>
<summary><b>Abstract</b></summary>
Recent 3D novel view synthesis (NVS) methods are limited to single-object-centric scenes generated from new viewpoints and struggle with complex environments. They often require extensive 3D data for training, lacking generalization beyond training distribution. Conversely, 3D-free methods can generate text-controlled views of complex, in-the-wild scenes using a pretrained stable diffusion model without tedious fine-tuning, but lack camera control. In this paper, we introduce HawkI++, a method capable of generating camera-controlled viewpoints from a single input image. HawkI++ excels in handling complex and diverse scenes without additional 3D data or extensive training. It leverages widely available pretrained NVS models for weak guidance, integrating this knowledge into a 3D-free view synthesis approach to achieve the desired results efficiently. Our experimental results demonstrate that HawkI++ outperforms existing models in both qualitative and quantitative evaluations, providing high-fidelity and consistent novel view synthesis at desired camera angles across a wide variety of scenes.

![image](https://github.com/user-attachments/assets/8b031b1b-ecf2-4ed0-aaf8-56c7e10d3df6)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.06157) | [⌨️ Code] | [🌐 Project Page]

#### <summary>HDRGS: High Dynamic Range Gaussian Splatting
Authors: Jiahao Wu, Lu Xiao, Chao Wang, Rui Peng, Kaiqiang Xiong, Ronggang Wang
<details span>
<summary><b>Abstract</b></summary>
Recent years have witnessed substantial advancements in the field of 3D reconstruction from 2D images, particularly following the introduction of the neural radiance field (NeRF) technique. However, reconstructing a 3D high dynamic range (HDR) radiance field, which aligns more closely with real-world conditions, from 2D multi-exposure low dynamic range (LDR) images continues to pose significant challenges. Approaches to this issue fall into two categories: grid-based and implicit-based. Implicit methods, using multi-layer perceptrons (MLP), face inefficiencies, limited solvability, and overfitting risks. Conversely, grid-based methods require significant memory and struggle with image quality and long training times. In this paper, we introduce Gaussian Splatting-a recent, high-quality, real-time 3D reconstruction technique-into this domain. We further develop the High Dynamic Range Gaussian Splatting (HDR-GS) method, designed to address the aforementioned challenges. This method enhances color dimensionality by including luminance and uses an asymmetric grid for tone-mapping, swiftly and precisely converting pixel irradiance to color. Our approach improves HDR scene recovery accuracy and integrates a novel coarse-to-fine strategy to speed up model convergence, enhancing robustness against sparse viewpoints and exposure extremes, and preventing local optima. Extensive testing confirms that our method surpasses current state-of-the-art techniques in both synthetic and real-world scenarios.

![image](https://github.com/user-attachments/assets/aaf6782f-a2bc-4e52-a6a5-ce841f498ca5)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.06543) | [⌨️ Code](https://github.com/WuJH2001/HDRGS) | [🌐 Project Page]


#### <summary>WaterSplatting: Fast Underwater 3D Scene Reconstruction Using Gaussian Splatting
Authors: Huapeng Li, Wenxuan Song, Tianao Xu, Alexandre Elsig, Jonas Kulhanek
<details span>
<summary><b>Abstract</b></summary>
The underwater 3D scene reconstruction is a challenging, yet interesting problem with applications ranging from naval robots to VR experiences. The problem was successfully tackled by fully volumetric NeRF-based methods which can model both the geometry and the medium (water). Unfortunately, these methods are slow to train and do not offer real-time rendering. More recently, 3D Gaussian Splatting (3DGS) method offered a fast alternative to NeRFs. However, because it is an explicit method that renders only the geometry, it cannot render the medium and is therefore unsuited for underwater reconstruction. Therefore, we propose a novel approach that fuses volumetric rendering with 3DGS to handle underwater data effectively. Our method employs 3DGS for explicit geometry representation and a separate volumetric field (queried once per pixel) for capturing the scattering medium. This dual representation further allows the restoration of the scenes by removing the scattering medium. Our method outperforms state-of-the-art NeRF-based methods in rendering quality on the underwater SeaThru-NeRF dataset. Furthermore, it does so while offering real-time rendering performance, addressing the efficiency limitations of existing methods.

![image](https://github.com/user-attachments/assets/b36a8e91-f5d3-43f7-8efa-d0e61c11a5de)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.08206) | [⌨️ Code] | [🌐 Project Page](https://water-splatting.github.io/)

#### <summary>Correspondence-Guided SfM-Free 3D Gaussian Splatting for NVS
Authors: Wei Sun, Xiaosong Zhang, Fang Wan, Yanzhao Zhou, Yuan Li, Qixiang Ye, Jianbin Jiao
<details span>
<summary><b>Abstract</b></summary>
Novel View Synthesis (NVS) without Structure-from-Motion (SfM) pre-processed camera poses--referred to as SfM-free methods--is crucial for promoting rapid response capabilities and enhancing robustness against variable operating conditions. Recent SfM-free methods have integrated pose optimization, designing end-to-end frameworks for joint camera pose estimation and NVS. However, most existing works rely on per-pixel image loss functions, such as L2 loss. In SfM-free methods, inaccurate initial poses lead to misalignment issue, which, under the constraints of per-pixel image loss functions, results in excessive gradients, causing unstable optimization and poor convergence for NVS. In this study, we propose a correspondence-guided SfM-free 3D Gaussian splatting for NVS. We use correspondences between the target and the rendered result to achieve better pixel alignment, facilitating the optimization of relative poses between frames. We then apply the learned poses to optimize the entire scene. Each 2D screen-space pixel is associated with its corresponding 3D Gaussians through approximated surface rendering to facilitate gradient back propagation. Experimental results underline the superior performance and time efficiency of the proposed approach compared to the state-of-the-art baselines.

![image](https://github.com/user-attachments/assets/1b5bc9b6-0438-42c3-aa3e-824bb59e4f2e)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.08723) | [⌨️ Code] | [🌐 Project Page]

#### <summary>GS-ID: Illumination Decomposition on Gaussian Splatting via Diffusion Prior and Parametric Light Source Optimization
Authors: Kang Du, Zhihao Liang, Zeyu Wang
<details span>
<summary><b>Abstract</b></summary>
We present GS-ID, a novel framework for illumination decomposition on Gaussian Splatting, achieving photorealistic novel view synthesis and intuitive light editing. Illumination decomposition is an ill-posed problem facing three main challenges: 1) priors for geometry and material are often lacking; 2) complex illumination conditions involve multiple unknown light sources; and 3) calculating surface shading with numerous light sources is computationally expensive. To address these challenges, we first introduce intrinsic diffusion priors to estimate the attributes for physically based rendering. Then we divide the illumination into environmental and direct components for joint optimization. Last, we employ deferred rendering to reduce the computational load. Our framework uses a learnable environment map and Spherical Gaussians (SGs) to represent light sources parametrically, therefore enabling controllable and photorealistic relighting on Gaussian Splatting. Extensive experiments and applications demonstrate that GS-ID produces state-of-the-art illumination decomposition results while achieving better geometry reconstruction and rendering performance.

![image](https://github.com/user-attachments/assets/b5a8986e-84ac-4dfa-a3e8-a50e631915c3)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.08524) | [⌨️ Code](https://github.com/dukang/GS-ID.) | [🌐 Project Page]

#### <summary>CHASE: 3D-Consistent Human Avatars with Sparse Inputs via Gaussian Splatting and Contrastive Learning
Authors: Haoyu Zhao, Hao Wang, Chen Yang, Wei Shen
<details span>
<summary><b>Abstract</b></summary>
Recent advancements in human avatar synthesis have utilized radiance fields to reconstruct photo-realistic animatable human avatars. However, both NeRFs-based and 3DGS-based methods struggle with maintaining 3D consistency and exhibit suboptimal detail reconstruction, especially with sparse inputs. To address this challenge, we propose CHASE, which introduces supervision from intrinsic 3D consistency across poses and 3D geometry contrastive learning, achieving performance comparable with sparse inputs to that with full inputs. Following previous work, we first integrate a skeleton-driven rigid deformation and a non-rigid cloth dynamics deformation to coordinate the movements of individual Gaussians during animation, reconstructing basic avatar with coarse 3D consistency. To improve 3D consistency under sparse inputs, we design Dynamic Avatar Adjustment(DAA) to adjust deformed Gaussians based on a selected similar pose/image from the dataset. Minimizing the difference between the image rendered by adjusted Gaussians and the image with the similar pose serves as an additional form of supervision for avatar. Furthermore, we propose a 3D geometry contrastive learning strategy to maintain the 3D global consistency of generated avatars. Though CHASE is designed for sparse inputs, it surprisingly outperforms current SOTA methods \textbf{in both full and sparse settings} on the ZJU-MoCap and H36M datasets, demonstrating that our CHASE successfully maintains avatar's 3D consistency, hence improving rendering quality.

![image](https://github.com/user-attachments/assets/d5900cf3-1191-4ab8-9adf-f53e5504aa0f)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.09663) | [⌨️ Code] | [🌐 Project Page]

#### <summary>ShapeSplat: A Large-scale Dataset of Gaussian Splats and Their Self-Supervised Pretraining
Authors: Qi Ma, Yue Li, Bin Ren, Nicu Sebe, Ender Konukoglu, Theo Gevers, Luc Van Gool, Danda Pani Paudel
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) has become the de facto method of 3D representation in many vision tasks. This calls for the 3D understanding directly in this representation space. To facilitate the research in this direction, we first build a large-scale dataset of 3DGS using the commonly used ShapeNet and ModelNet datasets. Our dataset ShapeSplat consists of 65K objects from 87 unique categories, whose labels are in accordance with the respective datasets. The creation of this dataset utilized the compute equivalent of 2 GPU years on a TITAN XP GPU.
We utilize our dataset for unsupervised pretraining and supervised finetuning for classification and segmentation tasks. To this end, we introduce \textbf{\textit{Gaussian-MAE}}, which highlights the unique benefits of representation learning from Gaussian parameters. Through exhaustive experiments, we provide several valuable insights. In particular, we show that (1) the distribution of the optimized GS centroids significantly differs from the uniformly sampled point cloud (used for initialization) counterpart; (2) this change in distribution results in degradation in classification but improvement in segmentation tasks when using only the centroids; (3) to leverage additional Gaussian parameters, we propose Gaussian feature grouping in a normalized feature space, along with splats pooling layer, offering a tailored solution to effectively group and embed similar Gaussians, which leads to notable improvement in finetuning tasks.

![image](https://github.com/user-attachments/assets/6401b2bf-2c62-4da8-b366-7aa0b54e0e5d)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.10906) | [⌨️ Code] | [🌐 Project Page](https://unique1i.github.io/ShapeSplat/)

#### <summary>Learning Part-aware 3D Representations by Fusing 2D Gaussians and Superquadrics
Authors: Zhirui Gao, Renjiao Yi, Yuhang Huang, Wei Chen, Chenyang Zhu, Kai Xu
<details span>
<summary><b>Abstract</b></summary>
Low-level 3D representations, such as point clouds, meshes, NeRFs, and 3D Gaussians, are commonly used to represent 3D objects or scenes. However, humans usually perceive 3D objects or scenes at a higher level as a composition of parts or structures rather than points or voxels. Representing 3D as semantic parts can benefit further understanding and applications. We aim to solve part-aware 3D reconstruction, which parses objects or scenes into semantic parts. In this paper, we introduce a hybrid representation of superquadrics and 2D Gaussians, trying to dig 3D structural clues from multi-view image inputs. Accurate structured geometry reconstruction and high-quality rendering are achieved at the same time. We incorporate parametric superquadrics in mesh forms into 2D Gaussians by attaching Gaussian centers to faces in meshes. During the training, superquadrics parameters are iteratively optimized, and Gaussians are deformed accordingly, resulting in an efficient hybrid representation. On the one hand, this hybrid representation inherits the advantage of superquadrics to represent different shape primitives, supporting flexible part decomposition of scenes. On the other hand, 2D Gaussians are incorporated to model the complex texture and geometry details, ensuring high-quality rendering and geometry reconstruction. The reconstruction is fully unsupervised. We conduct extensive experiments on data from DTU and ShapeNet datasets, in which the method decomposes scenes into reasonable parts, outperforming existing state-of-the-art approaches.

![image](https://github.com/user-attachments/assets/c9363efc-edf4-4040-bd07-1e050b5f9e47)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.10789) | [⌨️ Code] | [🌐 Project Page]

#### <summary>DeRainGS: Gaussian Splatting for Enhanced Scene Reconstruction in Rainy Environments
Authors: Shuhong Liu, Xiang Chen, Hongming Chen, Quanfeng Xu, Mingrui Li
<details span>
<summary><b>Abstract</b></summary>
Reconstruction under adverse rainy conditions poses significant challenges due to reduced visibility and the distortion of visual perception. These conditions can severely impair the quality of geometric maps, which is essential for applications ranging from autonomous planning to environmental monitoring. In response to these challenges, this study introduces the novel task of 3D Reconstruction in Rainy Environments (3DRRE), specifically designed to address the complexities of reconstructing 3D scenes under rainy conditions. To benchmark this task, we construct the HydroViews dataset that comprises a diverse collection of both synthesized and real-world scene images characterized by various intensities of rain streaks and raindrops. Furthermore, we propose DeRainGS, the first 3DGS method tailored for reconstruction in adverse rainy environments. Extensive experiments across a wide range of rain scenarios demonstrate that our method delivers state-of-the-art performance, remarkably outperforming existing occlusion-free methods.

![image](https://github.com/user-attachments/assets/1184e89e-a923-48c3-bf94-23e10705d8e2)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.11540) | [⌨️ Code] | [🌐 Project Page]


#### <summary>GSLoc: Efficient Camera Pose Refinement via 3D Gaussian Splatting
Authors: Changkun Liu, Shuai Chen, Yash Bhalgat, Siyan Hu, Zirui Wang, Ming Cheng, Victor Adrian Prisacariu, Tristan Braud
<details span>
<summary><b>Abstract</b></summary>
We leverage 3D Gaussian Splatting (3DGS) as a scene representation and propose a novel test-time camera pose refinement framework, GSLoc. This framework enhances the localization accuracy of state-of-the-art absolute pose regression and scene coordinate regression methods. The 3DGS model renders high-quality synthetic images and depth maps to facilitate the establishment of 2D-3D correspondences. GSLoc obviates the need for training feature extractors or descriptors by operating directly on RGB images, utilizing the 3D vision foundation model, MASt3R, for precise 2D matching. To improve the robustness of our model in challenging outdoor environments, we incorporate an exposure-adaptive module within the 3DGS framework. Consequently, GSLoc enables efficient pose refinement given a single RGB query and a coarse initial pose estimation. Our proposed approach surpasses leading NeRF-based optimization methods in both accuracy and runtime across indoor and outdoor visual localization benchmarks, achieving state-of-the-art accuracy on two indoor datasets.

![image](https://github.com/user-attachments/assets/a503a7df-9db5-4c70-9776-7b6a1e75e0ee)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.11085) | [⌨️ Code] | [🌐 Project Page](https://gsloc.active.vision/)

#### <summary>Subsurface Scattering for 3D Gaussian Splatting
Authors: Jan-Niklas Dihlmann, Arjun Majumdar, Andreas Engelhardt, Raphael Braun, Hendrik P.A. Lensch
<details span>
<summary><b>Abstract</b></summary>
3D reconstruction and relighting of objects made from scattering materials present a significant challenge due to the complex light transport beneath the surface. 3D Gaussian Splatting introduced high-quality novel view synthesis at real-time speeds. While 3D Gaussians efficiently approximate an object's surface, they fail to capture the volumetric properties of subsurface scattering. We propose a framework for optimizing an object's shape together with the radiance transfer field given multi-view OLAT (one light at a time) data. Our method decomposes the scene into an explicit surface represented as 3D Gaussians, with a spatially varying BRDF, and an implicit volumetric representation of the scattering component. A learned incident light field accounts for shadowing. We optimize all parameters jointly via ray-traced differentiable rendering. Our approach enables material editing, relighting and novel view synthesis at interactive rates. We show successful application on synthetic data and introduce a newly acquired multi-view multi-light dataset of objects in a light-stage setup. Compared to previous work we achieve comparable or better results at a fraction of optimization and rendering time while enabling detailed control over material attributes.

![image](https://github.com/user-attachments/assets/5748f252-f95e-4c8a-b72a-f3292d0365ab)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.12282) | [⌨️ Code](https://github.com/cgtuebingen/SSS-GS) | [🌐 Project Page](https://sss.jdihlmann.com/)

#### <summary>Atlas Gaussians Diffusion for 3D Generation with Infinite Number of Points
>  *surface parameterization*

Authors: Haitao Yang, Yuan Dong, Hanwen Jiang, Dejia Xu, Georgios Pavlakos, Qixing Huang
<details span>
<summary><b>Abstract</b></summary>
Using the latent diffusion model has proven effective in developing novel 3D generation techniques. To harness the latent diffusion model, a key challenge is designing a high-fidelity and efficient representation that links the latent space and the 3D space. In this paper, we introduce Atlas Gaussians, a novel representation for feed-forward native 3D generation. Atlas Gaussians represent a shape as the union of local patches, and each patch can decode 3D Gaussians. We parameterize a patch as a sequence of feature vectors and design a learnable function to decode 3D Gaussians from the feature vectors. In this process, we incorporate UV-based sampling, enabling the generation of a sufficiently large, and theoretically infinite, number of 3D Gaussian points. The large amount of 3D Gaussians enables high-quality details of generation results. Moreover, due to local awareness of the representation, the transformer-based decoding procedure operates on a patch level, ensuring efficiency. We train a variational autoencoder to learn the Atlas Gaussians representation, and then apply a latent diffusion model on its latent space for learning 3D Generation. Experiments show that our approach outperforms the prior arts of feed-forward native 3D generation.

![image](https://github.com/user-attachments/assets/448237ae-415a-4655-a296-0e14e206f53d)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.13055) | [⌨️ Code] | [🌐 Project Page]


#### <summary>S4D: Streaming 4D Real-World Reconstruction with Gaussians and 3D Control Points

Authors: Bing He, Yunuo Chen, Guo Lu, Li Song, Wenjun Zhang
<details span>
<summary><b>Abstract</b></summary>
Recently, the dynamic scene reconstruction using Gaussians has garnered increased interest. Mainstream approaches typically employ a global deformation field to warp a 3D scene in the canonical space. However, the inherently low-frequency nature of implicit neural fields often leads to ineffective representations of complex motions. Moreover, their structural rigidity can hinder adaptation to scenes with varying resolutions and durations. To overcome these challenges, we introduce a novel approach utilizing discrete 3D control points. This method models local rays physically and establishes a motion-decoupling coordinate system, which effectively merges traditional graphics with learnable pipelines for a robust and efficient local 6-degrees-of-freedom (6-DoF) motion representation. Additionally, we have developed a generalized framework that incorporates our control points with Gaussians. Starting from an initial 3D reconstruction, our workflow decomposes the streaming 4D real-world reconstruction into four independent submodules: 3D segmentation, 3D control points generation, object-wise motion manipulation, and residual compensation. Our experiments demonstrate that this method outperforms existing state-of-the-art 4D Gaussian Splatting techniques on both the Neu3DV and CMU-Panoptic datasets. Our approach also significantly accelerates training, with the optimization of our 3D control points achievable within just 2 seconds per frame on a single NVIDIA 4070 GPU.

![image](https://github.com/user-attachments/assets/9c27fa95-a41d-4b6c-b5cb-9ab3570781b2)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.13036) | [⌨️ Code] | [🌐 Project Page]

#### <summary>DynaSurfGS: Dynamic Surface Reconstruction with Planar-based Gaussian Splatting
>  *maybe for pose estimation*

Authors: Weiwei Cai, Weicai Ye, Peng Ye, Tong He, Tao Chen
<details span>
<summary><b>Abstract</b></summary>
Dynamic scene reconstruction has garnered significant attention in recent years due to its capabilities in high-quality and real-time rendering. Among various methodologies, constructing a 4D spatial-temporal representation, such as 4D-GS, has gained popularity for its high-quality rendered images. However, these methods often produce suboptimal surfaces, as the discrete 3D Gaussian point clouds fail to align with the object's surface precisely. To address this problem, we propose DynaSurfGS to achieve both photorealistic rendering and high-fidelity surface reconstruction of dynamic scenarios. Specifically, the DynaSurfGS framework first incorporates Gaussian features from 4D neural voxels with the planar-based Gaussian Splatting to facilitate precise surface reconstruction. It leverages normal regularization to enforce the smoothness of the surface of dynamic objects. It also incorporates the as-rigid-as-possible (ARAP) constraint to maintain the approximate rigidity of local neighborhoods of 3D Gaussians between timesteps and ensure that adjacent 3D Gaussians remain closely aligned throughout. Extensive experiments demonstrate that DynaSurfGS surpasses state-of-the-art methods in both high-fidelity surface reconstruction and photorealistic rendering.

![image](https://github.com/user-attachments/assets/dd708b66-132c-4c32-b3ae-e7c8d03c0077)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.13972) | [⌨️ Code] | [🌐 Project Page]


#### <summary>PRoGS: Progressive Rendering of Gaussian Splats
>  *By rendering each training viewpoint and calculating the contribution across all views, we create an initial ordering of the Gaussians. We further refine this by inserting all Gaussians into an octree and selecting the top contributing Gaussians per leaf node*

Authors: Brent Zoomers, Maarten Wijnants, Ivan Molenaers, Joni Vanherck, Jeroen Put, Lode Jorissen, Nick Michiels
<details span>
<summary><b>Abstract</b></summary>
Over the past year, 3D Gaussian Splatting (3DGS) has received significant attention for its ability to represent 3D scenes in a perceptually accurate manner. However, it can require a substantial amount of storage since each splat's individual data must be stored. While compression techniques offer a potential solution by reducing the memory footprint, they still necessitate retrieving the entire scene before any part of it can be rendered. In this work, we introduce a novel approach for progressively rendering such scenes, aiming to display visible content that closely approximates the final scene as early as possible without loading the entire scene into memory. This approach benefits both on-device rendering applications limited by memory constraints and streaming applications where minimal bandwidth usage is preferred. To achieve this, we approximate the contribution of each Gaussian to the final scene and construct an order of prioritization on their inclusion in the rendering process. Additionally, we demonstrate that our approach can be combined with existing compression methods to progressively render (and stream) 3DGS scenes, optimizing bandwidth usage by focusing on the most important splats within a scene. Overall, our work establishes a foundation for making remotely hosted 3DGS content more quickly accessible to end-users in over-the-top consumption scenarios, with our results showing significant improvements in quality across all metrics compared to existing methods.

![image](https://github.com/user-attachments/assets/a9004dfe-6dd5-46b7-9dae-d412c31d8207)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.01761) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Free-DyGS: Camera-Pose-Free Scene Reconstruction based on Gaussian Splatting for Dynamic Surgical Videos
>  *Generalizable Gaussian parameterization module*

Authors: Qian Li, Shuojue Yang, Daiyun Shen, Yueming Jin
<details span>
<summary><b>Abstract</b></summary>
Reconstructing endoscopic videos is crucial for high-fidelity visualization and the efficiency of surgical operations. Despite the importance, existing 3D reconstruction methods encounter several challenges, including stringent demands for accuracy, imprecise camera positioning, intricate dynamic scenes, and the necessity for rapid reconstruction. Addressing these issues, this paper presents the first camera-pose-free scene reconstruction framework, Free-DyGS, tailored for dynamic surgical videos, leveraging 3D Gaussian splatting technology. Our approach employs a frame-by-frame reconstruction strategy and is delineated into four distinct phases: Scene Initialization, Joint Learning, Scene Expansion, and Retrospective Learning. We introduce a Generalizable Gaussians Parameterization module within the Scene Initialization and Expansion phases to proficiently generate Gaussian attributes for each pixel from the RGBD frames. The Joint Learning phase is crafted to concurrently deduce scene deformation and camera pose, facilitated by an innovative flexible deformation module. In the scene expansion stage, the Gaussian points gradually grow as the camera moves. The Retrospective Learning phase is dedicated to enhancing the precision of scene deformation through the reassessment of prior frames. The efficacy of the proposed Free-DyGS is substantiated through experiments on two datasets: the StereoMIS and Hamlyn datasets. The experimental outcomes underscore that Free-DyGS surpasses conventional baseline models in both rendering fidelity and computational efficiency.

![image](https://github.com/user-attachments/assets/d4e2528b-1698-437e-a81b-4386c807efcb)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.01003) | [⌨️ Code] | [🌐 Project Page]


#### <summary>GST: Precise 3D Human Body from a Single Image with Gaussian Splatting Transformers
>  *token in transformer for gaussian attribute*

Authors: Lorenza Prospero, Abdullah Hamdi, Joao F. Henriques, Christian Rupprecht
<details span>
<summary><b>Abstract</b></summary>
Reconstructing realistic 3D human models from monocular images has significant applications in creative industries, human-computer interfaces, and healthcare. We base our work on 3D Gaussian Splatting (3DGS), a scene representation composed of a mixture of Gaussians. Predicting such mixtures for a human from a single input image is challenging, as it is a non-uniform density (with a many-to-one relationship with input pixels) with strict physical constraints. At the same time, it needs to be flexible to accommodate a variety of clothes and poses. Our key observation is that the vertices of standardized human meshes (such as SMPL) can provide an adequate density and approximate initial position for Gaussians. We can then train a transformer model to jointly predict comparatively small adjustments to these positions, as well as the other Gaussians' attributes and the SMPL parameters. We show empirically that this combination (using only multi-view supervision) can achieve fast inference of 3D human models from a single image without test-time optimization, expensive diffusion models, or 3D points supervision. We also show that it can improve 3D pose estimation by better fitting human models that account for clothes and other variations.

![image](https://github.com/user-attachments/assets/8917c584-50c3-49dc-9c35-ee65ef38a0b2)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.04196) | [⌨️ Code](https://github.com/prosperolo/GST) | [🌐 Project Page](https://abdullahamdi.com/gst/)

#### <summary>3D-GP-LMVIC: Learning-based Multi-View Image Coding with 3D Gaussian Geometric Priors
>  *compression(H264) -> redundancy between image pairs -> disparity estimation -> render depth(using 3D Gaussian as tool)*

Authors: Yujun Huang, Bin Chen, Niu Lian, Baoyi An, Shu-Tao Xia
<details span>
<summary><b>Abstract</b></summary>
Multi-view image compression is vital for 3D-related applications. To effectively model correlations between views, existing methods typically predict disparity between two views on a 2D plane, which works well for small disparities, such as in stereo images, but struggles with larger disparities caused by significant view changes. To address this, we propose a novel approach: learning-based multi-view image coding with 3D Gaussian geometric priors (3D-GP-LMVIC). Our method leverages 3D Gaussian Splatting to derive geometric priors of the 3D scene, enabling more accurate disparity estimation across views within the compression model. Additionally, we introduce a depth map compression model to reduce redundancy in geometric information between views. A multi-view sequence ordering method is also proposed to enhance correlations between adjacent views. Experimental results demonstrate that 3D-GP-LMVIC surpasses both traditional and learning-based methods in performance, while maintaining fast encoding and decoding speed.
 
![image](https://github.com/user-attachments/assets/f395b299-d12d-4d30-be0c-64322cd43060)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.04013) | [⌨️ Code](https://github.com/YujunHuang063/3D-GP-LMVIC) | [🌐 Project Page]

#### <summary>GraspSplats: Efficient Manipulation with 3D Feature Splatting

Authors: Mazeyu Ji, Ri-Zhao Qiu, Xueyan Zou, Xiaolong Wang
<details span>
<summary><b>Abstract</b></summary>
The ability for robots to perform efficient and zero-shot grasping of object parts is crucial for practical applications and is becoming prevalent with recent advances in Vision-Language Models (VLMs). To bridge the 2D-to-3D gap for representations to support such a capability, existing methods rely on neural fields (NeRFs) via differentiable rendering or point-based projection methods. However, we demonstrate that NeRFs are inappropriate for scene changes due to their implicitness and point-based methods are inaccurate for part localization without rendering-based optimization. To amend these issues, we propose GraspSplats. Using depth supervision and a novel reference feature computation method, GraspSplats generates high-quality scene representations in under 60 seconds. We further validate the advantages of Gaussian-based representation by showing that the explicit and optimized geometry in GraspSplats is sufficient to natively support (1) real-time grasp sampling and (2) dynamic and articulated object manipulation with point trackers. With extensive experiments on a Franka robot, we demonstrate that GraspSplats significantly outperforms existing methods under diverse task settings. In particular, GraspSplats outperforms NeRF-based methods like F3RM and LERF-TOGO, and 2D detection methods.
 
![image](https://github.com/user-attachments/assets/6ae58232-5d62-4669-be9f-c5ac0b50038e)


</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.02084) | [⌨️ Code](https://github.com/jimazeyu/GraspSplats) | [🌐 Project Page](https://graspsplats.github.io/)

#### <summary>GGS: Generalizable Gaussian Splatting for Lane Switching in Autonomous Driving
>*In addition, to refine the depth, we introduce a confidence based method. The lower the transparency of the predicted 3D Gaussian, the lower the confidence level of the predicted depth. virtual lane approach for large viewpoint changes. diffusion prior with lane converters.*

Authors: Huasong Han, Kaixuan Zhou, Xiaoxiao Long, Yusen Wang, Chunxia Xiao
<details span>
<summary><b>Abstract</b></summary>
We propose GGS, a Generalizable Gaussian Splatting method for Autonomous Driving which can achieve realistic rendering under large viewpoint changes. Previous generalizable 3D gaussian splatting methods are limited to rendering novel views that are very close to the original pair of images, which cannot handle large differences in viewpoint. Especially in autonomous driving scenarios, images are typically collected from a single lane. The limited training perspective makes rendering images of a different lane very challenging. To further improve the rendering capability of GGS under large viewpoint changes, we introduces a novel virtual lane generation module into GSS method to enables high-quality lane switching even without a multi-lane dataset. Besides, we design a diffusion loss to supervise the generation of virtual lane image to further address the problem of lack of data in the virtual lanes. Finally, we also propose a depth refinement module to optimize depth estimation in the GSS model. Extensive validation of our method, compared to existing approaches, demonstrates state-of-the-art performance.
 
![image](https://github.com/user-attachments/assets/2d1f1cf4-9403-40bd-ad5d-46bc12953c96)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.02382) | [⌨️ Code] | [🌐 Project Page]

#### <summary>GS-PT: Exploiting 3D Gaussian Splatting for Comprehensive Point Cloud Understanding via Self-supervised Learning
>*point cloud processing with gaussian splatting*

Authors: Keyi Liu, Yeqi Luo, Weidong Yang, Jingyi Xu, Zhijun Li, Wen-Ming Chen, Ben Fei
<details span>
<summary><b>Abstract</b></summary>
Self-supervised learning of point cloud aims to leverage unlabeled 3D data to learn meaningful representations without reliance on manual annotations. However, current approaches face challenges such as limited data diversity and inadequate augmentation for effective feature learning. To address these challenges, we propose GS-PT, which integrates 3D Gaussian Splatting (3DGS) into point cloud self-supervised learning for the first time. Our pipeline utilizes transformers as the backbone for self-supervised pre-training and introduces novel contrastive learning tasks through 3DGS. Specifically, the transformers aim to reconstruct the masked point cloud. 3DGS utilizes multi-view rendered images as input to generate enhanced point cloud distributions and novel view images, facilitating data augmentation and cross-modal contrastive learning. Additionally, we incorporate features from depth maps. By optimizing these tasks collectively, our method enriches the tri-modal self-supervised learning process, enabling the model to leverage the correlation across 3D point clouds and 2D images from various modalities. We freeze the encoder after pre-training and test the model's performance on multiple downstream tasks. Experimental results indicate that GS-PT outperforms the off-the-shelf self-supervised learning methods on various downstream tasks including 3D object classification, real-world classifications, and few-shot learning and segmentation.
 
![image](https://github.com/user-attachments/assets/11028cc2-90dc-4a8b-82e8-2f61fbe3be50)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.04963) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Fisheye-GS: Lightweight and Extensible Gaussian Splatting Module for Fisheye Cameras
>*recalculates the projection transformation and its gradients for fisheye cameras*

Authors: Zimu Liao, Siyan Chen, Rong Fu, Yi Wang, Zhongling Su, Hao Luo, Li Ma, Linning Xu, Bo Dai, Hengjie Li, Zhilin Pei, Xingcheng Zhang
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has garnered attention for its high fidelity and real-time rendering. However, adapting 3DGS to different camera models, particularly fisheye lenses, poses challenges due to the unique 3D to 2D projection calculation. Additionally, there are inefficiencies in the tile-based splatting, especially for the extreme curvature and wide field of view of fisheye lenses, which are crucial for its broader real-life applications. To tackle these challenges, we introduce Fisheye-GS.This innovative method recalculates the projection transformation and its gradients for fisheye cameras. Our approach can be seamlessly integrated as a module into other efficient 3D rendering methods, emphasizing its extensibility, lightweight nature, and modular design. Since we only modified the projection component, it can also be easily adapted for use with different camera models. Compared to methods that train after undistortion, our approach demonstrates a clear improvement in visual quality.
 
![image](https://github.com/user-attachments/assets/6f186bcd-a0f2-4d89-b1d5-0e4fab6a17a8)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.04751) | [⌨️ Code](https://github.com/zmliao/Fisheye-GS) | [🌐 Project Page]


#### <summary>Single-View 3D Reconstruction via SO(2)-Equivariant Gaussian Sculpting Networks
>*Gaussian Sculpting Network*

Authors: Ruihan Xu, Anthony Opipari, Joshua Mah, Stanley Lewis, Haoran Zhang, Hanzhe Guo, Odest Chadwicke Jenkins
<details span>
<summary><b>Abstract</b></summary>
This paper introduces SO(2)-Equivariant Gaussian Sculpting Networks (GSNs) as an approach for SO(2)-Equivariant 3D object reconstruction from single-view image observations.
GSNs take a single observation as input to generate a Gaussian splat representation describing the observed object's geometry and texture. By using a shared feature extractor before decoding Gaussian colors, covariances, positions, and opacities, GSNs achieve extremely high throughput (>150FPS). Experiments demonstrate that GSNs can be trained efficiently using a multi-view rendering loss and are competitive, in quality, with expensive diffusion-based reconstruction algorithms. The GSN model is validated on multiple benchmark experiments. Moreover, we demonstrate the potential for GSNs to be used within a robotic manipulation pipeline for object-centric grasping.

![image](https://github.com/user-attachments/assets/186d9f92-1adb-45e1-9622-ce68b02b601e)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.07245) | [⌨️ Code] | [🌐 Project Page]


#### <summary>ThermalGaussian: Thermal 3D Gaussian Splatting
>*multimodal regularization for Thremal Gaussian and RGB Gaussian*

Authors: Rongfeng Lu, Hangyu Chen, Zunjie Zhu, Yuhang Qin, Ming Lu, Le Zhang, Chenggang Yan, Anke Xue
<details span>
<summary><b>Abstract</b></summary>
Thermography is especially valuable for the military and other users of surveillance cameras. Some recent methods based on Neural Radiance Fields (NeRF) are proposed to reconstruct the thermal scenes in 3D from a set of thermal and RGB images. However, unlike NeRF, 3D Gaussian splatting (3DGS) prevails due to its rapid training and real-time rendering. In this work, we propose ThermalGaussian, the first thermal 3DGS approach capable of rendering high-quality images in RGB and thermal modalities. We first calibrate the RGB camera and the thermal camera to ensure that both modalities are accurately aligned. Subsequently, we use the registered images to learn the multimodal 3D Gaussians. To prevent the overfitting of any single modality, we introduce several multimodal regularization constraints. We also develop smoothing constraints tailored to the physical characteristics of the thermal modality. Besides, we contribute a real-world dataset named RGBT-Scenes, captured by a hand-hold thermal-infrared camera, facilitating future research on thermal scene reconstruction. We conduct comprehensive experiments to show that ThermalGaussian achieves photorealistic rendering of thermal images and improves the rendering quality of RGB images. With the proposed multimodal regularization constraints, we also reduced the model's storage cost by 90\%.

![image](https://github.com/user-attachments/assets/f0c39406-a1e3-4991-a81d-5b6e1b229fd6)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.07200) | [⌨️ Code] | [🌐 Project Page]

#### <summary>gsplat: An Open-Source Library for Gaussian Splatting
Authors: Vickie Ye, Ruilong Li, Justin Kerr, Matias Turkulainen, Brent Yi, Zhuoyang Pan, Otto Seiskari, Jianbo Ye, Jeffrey Hu, Matthew Tancik, Angjoo Kanazawa
<details span>
<summary><b>Abstract</b></summary>
gsplat is an open-source library designed for training and developing Gaussian Splatting methods. It features a front-end with Python bindings compatible with the PyTorch library and a back-end with highly optimized CUDA kernels. gsplat offers numerous features that enhance the optimization of Gaussian Splatting models, which include optimization improvements for speed, memory, and convergence times. Experimental results demonstrate that gsplat achieves up to 10% less training time and 4x less memory than the original implementation. Utilized in several research projects, gsplat is actively maintained on GitHub.

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.06765) | [⌨️ Code](https://github.com/nerfstudio-project/gsplat) | [🌐 Project Page](https://docs.gsplat.studio/main/)


#### <summary>Thermal3D-GS: Physics-induced 3D Gaussians for Thermal Infrared Novel-view Synthesis
>*modeling atmospheric transmission and thermal conduction physical processes through neural networks for Gaussian Splatting*

Authors: Qian Chen, Shihao Shu, Xiangzhi Bai
<details span>
<summary><b>Abstract</b></summary>
Novel-view synthesis based on visible light has been extensively studied. In comparison to visible light imaging, thermal infrared imaging offers the advantage of all-weather imaging and strong penetration, providing increased possibilities for reconstruction in nighttime and adverse weather scenarios. However, thermal infrared imaging is influenced by physical characteristics such as atmospheric transmission effects and thermal conduction, hindering the precise reconstruction of intricate details in thermal infrared scenes, manifesting as issues of floaters and indistinct edge features in synthesized images. To address these limitations, this paper introduces a physics-induced 3D Gaussian splatting method named Thermal3D-GS. Thermal3D-GS begins by modeling atmospheric transmission effects and thermal conduction in three-dimensional media using neural networks. Additionally, a temperature consistency constraint is incorporated into the optimization objective to enhance the reconstruction accuracy of thermal infrared images. Furthermore, to validate the effectiveness of our method, the first large-scale benchmark dataset for this field named Thermal Infrared Novel-view Synthesis Dataset (TI-NSD) is created. This dataset comprises 20 authentic thermal infrared video scenes, covering indoor, outdoor, and UAV(Unmanned Aerial Vehicle) scenarios, totaling 6,664 frames of thermal infrared image data. Based on this dataset, this paper experimentally verifies the effectiveness of Thermal3D-GS. The results indicate that our method outperforms the baseline method with a 3.03 dB improvement in PSNR and significantly addresses the issues of floaters and indistinct edge features present in the baseline method.

![image](https://github.com/user-attachments/assets/79145e3f-d43d-489a-9cc3-c2cf55f7d544)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.08042) | [⌨️ Code](https://github.com/mzzcdf/Thermal3DGS) | [🌐 Project Page]


#### <summary>SwinGS: Sliding Window Gaussian Splatting for Volumetric Video Streaming with Arbitrary Length
>*This approach necessitates the snapshot of only a small portion of the Gaussians at any given frame. This policy offers significant advantages during volumetric video streaming*

Authors: Bangya Liu, Suman Banerjee
<details span>
<summary><b>Abstract</b></summary>
Recent advances in 3D Gaussian Splatting (3DGS) have garnered significant attention in computer vision and computer graphics due to its high rendering speed and remarkable quality. While extant research has endeavored to extend the application of 3DGS from static to dynamic scenes, such efforts have been consistently impeded by excessive model sizes, constraints on video duration, and content deviation. These limitations significantly compromise the streamability of dynamic 3D Gaussian models, thereby restricting their utility in downstream applications, including volumetric video, autonomous vehicle, and immers ive technologies such as virtual, augmented, and mixed reality.
This paper introduces SwinGS, a novel framework for training, delivering, and rendering volumetric video in a real-time streaming fashion. To address the aforementioned challenges and enhance streamability, SwinGS integrates spacetime Gaussian with Markov Chain Monte Carlo (MCMC) to adapt the model to fit various 3D scenes across frames, in the meantime employing a sliding window captures Gaussian snapshots for each frame in an accumulative way. We implement a prototype of SwinGS and demonstrate its streamability across various datasets and scenes. Additionally, we develop an interactive WebGL viewer enabling real-time volumetric video playback on most devices with modern browsers, including smartphones and tablets. Experimental results show that SwinGS reduces transmission costs by 83.6% compared to previous work with ignorable compromise in PSNR. Moreover, SwinGS easily scales to long video sequences without compromising quality.

![image](https://github.com/user-attachments/assets/704114e9-3a71-4de2-a3f6-66321b0dd237)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.07759) | [⌨️ Code] | [🌐 Project Page]


#### <summary>AdR-Gaussian: Accelerating Gaussian Splatting with Adaptive Radius
> *culls pairs of Gaussian-Tile with low splatting opacity earlier in Preprocess stage, and balances the computational costs of pixel thread*

Authors: Xinzhe Wang, Ran Yi, Lizhuang Ma
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) is a recent explicit 3D representation that has achieved high-quality reconstruction and real-time rendering of complex scenes. However, the rasterization pipeline still suffers from unnecessary overhead resulting from avoidable serial Gaussian culling, and uneven load due to the distinct number of Gaussian to be rendered across pixels, which hinders wider promotion and application of 3DGS. In order to accelerate Gaussian splatting, we propose AdR-Gaussian, which moves part of serial culling in Render stage into the earlier Preprocess stage to enable parallel culling, employing adaptive radius to narrow the rendering pixel range for each Gaussian, and introduces a load balancing method to minimize thread waiting time during the pixel-parallel rendering. Our contributions are threefold, achieving a rendering speed of 310% while maintaining equivalent or even better quality than the state-of-the-art. Firstly, we propose to early cull Gaussian-Tile pairs of low splatting opacity based on an adaptive radius in the Gaussian-parallel Preprocess stage, which reduces the number of affected tile through the Gaussian bounding circle, thus reducing unnecessary overhead and achieving faster rendering speed. Secondly, we further propose early culling based on axis-aligned bounding box for Gaussian splatting, which achieves a more significant reduction in ineffective expenses by accurately calculating the Gaussian size in the 2D directions. Thirdly, we propose a balancing algorithm for pixel thread load, which compresses the information of heavy-load pixels to reduce thread waiting time, and enhance information of light-load pixels to hedge against rendering quality loss. Experiments on three datasets demonstrate that our algorithm can significantly improve the Gaussian Splatting rendering speed.

![image](https://github.com/user-attachments/assets/e9a3bd0c-4b74-4d18-a67f-8cf60f0815a0)


</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.08669) | [⌨️ Code] | [🌐 Project Page]


#### <summary>CSS: Overcoming Pose and Scene Challenges in Crowd-Sourced 3D Gaussian Splatting
> *MASt3R for intrinsics and extrinsics. These matches are critical for robust camera pose estimation*

Authors: Runze Chen, Mingyu Xiao, Haiyong Luo, Fang Zhao, Fan Wu, Hao Xiong, Qi Liu, Meng Song
<details span>
<summary><b>Abstract</b></summary>
We introduce Crowd-Sourced Splatting (CSS), a novel 3D Gaussian Splatting (3DGS) pipeline designed to overcome the challenges of pose-free scene reconstruction using crowd-sourced imagery. The dream of reconstructing historically significant but inaccessible scenes from collections of photographs has long captivated researchers. However, traditional 3D techniques struggle with missing camera poses, limited viewpoints, and inconsistent lighting. CSS addresses these challenges through robust geometric priors and advanced illumination modeling, enabling high-quality novel view synthesis under complex, real-world conditions. Our method demonstrates clear improvements over existing approaches, paving the way for more accurate and flexible applications in AR, VR, and large-scale 3D reconstruction.

![image](https://github.com/user-attachments/assets/63a50578-0e24-48f1-919e-a724b986d479)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.08562) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Robust Dual Gaussian Splatting for Immersive Human-centric Volumetric Videos
> *avatar*

Authors: Yuheng Jiang, Zhehao Shen, Yu Hong, Chengcheng Guo, Yize Wu, Yingliang Zhang, Jingyi Yu, Lan Xu
<details span>
<summary><b>Abstract</b></summary>
Volumetric video represents a transformative advancement in visual media, enabling users to freely navigate immersive virtual experiences and narrowing the gap between digital and real worlds. However, the need for extensive manual intervention to stabilize mesh sequences and the generation of excessively large assets in existing workflows impedes broader adoption. In this paper, we present a novel Gaussian-based approach, dubbed \textit{DualGS}, for real-time and high-fidelity playback of complex human performance with excellent compression ratios. Our key idea in DualGS is to separately represent motion and appearance using the corresponding skin and joint Gaussians. Such an explicit disentanglement can significantly reduce motion redundancy and enhance temporal coherence. We begin by initializing the DualGS and anchoring skin Gaussians to joint Gaussians at the first frame. Subsequently, we employ a coarse-to-fine training strategy for frame-by-frame human performance modeling. It includes a coarse alignment phase for overall motion prediction as well as a fine-grained optimization for robust tracking and high-fidelity rendering. To integrate volumetric video seamlessly into VR environments, we efficiently compress motion using entropy encoding and appearance using codec compression coupled with a persistent codebook. Our approach achieves a compression ratio of up to 120 times, only requiring approximately 350KB of storage per frame. We demonstrate the efficacy of our representation through photo-realistic, free-view experiences on VR headsets, enabling users to immersively watch musicians in performance and feel the rhythm of the notes at the performers' fingertips.

![image](https://github.com/user-attachments/assets/f6e3e61f-68c4-4ddb-8f44-5f6092ab2c89)
![image](https://github.com/user-attachments/assets/b9bbe0d0-b9a2-433f-9e07-ad010b4988c3)


</details>

[📃 arXiv:2409](https://www.arxiv.org/pdf/2409.08353) | [⌨️ Code] | [🌐 Project Page](https://nowheretrix.github.io/DualGS/)


#### <summary>GS-Net: Generalizable Plug-and-Play 3D Gaussian Splatting Module
> *designed to generate dense initial Gaussian ellipsoids and parameters from sparse SfM point clouds*

Authors: Yichen Zhang, Zihan Wang, Jiali Han, Peilin Li, Jiaxun Zhang, Jianqiang Wang, Lei He, Keqiang Li
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting (3DGS) integrates the strengths of primitive-based representations and volumetric rendering techniques, enabling real-time, high-quality rendering. However, 3DGS models typically overfit to single-scene training and are highly sensitive to the initialization of Gaussian ellipsoids, heuristically derived from Structure from Motion (SfM) point clouds, which limits both generalization and practicality. To address these limitations, we propose GS-Net, a generalizable, plug-and-play 3DGS module that densifies Gaussian ellipsoids from sparse SfM point clouds, enhancing geometric structure representation. To the best of our knowledge, GS-Net is the first plug-and-play 3DGS module with cross-scene generalization capabilities. Additionally, we introduce the CARLA-NVS dataset, which incorporates additional camera viewpoints to thoroughly evaluate reconstruction and rendering quality. Extensive experiments demonstrate that applying GS-Net to 3DGS yields a PSNR improvement of 2.08 dB for conventional viewpoints and 1.86 dB for novel viewpoints, confirming the method's effectiveness and robustness.

![image](https://github.com/user-attachments/assets/66f8275a-8559-4b0b-9165-009ae5fe98e6)


</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.11307) | [⌨️ Code] | [🌐 Project Page]



#### <summary>GStex: Per-Primitive Texturing of 2D Gaussian Splatting for Decoupled Appearance and Geometry Modeling
> *Conventional graphics representations have a clear separation between appearance and geometry. For example, vertices and faces of a triangle mesh are used to parameterize geometry, and a 2D texture map is used to parameterize appearance. decouples appearance and geometry through use of per-Gaussian texture maps. each Gaussian represents a single viewdependent color, many Gaussians are needed to model regions of a scene with high-frequency texture or spatially varying reflectance—even if the underlying geometry is simple.*

Authors: Victor Rong, Jingxiang Chen, Sherwin Bahmani, Kiriakos N. Kutulakos, David B. Lindell
<details span>
<summary><b>Abstract</b></summary>
Gaussian splatting has demonstrated excellent performance for view synthesis and scene reconstruction. The representation achieves photorealistic quality by optimizing the position, scale, color, and opacity of thousands to millions of 2D or 3D Gaussian primitives within a scene. However, since each Gaussian primitive encodes both appearance and geometry, these attributes are strongly coupled--thus, high-fidelity appearance modeling requires a large number of Gaussian primitives, even when the scene geometry is simple (e.g., for a textured planar surface). We propose to texture each 2D Gaussian primitive so that even a single Gaussian can be used to capture appearance details. By employing per-primitive texturing, our appearance representation is agnostic to the topology and complexity of the scene's geometry. We show that our approach, GStex, yields improved visual quality over prior work in texturing Gaussian splats. Furthermore, we demonstrate that our decoupling enables improved novel view synthesis performance compared to 2D Gaussian splatting when reducing the number of Gaussian primitives, and that GStex can be used for scene appearance editing and re-texturing.

![image](https://github.com/user-attachments/assets/1e10ae9f-62f7-4989-ac4d-41c741982c47)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.12954) | [⌨️ Code](https://github.com/victor-rong/GStex) | [🌐 Project Page](https://lessvrong.com/cs/gstex/)


#### <summary>3DGS-LM: Faster Gaussian-Splatting Optimization with Levenberg-Marquardt
> *change the optimizer to Levenberg-Marquardt that runs in conjunction with the 3DGS differentiable rasterizer*

Authors: Lukas Höllein, Aljaž Božič, Michael Zollhöfer, Matthias Nießner
<details span>
<summary><b>Abstract</b></summary>
We present 3DGS-LM, a new method that accelerates the reconstruction of 3D Gaussian Splatting (3DGS) by replacing its ADAM optimizer with a tailored Levenberg-Marquardt (LM). Existing methods reduce the optimization time by decreasing the number of Gaussians or by improving the implementation of the differentiable rasterizer. However, they still rely on the ADAM optimizer to fit Gaussian parameters of a scene in thousands of iterations, which can take up to an hour. To this end, we change the optimizer to LM that runs in conjunction with the 3DGS differentiable rasterizer. For efficient GPU parallization, we propose a caching data structure for intermediate gradients that allows us to efficiently calculate Jacobian-vector products in custom CUDA kernels. In every LM iteration, we calculate update directions from multiple image subsets using these kernels and combine them in a weighted mean. Overall, our method is 30% faster than the original 3DGS while obtaining the same reconstruction quality. Our optimization is also agnostic to other methods that acclerate 3DGS, thus enabling even faster speedups compared to vanilla 3DGS.

![image](https://github.com/user-attachments/assets/d301d8a2-f90b-41b3-8b1f-43fca0a03e55)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.12892) | [⌨️ Code](https://github.com/lukasHoel/3DGS-LM) | [🌐 Project Page](https://lukashoel.github.io/3DGS-LM/)

#### <summary>EdgeGaussians -- 3D Edge Mapping via Gaussian Splatting

Authors: Kunal Chelani, Assia Benbihi, Torsten Sattler, Fredrik Kahl
<details span>
<summary><b>Abstract</b></summary>
With their meaningful geometry and their omnipresence in the 3D world, edges are extremely useful primitives in computer vision. 3D edges comprise of lines and curves, and methods to reconstruct them use either multi-view images or point clouds as input. State-of-the-art image-based methods first learn a 3D edge point cloud then fit 3D edges to it. The edge point cloud is obtained by learning a 3D neural implicit edge field from which the 3D edge points are sampled on a specific level set (0 or 1). However, such methods present two important drawbacks: i) it is not realistic to sample points on exact level sets due to float imprecision and training inaccuracies. Instead, they are sampled within a range of levels so the points do not lie accurately on the 3D edges and require further processing. ii) Such implicit representations are computationally expensive and require long training times. In this paper, we address these two limitations and propose a 3D edge mapping that is simpler, more efficient, and preserves accuracy. Our method learns explicitly the 3D edge points and their edge direction hence bypassing the need for point sampling. It casts a 3D edge point as the center of a 3D Gaussian and the edge direction as the principal axis of the Gaussian. Such a representation has the advantage of being not only geometrically meaningful but also compatible with the efficient training optimization defined in Gaussian Splatting. Results show that the proposed method produces edges as accurate and complete as the state-of-the-art while being an order of magnitude faster.

![image](https://github.com/user-attachments/assets/09961333-147a-4243-ab97-ef8328dce068)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.12886) | [⌨️ Code](https://github.com/kunalchelani/EdgeGaussians) | [🌐 Project Page]


#### <summary>Spectral-GS: Taming 3D Gaussian Splatting with Spectral Entropy
>*whether to split based on the positional gradients and the spectral radius of the covariance matrix without considering the shape of primitives*

Authors: Letian Huang, Jie Guo, Jialin Dan, Ruoyu Fu, Shujie Wang, Yuanqi Li, Yanwen Guo
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3D-GS) has achieved impressive results in novel view synthesis, demonstrating high fidelity and efficiency. However, it easily exhibits needle-like artifacts, especially when increasing the sampling rate. Mip-Splatting tries to remove these artifacts with a 3D smoothing filter for frequency constraints and a 2D Mip filter for approximated supersampling. Unfortunately, it tends to produce over-blurred results, and sometimes needle-like Gaussians still persist. Our spectral analysis of the covariance matrix during optimization and densification reveals that current 3D-GS lacks shape awareness, relying instead on spectral radius and view positional gradients to determine splitting. As a result, needle-like Gaussians with small positional gradients and low spectral entropy fail to split and overfit high-frequency details. Furthermore, both the filters used in 3D-GS and Mip-Splatting reduce the spectral entropy and increase the condition number during zooming in to synthesize novel view, causing view inconsistencies and more pronounced artifacts. Our Spectral-GS, based on spectral analysis, introduces 3D shape-aware splitting and 2D view-consistent filtering strategies, effectively addressing these issues, enhancing 3D-GS's capability to represent high-frequency details without noticeable artifacts, and achieving high-quality photorealistic rendering.

![image](https://github.com/user-attachments/assets/b5f34a6e-6976-4503-8059-84c86453fd85)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.12771) | [⌨️ Code] | [🌐 Project Page]


#### <summary>V^3: Viewing Volumetric Videos on Mobiles via Streamable 2D Dynamic Gaussians
>*looks cool*

Authors: Penghao Wang, Zhirui Zhang, Liao Wang, Kaixin Yao, Siyuan Xie, Jingyi Yu, Minye Wu, Lan Xu
<details span>
<summary><b>Abstract</b></summary>
Experiencing high-fidelity volumetric video as seamlessly as 2D videos is a long-held dream. However, current dynamic 3DGS methods, despite their high rendering quality, face challenges in streaming on mobile devices due to computational and bandwidth constraints. In this paper, we introduce V^3 (Viewing Volumetric Videos), a novel approach that enables high-quality mobile rendering through the streaming of dynamic Gaussians. Our key innovation is to view dynamic 3DGS as 2D videos, facilitating the use of hardware video codecs. Additionally, we propose a two-stage training strategy to reduce storage requirements with rapid training speed. The first stage employs hash encoding and shallow MLP to learn motion, then reduces the number of Gaussians through pruning to meet the streaming requirements, while the second stage fine tunes other Gaussian attributes using residual entropy loss and temporal loss to improve temporal continuity. This strategy, which disentangles motion and appearance, maintains high rendering quality with compact storage requirements. Meanwhile, we designed a multi-platform player to decode and render 2D Gaussian videos. Extensive experiments demonstrate the effectiveness of V^3, outperforming other methods by enabling high-quality rendering and streaming on common devices, which is unseen before. As the first to stream dynamic Gaussians on mobile devices, our companion player offers users an unprecedented volumetric video experience, including smooth scrolling and instant sharing.

![image](https://github.com/user-attachments/assets/bf9ff3df-7202-45e2-8643-1be8596fbac4)


</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.13648) | [⌨️ Code] | [🌐 Project Page](https://authoritywang.github.io/v3/)

#### <summary>3D-GSW: 3D Gaussian Splatting Watermark for Protecting Copyrights in Radiance Fields

Authors: Youngdong Jang, Hyunje Park, Feng Yang, Heeju Ko, Euijin Choo, Sangpil Kim
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian splatting has been getting a lot of attention as an innovative method for representing 3D space due to rapid rendering and image quality. However, copyright protection for the 3D Gaussian splatting has not yet been introduced. In this paper, we present a novel watermarking method for 3D Gaussian splatting. The proposed method embeds a binary message into 3D Gaussians by fine-tuning the pre-trained 3D Gaussian splatting model. To achieve this, we present Frequency-Guided Densification (FGD) that utilizes Discrete Fourier Transform to find patches with high-frequencies and split 3D Gaussians based on 3D Gaussian Contribution Vector. It is each 3D Gaussian contribution to rendered pixel colors, improving both rendering quality and bit accuracy. Furthermore, we modify an adaptive gradient mask to enhance rendering quality. Our experiments show that our method can embed a watermark in 3D Gaussians imperceptibly with increased capacity and robustness against attacks. Our method reduces optimization cost and achieves state-of-the-art performance compared to other methods.

![image](https://github.com/user-attachments/assets/a81fd32d-b743-4b8d-a6af-0ab589354a3c)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.13222) | [⌨️ Code] | [🌐 Project Page]




#### <summary>AIM 2024 Sparse Neural Rendering Challenge: Dataset and Benchmark

Authors: Michal Nazarczuk, Thomas Tanay, Sibi Catley-Chandar, Richard Shaw, Radu Timofte, Eduardo Pérez-Pellitero
<details span>
<summary><b>Abstract</b></summary>
Recent developments in differentiable and neural rendering have made impressive breakthroughs in a variety of 2D and 3D tasks, e.g. novel view synthesis, 3D reconstruction. Typically, differentiable rendering relies on a dense viewpoint coverage of the scene, such that the geometry can be disambiguated from appearance observations alone. Several challenges arise when only a few input views are available, often referred to as sparse or few-shot neural rendering. As this is an underconstrained problem, most existing approaches introduce the use of regularisation, together with a diversity of learnt and hand-crafted priors. A recurring problem in sparse rendering literature is the lack of an homogeneous, up-to-date, dataset and evaluation protocol. While high-resolution datasets are standard in dense reconstruction literature, sparse rendering methods often evaluate with low-resolution images. Additionally, data splits are inconsistent across different manuscripts, and testing ground-truth images are often publicly available, which may lead to over-fitting. In this work, we propose the Sparse Rendering (SpaRe) dataset and benchmark. We introduce a new dataset that follows the setup of the DTU MVS dataset. The dataset is composed of 97 new scenes based on synthetic, high-quality assets. Each scene has up to 64 camera views and 7 lighting configurations, rendered at 1600x1200 resolution. We release a training split of 82 scenes to foster generalizable approaches, and provide an online evaluation platform for the validation and test sets, whose ground-truth images remain hidden. We propose two different sparse configurations (3 and 9 input images respectively). This provides a powerful and convenient tool for reproducible evaluation, and enable researchers easy access to a public leaderboard with the state-of-the-art performance scores.

![image](https://github.com/user-attachments/assets/2c3b4d62-a380-4b01-ba47-fc8ca9cce42b)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.15041) | [⌨️ Code] | [🌐 Project Page](https://sparebenchmark.github.io/)


#### <summary>Dynamic 2D Gaussians: Geometrically accurate radiance fields for dynamic objects

Authors: Shuai Zhang, Guanjun Wu, Xinggang Wang, Bin Feng, Wenyu Liu
<details span>
<summary><b>Abstract</b></summary>
Reconstructing objects and extracting high-quality surfaces play a vital role in the real world. Current 4D representations show the ability to render high-quality novel views for dynamic objects but cannot reconstruct high-quality meshes due to their implicit or geometrically inaccurate representations. In this paper, we propose a novel representation that can reconstruct accurate meshes from sparse image input, named Dynamic 2D Gaussians (D-2DGS). We adopt 2D Gaussians for basic geometry representation and use sparse-controlled points to capture 2D Gaussian's deformation. By extracting the object mask from the rendered high-quality image and masking the rendered depth map, a high-quality dynamic mesh sequence of the object can be extracted. Experiments demonstrate that our D-2DGS is outstanding in reconstructing high-quality meshes from sparse input.

![image](https://github.com/user-attachments/assets/f8787304-4918-4e56-8928-f6829d6c1a47)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.14072) | [⌨️ Code](https://github.com/hustvl/Dynamic-2DGS) | [🌐 Project 
Page]


#### <summary>Disentangled Generation and Aggregation for Robust Radiance Fields

Authors: Shihe Shen, Huachen Gao, Wangze Xu, Rui Peng, Luyang Tang, Kaiqiang Xiong, Jianbo Jiao, Ronggang Wang
<details span>
<summary><b>Abstract</b></summary>
The utilization of the triplane-based radiance fields has gained attention in recent years due to its ability to effectively disentangle 3D scenes with a high-quality representation and low computation cost. A key requirement of this method is the precise input of camera poses. However, due to the local update property of the triplane, a similar joint estimation as previous joint pose-NeRF optimization works easily results in local minima. To this end, we propose the Disentangled Triplane Generation module to introduce global feature context and smoothness into triplane learning, which mitigates errors caused by local updating. Then, we propose the Disentangled Plane Aggregation to mitigate the entanglement caused by the common triplane feature aggregation during camera pose updating. In addition, we introduce a two-stage warm-start training strategy to reduce the implicit constraints caused by the triplane generator. Quantitative and qualitative results demonstrate that our proposed method achieves state-of-the-art performance in novel view synthesis with noisy or unknown camera poses, as well as efficient convergence of optimization.

![image](https://github.com/user-attachments/assets/b986ceb9-f672-44f0-9ccb-6145a8d46fe7)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.15715) | [⌨️ Code] | [🌐 Project Page](https://gaohchen.github.io/DiGARR/)



#### <summary>DreamWaltz-G: Expressive 3D Gaussian Avatars from Skeleton-Guided 2D Diffusion

Authors: Yukun Huang, Jianan Wang, Ailing Zeng, Zheng-Jun Zha, Lei Zhang, Xihui Liu
<details span>
<summary><b>Abstract</b></summary>
Leveraging pretrained 2D diffusion models and score distillation sampling (SDS), recent methods have shown promising results for text-to-3D avatar generation. However, generating high-quality 3D avatars capable of expressive animation remains challenging. In this work, we present DreamWaltz-G, a novel learning framework for animatable 3D avatar generation from text. The core of this framework lies in Skeleton-guided Score Distillation and Hybrid 3D Gaussian Avatar representation. Specifically, the proposed skeleton-guided score distillation integrates skeleton controls from 3D human templates into 2D diffusion models, enhancing the consistency of SDS supervision in terms of view and human pose. This facilitates the generation of high-quality avatars, mitigating issues such as multiple faces, extra limbs, and blurring. The proposed hybrid 3D Gaussian avatar representation builds on the efficient 3D Gaussians, combining neural implicit fields and parameterized 3D meshes to enable real-time rendering, stable SDS optimization, and expressive animation. Extensive experiments demonstrate that DreamWaltz-G is highly effective in generating and animating 3D avatars, outperforming existing methods in both visual quality and animation expressiveness. Our framework further supports diverse applications, including human video reenactment and multi-subject scene composition.

![image](https://github.com/user-attachments/assets/3ae78726-8365-4309-8a97-75a73ec01545)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.17145) | [⌨️ Code](https://github.com/yukun-huang/DreamWaltz-G) | [🌐 Project Page](https://yukun-huang.github.io/DreamWaltz-G/)


#### <summary>Frequency-based View Selection in Gaussian Splatting Reconstruction
>*Next-best-view Selection for gaussian splatting*

Authors: Monica M.Q. Li, Pierre-Yves Lajoie, Giovanni Beltrame
<details span>
<summary><b>Abstract</b></summary>
Three-dimensional reconstruction is a fundamental problem in robotics perception. We examine the problem of active view selection to perform 3D Gaussian Splatting reconstructions with as few input images as possible. Although 3D Gaussian Splatting has made significant progress in image rendering and 3D reconstruction, the quality of the reconstruction is strongly impacted by the selection of 2D images and the estimation of camera poses through Structure-from-Motion (SfM) algorithms. Current methods to select views that rely on uncertainties from occlusions, depth ambiguities, or neural network predictions directly are insufficient to handle the issue and struggle to generalize to new scenes. By ranking the potential views in the frequency domain, we are able to effectively estimate the potential information gain of new viewpoints without ground truth data. By overcoming current constraints on model architecture and efficacy, our method achieves state-of-the-art results in view selection, demonstrating its potential for efficient image-based 3D reconstruction.

![image](https://github.com/user-attachments/assets/f673c168-b208-42cf-ac3c-95d467a9933a)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.16470) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Gaussian-Det: Learning Closed-Surface Gaussians for 3D Object Detection
>*Closure Inference Module (CIM), come back later*

Authors: Hongru Yan, Yu Zheng, Yueqi Duan
<details span>
<summary><b>Abstract</b></summary>
Skins wrapping around our bodies, leathers covering over the sofa, sheet metal coating the car - it suggests that objects are enclosed by a series of continuous surfaces, which provides us with informative geometry prior for objectness deduction. In this paper, we propose Gaussian-Det which leverages Gaussian Splatting as surface representation for multi-view based 3D object detection. Unlike existing monocular or NeRF-based methods which depict the objects via discrete positional data, Gaussian-Det models the objects in a continuous manner by formulating the input Gaussians as feature descriptors on a mass of partial surfaces. Furthermore, to address the numerous outliers inherently introduced by Gaussian splatting, we accordingly devise a Closure Inferring Module (CIM) for the comprehensive surface-based objectness deduction. CIM firstly estimates the probabilistic feature residuals for partial surfaces given the underdetermined nature of Gaussian Splatting, which are then coalesced into a holistic representation on the overall surface closure of the object proposal. In this way, the surface information Gaussian-Det exploits serves as the prior on the quality and reliability of objectness and the information basis of proposal refinement. Experiments on both synthetic and real-world datasets demonstrate that Gaussian-Det outperforms various existing approaches, in terms of both average precision and recall.

![image](https://github.com/user-attachments/assets/76cfc0b5-7982-4546-a13b-665f05384bc0)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.01404) | [⌨️ Code] | [🌐 Project Page]


#### <summary>3DGS-DET: Empower 3D Gaussian Splatting with Boundary Guidance and Box-Focused Sampling for 3D Object Detection
>*incorporating 2D Boundary Guidance to achieve a more suitable 3D spatial distribution of Gaussian blobs for detection*

Authors: Yang Cao, Yuanliang Jv, Dan Xu
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRF) are widely used for novel-view synthesis and have been adapted for 3D Object Detection (3DOD), offering a promising approach to 3DOD through view-synthesis representation. However, NeRF faces inherent limitations: (i) limited representational capacity for 3DOD due to its implicit nature, and (ii) slow rendering speeds. Recently, 3D Gaussian Splatting (3DGS) has emerged as an explicit 3D representation that addresses these limitations. Inspired by these advantages, this paper introduces 3DGS into 3DOD for the first time, identifying two main challenges: (i) Ambiguous spatial distribution of Gaussian blobs: 3DGS primarily relies on 2D pixel-level supervision, resulting in unclear 3D spatial distribution of Gaussian blobs and poor differentiation between objects and background, which hinders 3DOD; (ii) Excessive background blobs: 2D images often include numerous background pixels, leading to densely reconstructed 3DGS with many noisy Gaussian blobs representing the background, negatively affecting detection. To tackle the challenge (i), we leverage the fact that 3DGS reconstruction is derived from 2D images, and propose an elegant and efficient solution by incorporating 2D Boundary Guidance to significantly enhance the spatial distribution of Gaussian blobs, resulting in clearer differentiation between objects and their background. To address the challenge (ii), we propose a Box-Focused Sampling strategy using 2D boxes to generate object probability distribution in 3D spaces, allowing effective probabilistic sampling in 3D to retain more object blobs and reduce noisy background blobs. Benefiting from our designs, our 3DGS-DET significantly outperforms the SOTA NeRF-based method, NeRF-Det, achieving improvements of +6.6 on mAP@0.25 and +8.1 on mAP@0.5 for the ScanNet dataset, and impressive +31.5 on mAP@0.25 for the ARKITScenes dataset.

![image](https://github.com/user-attachments/assets/d05a5ab4-8ecd-4f1d-8605-c20984d83099)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.01647) | [⌨️ Code](https://arxiv.org/pdf/2410.01647) | [🌐 Project Page]

#### <summary>MVGS: Multi-view-regulated Gaussian Splatting for Novel View Synthesis
>*interesting!!!*

Authors: Xiaobiao Du, Yida Wang, Xin Yu
<details span>
<summary><b>Abstract</b></summary>
Recent works in volume rendering, \textit{e.g.} NeRF and 3D Gaussian Splatting (3DGS), significantly advance the rendering quality and efficiency with the help of the learned implicit neural radiance field or 3D Gaussians. Rendering on top of an explicit representation, the vanilla 3DGS and its variants deliver real-time efficiency by optimizing the parametric model with single-view supervision per iteration during training which is adopted from NeRF. Consequently, certain views are overfitted, leading to unsatisfying appearance in novel-view synthesis and imprecise 3D geometries. To solve aforementioned problems, we propose a new 3DGS optimization method embodying four key novel contributions: 1) We transform the conventional single-view training paradigm into a multi-view training strategy. With our proposed multi-view regulation, 3D Gaussian attributes are further optimized without overfitting certain training views. As a general solution, we improve the overall accuracy in a variety of scenarios and different Gaussian variants. 2) Inspired by the benefit introduced by additional views, we further propose a cross-intrinsic guidance scheme, leading to a coarse-to-fine training procedure concerning different resolutions. 3) Built on top of our multi-view regulated training, we further propose a cross-ray densification strategy, densifying more Gaussian kernels in the ray-intersect regions from a selection of views. 4) By further investigating the densification strategy, we found that the effect of densification should be enhanced when certain views are distinct dramatically. As a solution, we propose a novel multi-view augmented densification strategy, where 3D Gaussians are encouraged to get densified to a sufficient number accordingly, resulting in improved reconstruction accuracy.

![image](https://github.com/user-attachments/assets/96d5a43e-ee55-4893-ac2f-28e9b83ae42e)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.02103) | [⌨️ Code](https://github.com/xiaobiaodu/MVGS) | [🌐 Project Page](https://xiaobiaodu.github.io/mvgs-project/)


#### <summary>SuperGS: Super-Resolution 3D Gaussian Splatting via Latent Feature Field and Gradient-guided Splitting

Authors: Shiyun Xie, Zhiru Wang, Yinghao Zhu, Chengwei Pan
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has exceled in novel view synthesis with its real-time rendering capabilities and superior quality. However, it faces challenges for high-resolution novel view synthesis (HRNVS) due to the coarse nature of primitives derived from low-resolution input views. To address this issue, we propose Super-Resolution 3DGS (SuperGS), which is an expansion of 3DGS designed with a two-stage coarse-to-fine training framework, utilizing pretrained low-resolution scene representation as an initialization for super-resolution optimization. Moreover, we introduce Multi-resolution Feature Gaussian Splatting (MFGS) to incorporates a latent feature field for flexible feature sampling and Gradient-guided Selective Splitting (GSS) for effective Gaussian upsampling. By integrating these strategies within the coarse-to-fine framework ensure both high fidelity and memory efficiency. Extensive experiments demonstrate that SuperGS surpasses state-of-the-art HRNVS methods on challenging real-world datasets using only low-resolution inputs.

![image](https://github.com/user-attachments/assets/014e78ad-788f-4774-b495-2ec10c8ab1c0)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.02571) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Flash-Splat: 3D Reflection Removal with Flash Cues and Gaussian Splats

Authors: Mingyang Xie, Haoming Cai, Sachin Shah, Yiran Xu, Brandon Y. Feng, Jia-Bin Huang, Christopher A. Metzler
<details span>
<summary><b>Abstract</b></summary>
We introduce a simple yet effective approach for separating transmitted and reflected light. Our key insight is that the powerful novel view synthesis capabilities provided by modern inverse rendering methods (e.g.,~3D Gaussian splatting) allow one to perform flash/no-flash reflection separation using unpaired measurements -- this relaxation dramatically simplifies image acquisition over conventional paired flash/no-flash reflection separation methods. Through extensive real-world experiments, we demonstrate our method, Flash-Splat, accurately reconstructs both transmitted and reflected scenes in 3D. Our method outperforms existing 3D reflection separation methods, which do not leverage illumination control, by a large margin.

![image](https://github.com/user-attachments/assets/014e78ad-788f-4774-b495-2ec10c8ab1c0)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.02764) | [⌨️ Code] | [🌐 Project Page](https://flash-splat.github.io/)



#### <summary>Depth Estimation Based on 3D Gaussian Splatting Siamese Defocus
>*monocular depth metric estimation. Circle of Confusion (CoC)*

Authors: Jinchang Zhang, Ningning Xu, Hao Zhang, Guoyu Lu
<details span>
<summary><b>Abstract</b></summary>
Depth estimation is a fundamental task in 3D geometry. While stereo depth estimation can be achieved through triangulation methods, it is not as straightforward for monocular methods, which require the integration of global and local information. The Depth from Defocus (DFD) method utilizes camera lens models and parameters to recover depth information from blurred images and has been proven to perform well. However, these methods rely on All-In-Focus (AIF) images for depth estimation, which is nearly impossible to obtain in real-world applications. To address this issue, we propose a self-supervised framework based on 3D Gaussian splatting and Siamese networks. By learning the blur levels at different focal distances of the same scene in the focal stack, the framework predicts the defocus map and Circle of Confusion (CoC) from a single defocused image, using the defocus map as input to DepthNet for monocular depth estimation. The 3D Gaussian splatting model renders defocused images using the predicted CoC, and the differences between these and the real defocused images provide additional supervision signals for the Siamese Defocus self-supervised network. This framework has been validated on both artificially synthesized and real blurred datasets. Subsequent quantitative and visualization experiments demonstrate that our proposed framework is highly effective as a DFD method.

![image](https://github.com/user-attachments/assets/7afdc16b-22c4-4df5-9c99-085e2344201f)


</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.12323) | [⌨️ Code] | [🌐 Project Page]




<br>
<br>




## Not Gaussian



### NVS



#### <summary>NoPe-NeRF: Optimising Neural Radiance Field with No Pose Prior
Authors: Wenjing Bian, Zirui Wang, Kejie Li, Jia-Wang Bian, Victor Adrian Prisacariu
<details span>
<summary><b>Abstract</b></summary>
Training a Neural Radiance Field (NeRF) without pre-computed camera poses is challenging. Recent advances in this direction demonstrate the possibility of jointly optimising a NeRF and camera poses in forward-facing scenes. However, these methods still face difficulties during dramatic camera movement. We tackle this challenging problem by incorporating undistorted monocular depth priors. These priors are generated by correcting scale and shift parameters during training, with which we are then able to constrain the relative poses between consecutive frames. This constraint is achieved using our proposed novel loss functions. Experiments on real-world indoor and outdoor scenes show that our method can handle challenging camera trajectories and outperforms existing methods in terms of novel view rendering quality and pose estimation accuracy.

![image](https://github.com/user-attachments/assets/3bc5e43c-a5ef-4b69-84ea-61196bed850d)


</details>

[📃 arXiv:2212](https://arxiv.org/pdf/2212.07388) | [⌨️ Code](https://github.com/ActiveVisionLab/nope-nerf/) | [🌐 Project Page](https://nope-nerf.active.vision/)



#### <summary>MixNeRF: Modeling a Ray with Mixture Density for Novel View Synthesis from Sparse Inputs
Authors: Seunghyeon Seo, Donghoon Han, Yeonjin Chang, Nojun Kwak
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Field (NeRF) has broken new ground in the novel view synthesis due to its simple concept and state-of-the-art quality. However, it suffers from severe performance degradation unless trained with a dense set of images with different camera poses, which hinders its practical applications. Although previous methods addressing this problem achieved promising results, they relied heavily on the additional training resources, which goes against the philosophy of sparse-input novel-view synthesis pursuing the training efficiency. In this work, we propose MixNeRF, an effective training strategy for novel view synthesis from sparse inputs by modeling a ray with a mixture density model. Our MixNeRF estimates the joint distribution of RGB colors along the ray samples by modeling it with mixture of distributions. We also propose a new task of ray depth estimation as a useful training objective, which is highly correlated with 3D scene geometry. Moreover, we remodel the colors with regenerated blending weights based on the estimated ray depth and further improves the robustness for colors and viewpoints. Our MixNeRF outperforms other state-of-the-art methods in various standard benchmarks with superior efficiency of training and inference.

![image](https://github.com/user-attachments/assets/82a5f8e6-94b5-44b8-95f3-22a9c66cc84f)

</details>

[📃 arXiv:2302](https://arxiv.org/pdf/2302.08788) | [⌨️ Code](https://github.com/shawn615/MixNeRF/tree/main?tab=readme-ov-file) | [🌐 Project Page](https://shawn615.github.io/mixnerf/)




#### <summary>DiffusioNeRF: Regularizing Neural Radiance Fields with Denoising Diffusion Models
Authors: Jamie Wynn, Daniyar Turmukhambetov
<details span>
<summary><b>Abstract</b></summary>
Under good conditions, Neural Radiance Fields (NeRFs) have shown impressive results on novel view synthesis tasks. NeRFs learn a scene's color and density fields by minimizing the photometric discrepancy between training views and differentiable renderings of the scene. Once trained from a sufficient set of views, NeRFs can generate novel views from arbitrary camera positions. However, the scene geometry and color fields are severely under-constrained, which can lead to artifacts, especially when trained with few input views.
To alleviate this problem we learn a prior over scene geometry and color, using a denoising diffusion model (DDM). Our DDM is trained on RGBD patches of the synthetic Hypersim dataset and can be used to predict the gradient of the logarithm of a joint probability distribution of color and depth patches. We show that, these gradients of logarithms of RGBD patch priors serve to regularize geometry and color of a scene. During NeRF training, random RGBD patches are rendered and the estimated gradient of the log-likelihood is backpropagated to the color and density fields. Evaluations on LLFF, the most relevant dataset, show that our learned prior achieves improved quality in the reconstructed geometry and improved generalization to novel views. Evaluations on DTU show improved reconstruction quality among NeRF methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/b6b3c6c4-7fef-4ea5-842c-d23199306985)

</details>

[📃 arXiv:2302](https://arxiv.org/pdf/2302.12231) | [⌨️ Code](https://www.github.com/nianticlabs/diffusionerf) | [🌐 Project Page]



#### <summary>FouriScale: A Frequency Perspective on Training-Free High-Resolution Image Synthesis
Authors: Linjiang Huang, Rongyao Fang, Aiping Zhang, Guanglu Song, Si Liu, Yu Liu, Hongsheng Li
<details span>
<summary><b>Abstract</b></summary>
In this study, we delve into the generation of high-resolution images from pre-trained diffusion models, addressing persistent challenges, such as repetitive patterns and structural distortions, that emerge when models are applied beyond their trained resolutions. To address this issue, we introduce an innovative, training-free approach FouriScale from the perspective of frequency domain analysis. We replace the original convolutional layers in pre-trained diffusion models by incorporating a dilation technique along with a low-pass operation, intending to achieve structural consistency and scale consistency across resolutions, respectively. Further enhanced by a padding-then-crop strategy, our method can flexibly handle text-to-image generation of various aspect ratios. By using the FouriScale as guidance, our method successfully balances the structural integrity and fidelity of generated images, achieving an astonishing capacity of arbitrary-size, high-resolution, and high-quality generation. With its simplicity and compatibility, our method can provide valuable insights for future explorations into the synthesis of ultra-high-resolution images.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/9286c6c4-2d8d-415b-a784-8ac94212f575)


 
</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.12963.pdf) | [⌨️ Code](https://github.com/LeonHLJ/FouriScale) | [🌐 Project Page]


#### <summary>XScale-NVS: Cross-Scale Novel View Synthesis with Hash Featurized Manifold
Authors: Guangyu Wang, Jinzhi Zhang, Fan Wang, Ruqi Huang, Lu Fang
<details span>
<summary><b>Abstract</b></summary>
We propose XScale-NVS for high-fidelity cross-scale novel view synthesis of real-world large-scale scenes. Existing representations based on explicit surface suffer from discretization resolution or UV distortion, while implicit volumetric representations lack scalability for large scenes due to the dispersed weight distribution and surface ambiguity. In light of the above challenges, we introduce hash featurized manifold, a novel hash-based featurization coupled with a deferred neural rendering framework. This approach fully unlocks the expressivity of the representation by explicitly concentrating the hash entries on the 2D manifold, thus effectively representing highly detailed contents independent of the discretization resolution. We also introduce a novel dataset, namely GigaNVS, to benchmark cross-scale, high-resolution novel view synthesis of realworld large-scale scenes. Our method significantly outperforms competing baselines on various real-world scenes, yielding an average LPIPS that is 40% lower than prior state-of-the-art on the challenging GigaNVS benchmark.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/470fcbba-6f21-42d1-a4b4-599df025e624)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.19517) | [⌨️ Code](https://github.com/THU-luvision/XScale-NVS) | [🌐 Project Page](https://xscalenvs.github.io/)

#### <summary>Aerial-NeRF: Adaptive Spatial Partitioning and Sampling for Large-Scale Aerial Rendering
Authors: Xiaohan Zhang, Yukui Qiu, Zhenyu Sun, Qi Liu
<details span>
<summary><b>Abstract</b></summary>
Recent progress in large-scale scene rendering has yielded Neural Radiance Fields (NeRF)-based models with an impressive ability to synthesize scenes across small objects and indoor scenes. Nevertheless, extending this idea to large-scale aerial rendering poses two critical problems. Firstly, a single NeRF cannot render the entire scene with high-precision for complex large-scale aerial datasets since the sampling range along each view ray is insufficient to cover buildings adequately. Secondly, traditional NeRFs are infeasible to train on one GPU to enable interactive fly-throughs for modeling massive images. Instead, existing methods typically separate the whole scene into multiple regions and train a NeRF on each region, which are unaccustomed to different flight trajectories and difficult to achieve fast rendering. To that end, we propose Aerial-NeRF with three innovative modifications for jointly adapting NeRF in large-scale aerial rendering: (1) Designing an adaptive spatial partitioning and selection method based on drones' poses to adapt different flight trajectories; (2) Using similarity of poses instead of (expert) network for rendering speedup to determine which region a new viewpoint belongs to; (3) Developing an adaptive sampling approach for rendering performance improvement to cover the entire buildings at different heights. Extensive experiments have conducted to verify the effectiveness and efficiency of Aerial-NeRF, and new state-of-the-art results have been achieved on two public large-scale aerial datasets and presented SCUTic dataset. Note that our model allows us to perform rendering over 4 times as fast as compared to multiple competitors.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/6bf1d383-7d7d-4395-9ed8-01690ae7065b)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.06214) | [⌨️ Code] | [🌐 Project Page]



#### <summary>NVS-Solver: Video Diffusion Model as Zero-Shot Novel View Synthesizer
Authors: Meng You, Zhiyu Zhu, Hui Liu, Junhui Hou
<details span>
<summary><b>Abstract</b></summary>
By harnessing the potent generative capabilities of pre-trained large video diffusion models, we propose NVS-Solver, a new novel view synthesis (NVS) paradigm that operates \textit{without} the need for training. NVS-Solver adaptively modulates the diffusion sampling process with the given views to enable the creation of remarkable visual experiences from single or multiple views of static scenes or monocular videos of dynamic scenes. Specifically, built upon our theoretical modeling, we iteratively modulate the score function with the given scene priors represented with warped input views to control the video diffusion process. Moreover, by theoretically exploring the boundary of the estimation error, we achieve the modulation in an adaptive fashion according to the view pose and the number of diffusion steps. Extensive evaluations on both static and dynamic scenes substantiate the significant superiority of our NVS-Solver over state-of-the-art methods both quantitatively and qualitatively.

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.15364) | [⌨️ Code](https://github.com/ZHU-Zhiyu/NVS_Solver) | [🌐 Project Page]





#### <summary>Generative Lifting of Multiview to 3D from Unknown Pose: Wrapping NeRF inside Diffusion
Authors: Xin Yuan, Rana Hanocka, Michael Maire
<details span>
<summary><b>Abstract</b></summary>
We cast multiview reconstruction from unknown pose as a generative modeling problem. From a collection of unannotated 2D images of a scene, our approach simultaneously learns both a network to predict camera pose from 2D image input, as well as the parameters of a Neural Radiance Field (NeRF) for the 3D scene. To drive learning, we wrap both the pose prediction network and NeRF inside a Denoising Diffusion Probabilistic Model (DDPM) and train the system via the standard denoising objective. Our framework requires the system accomplish the task of denoising an input 2D image by predicting its pose and rendering the NeRF from that pose. Learning to denoise thus forces the system to concurrently learn the underlying 3D NeRF representation and a mapping from images to camera extrinsic parameters. To facilitate the latter, we design a custom network architecture to represent pose as a distribution, granting implicit capacity for discovering view correspondences when trained end-to-end for denoising alone. This technique allows our system to successfully build NeRFs, without pose knowledge, for challenging scenes where competing methods fail. At the conclusion of training, our learned NeRF can be extracted and used as a 3D scene model; our full system can be used to sample novel camera poses and generate novel-view images.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/dff892ae-98e8-456b-b9ea-554d05c1be3e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.06972) | [⌨️ Code] | [🌐 Project Page]




#### <summary>MultiDiff: Consistent Novel View Synthesis from a Single Image
Authors: Norman Müller, Katja Schwarz, Barbara Roessle, Lorenzo Porzi, Samuel Rota Bulò, Matthias Nießner, Peter Kontschieder
<details span>
<summary><b>Abstract</b></summary>
We introduce MultiDiff, a novel approach for consistent novel view synthesis of scenes from a single RGB image. The task of synthesizing novel views from a single reference image is highly ill-posed by nature, as there exist multiple, plausible explanations for unobserved areas. To address this issue, we incorporate strong priors in form of monocular depth predictors and video-diffusion models. Monocular depth enables us to condition our model on warped reference images for the target views, increasing geometric stability. The video-diffusion prior provides a strong proxy for 3D scenes, allowing the model to learn continuous and pixel-accurate correspondences across generated images. In contrast to approaches relying on autoregressive image generation that are prone to drifts and error accumulation, MultiDiff jointly synthesizes a sequence of frames yielding high-quality and multi-view consistent results -- even for long-term scene generation with large camera movements, while reducing inference time by an order of magnitude. For additional consistency and image quality improvements, we introduce a novel, structured noise distribution. Our experimental results demonstrate that MultiDiff outperforms state-of-the-art methods on the challenging, real-world datasets RealEstate10K and ScanNet. Finally, our model naturally supports multi-view consistent editing without the need for further tuning.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ba69a9b1-29fe-41b6-a92d-cec31209b0c3)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.18524) | [⌨️ Code] | [🌐 Project Page](https://sirwyver.github.io/MultiDiff)





#### <summary>ExtraNeRF: Visibility-Aware View Extrapolation of Neural Radiance Fields with Diffusion Models
Authors: Meng-Li Shih, Wei-Chiu Ma, Lorenzo Boyice, Aleksander Holynski, Forrester Cole, Brian L. Curless, Janne Kontkanen
<details span>
<summary><b>Abstract</b></summary>
We propose ExtraNeRF, a novel method for extrapolating the range of views handled by a Neural Radiance Field (NeRF). Our main idea is to leverage NeRFs to model scene-specific, fine-grained details, while capitalizing on diffusion models to extrapolate beyond our observed data. A key ingredient is to track visibility to determine what portions of the scene have not been observed, and focus on reconstructing those regions consistently with diffusion models. Our primary contributions include a visibility-aware diffusion-based inpainting module that is fine-tuned on the input imagery, yielding an initial NeRF with moderate quality (often blurry) inpainted regions, followed by a second diffusion model trained on the input imagery to consistently enhance, notably sharpen, the inpainted imagery from the first pass. We demonstrate high-quality results, extrapolating beyond a small number of (typically six or fewer) input views, effectively outpainting the NeRF as well as inpainting newly disoccluded regions inside the original viewing volume. We compare with related work both quantitatively and qualitatively and show significant gains over prior art.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/48598b65-bca0-43f5-a179-905cab25cf9d)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.06133) | [⌨️ Code] | [🌐 Project Page](https://shihmengli.github.io/extranerf-website)




#### <summary>Controlling Space and Time with Diffusion Models
Authors: Daniel Watson, Saurabh Saxena, Lala Li, Andrea Tagliasacchi, David J. Fleet
<details span>
<summary><b>Abstract</b></summary>
We present 4DiM, a cascaded diffusion model for 4D novel view synthesis (NVS), conditioned on one or more images of a general scene, and a set of camera poses and timestamps. To overcome challenges due to limited availability of 4D training data, we advocate joint training on 3D (with camera pose), 4D (pose+time) and video (time but no pose) data and propose a new architecture that enables the same. We further advocate the calibration of SfM posed data using monocular metric depth estimators for metric scale camera control. For model evaluation, we introduce new metrics to enrich and overcome shortcomings of current evaluation schemes, demonstrating state-of-the-art results in both fidelity and pose control compared to existing diffusion models for 3D NVS, while at the same time adding the ability to handle temporal dynamics. 4DiM is also used for improved panorama stitching, pose-conditioned video to video translation, and several other tasks.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f98c287d-37ac-4da7-bcb1-1ce539d5c30a)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.07860) | [⌨️ Code] | [🌐 Project Page](https://4d-diffusion.github.io/)

#### <summary>Drantal-NeRF: Diffusion-Based Restoration for Anti-aliasing Neural Radiance Field
Authors: Ganlin Yang, Kaidong Zhang, Jingjing Fu, Dong Liu
<details span>
<summary><b>Abstract</b></summary>
Aliasing artifacts in renderings produced by Neural Radiance Field (NeRF) is a long-standing but complex issue in the field of 3D implicit representation, which arises from a multitude of intricate causes and was mitigated by designing more advanced but complex scene parameterization methods before. In this paper, we present a Diffusion-based restoration method for anti-aliasing Neural Radiance Field (Drantal-NeRF). We consider the anti-aliasing issue from a low-level restoration perspective by viewing aliasing artifacts as a kind of degradation model added to clean ground truths. By leveraging the powerful prior knowledge encapsulated in diffusion model, we could restore the high-realism anti-aliasing renderings conditioned on aliased low-quality counterparts. We further employ a feature-wrapping operation to ensure multi-view restoration consistency and finetune the VAE decoder to better adapt to the scene-specific data distribution. Our proposed method is easy to implement and agnostic to various NeRF backbones. We conduct extensive experiments on challenging large-scale urban scenes as well as unbounded 360-degree scenes and achieve substantial qualitative and quantitative improvements.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/b5f6bb81-eebd-4379-80b7-56786ccbcce2)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.07461) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Radiance Fields from Photons
Authors: Sacha Jungerman, Mohit Gupta
<details span>
<summary><b>Abstract</b></summary>
Neural radiance fields, or NeRFs, have become the de facto approach for high-quality view synthesis from a collection of images captured from multiple viewpoints. However, many issues remain when capturing images in-the-wild under challenging conditions, such as low light, high dynamic range, or rapid motion leading to smeared reconstructions with noticeable artifacts. In this work, we introduce quanta radiance fields, a novel class of neural radiance fields that are trained at the granularity of individual photons using single-photon cameras (SPCs). We develop theory and practical computational techniques for building radiance fields and estimating dense camera poses from unconventional, stochastic, and high-speed binary frame sequences captured by SPCs. We demonstrate, both via simulations and a SPC hardware prototype, high-fidelity reconstructions under high-speed motion, in low light, and for extreme dynamic range settings.

![image](https://github.com/user-attachments/assets/2160046e-61d1-477c-ada8-2627a84064e6)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.09386) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Boost Your NeRF: A Model-Agnostic Mixture of Experts Framework for High Quality and Efficient Rendering
Authors: Francesco Di Sario, Riccardo Renzulli, Enzo Tartaglione, Marco Grangetto
<details span>
<summary><b>Abstract</b></summary>
Since the introduction of NeRFs, considerable attention has been focused on improving their training and inference times, leading to the development of Fast-NeRFs models. Despite demonstrating impressive rendering speed and quality, the rapid convergence of such models poses challenges for further improving reconstruction quality. Common strategies to improve rendering quality involves augmenting model parameters or increasing the number of sampled points. However, these computationally intensive approaches encounter limitations in achieving significant quality enhancements. This study introduces a model-agnostic framework inspired by Sparsely-Gated Mixture of Experts to enhance rendering quality without escalating computational complexity. Our approach enables specialization in rendering different scene components by employing a mixture of experts with varying resolutions. We present a novel gate formulation designed to maximize expert capabilities and propose a resolution-based routing technique to effectively induce sparsity and decompose scenes. Our work significantly improves reconstruction quality while maintaining competitive performance.

![image](https://github.com/user-attachments/assets/093af40b-62ce-4ace-89b2-0b787ae03d94)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.10389) | [⌨️ Code] | [🌐 Project Page]

#### <summary>RS-NeRF: Neural Radiance Fields from Rolling Shutter Images
Authors: Muyao Niu, Tong Chen, Yifan Zhan, Zhuoxiao Li, Xiang Ji, Yinqiang Zheng
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRFs) have become increasingly popular because of their impressive ability for novel view synthesis. However, their effectiveness is hindered by the Rolling Shutter (RS) effects commonly found in most camera systems. To solve this, we present RS-NeRF, a method designed to synthesize normal images from novel views using input with RS distortions. This involves a physical model that replicates the image formation process under RS conditions and jointly optimizes NeRF parameters and camera extrinsic for each image row. We further address the inherent shortcomings of the basic RS-NeRF model by delving into the RS characteristics and developing algorithms to enhance its functionality. First, we impose a smoothness regularization to better estimate trajectories and improve the synthesis quality, in line with the camera movement prior. We also identify and address a fundamental flaw in the vanilla RS model by introducing a multi-sampling algorithm. This new approach improves the model's performance by comprehensively exploiting the RGB data across different rows for each intermediate camera pose. Through rigorous experimentation, we demonstrate that RS-NeRF surpasses previous methods in both synthetic and real-world scenarios, proving its ability to correct RS-related distortions effectively.

![image](https://github.com/user-attachments/assets/bab22aaf-e5d9-4ab3-b8ed-19f26f921e04)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.10267) | [⌨️ Code](https://github.com/MyNiuuu/RS-NeRF) | [🌐 Project Page]

#### <summary>Invertible Neural Warp for NeRF
Authors: Shin-Fang Chng, Ravi Garg, Hemanth Saratchandran, Simon Lucey
<details span>
<summary><b>Abstract</b></summary>
This paper tackles the simultaneous optimization of pose and Neural Radiance Fields (NeRF). Departing from the conventional practice of using explicit global representations for camera pose, we propose a novel overparameterized representation that models camera poses as learnable rigid warp functions. We establish that modeling the rigid warps must be tightly coupled with constraints and regularization imposed. Specifically, we highlight the critical importance of enforcing invertibility when learning rigid warp functions via neural network and propose the use of an Invertible Neural Network (INN) coupled with a geometry-informed constraint for this purpose. We present results on synthetic and real-world datasets, and demonstrate that our approach outperforms existing baselines in terms of pose estimation and high-fidelity reconstruction due to enhanced optimization convergence.

![image](https://github.com/user-attachments/assets/364a2073-0f85-4f9d-93b0-f6f18e09a360)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12354) | [⌨️ Code](https://github.com/sfchng/neural_invertible_warp) | [🌐 Project Page](https://sfchng.github.io/ineurowarping-github.io/)



#### <summary>Efficient Depth-Guided Urban View Synthesis
Authors: Sheng Miao, Jiaxin Huang, Dongfeng Bai, Weichao Qiu, Bingbing Liu, Andreas Geiger, Yiyi Liao
<details span>
<summary><b>Abstract</b></summary>
Recent advances in implicit scene representation enable high-fidelity street view novel view synthesis. However, existing methods optimize a neural radiance field for each scene, relying heavily on dense training images and extensive computation resources. To mitigate this shortcoming, we introduce a new method called Efficient Depth-Guided Urban View Synthesis (EDUS) for fast feed-forward inference and efficient per-scene fine-tuning. Different from prior generalizable methods that infer geometry based on feature matching, EDUS leverages noisy predicted geometric priors as guidance to enable generalizable urban view synthesis from sparse input images. The geometric priors allow us to apply our generalizable model directly in the 3D space, gaining robustness across various sparsity levels. Through comprehensive experiments on the KITTI-360 and Waymo datasets, we demonstrate promising generalization abilities on novel street scenes. Moreover, our results indicate that EDUS achieves state-of-the-art performance in sparse view settings when combined with fast test-time optimization.

![image](https://github.com/user-attachments/assets/0f9e894b-c23d-4166-8224-d3fb0e99fb16)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12395) | [⌨️ Code] | [🌐 Project Page](https://xdimlab.github.io/EDUS/)


#### <summary>SparseCraft: Few-Shot Neural Reconstruction through Stereopsis Guided Geometric Linearization
Authors: Mae Younes, Amine Ouasfi, Adnane Boukhayma
<details span>
<summary><b>Abstract</b></summary>
We present a novel approach for recovering 3D shape and view dependent appearance from a few colored images, enabling efficient 3D reconstruction and novel view synthesis. Our method learns an implicit neural representation in the form of a Signed Distance Function (SDF) and a radiance field. The model is trained progressively through ray marching enabled volumetric rendering, and regularized with learning-free multi-view stereo (MVS) cues. Key to our contribution is a novel implicit neural shape function learning strategy that encourages our SDF field to be as linear as possible near the level-set, hence robustifying the training against noise emanating from the supervision and regularization signals. Without using any pretrained priors, our method, called SparseCraft, achieves state-of-the-art performances both in novel-view synthesis and reconstruction from sparse views in standard benchmarks, while requiring less than 10 minutes for training.

![image](https://github.com/user-attachments/assets/18dc3077-b499-4ff2-9129-1607a2dd16e7)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.14257) | [⌨️ Code](https://github.com/maeyounes/SparseCraft) | [🌐 Project Page](https://sparsecraft.github.io/)

#### <summary>BoostMVSNeRFs: Boosting MVS-based NeRFs to Generalizable View Synthesis in Large-scale Scenes
Authors: Chih-Hai Su, Chih-Yao Hu, Shr-Ruei Tsai, Jie-Ying Lee, Chin-Yang Lin, Yu-Lun Liu
<details span>
<summary><b>Abstract</b></summary>
While Neural Radiance Fields (NeRFs) have demonstrated exceptional quality, their protracted training duration remains a limitation. Generalizable and MVS-based NeRFs, although capable of mitigating training time, often incur tradeoffs in quality. This paper presents a novel approach called BoostMVSNeRFs to enhance the rendering quality of MVS-based NeRFs in large-scale scenes. We first identify limitations in MVS-based NeRF methods, such as restricted viewport coverage and artifacts due to limited input views. Then, we address these limitations by proposing a new method that selects and combines multiple cost volumes during volume rendering. Our method does not require training and can adapt to any MVS-based NeRF methods in a feed-forward fashion to improve rendering quality. Furthermore, our approach is also end-to-end trainable, allowing fine-tuning on specific scenes. We demonstrate the effectiveness of our method through experiments on large-scale datasets, showing significant rendering quality improvements in large-scale scenes and unbounded outdoor scenarios.

![image](https://github.com/user-attachments/assets/4b6edbe0-7b7f-4fbf-bf99-2c4756d3916a)



</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.15848) | [⌨️ Code](https://github.com/Su-Terry/BoostMVSNeRFs) | [🌐 Project Page](https://su-terry.github.io/BoostMVSNeRFs/)


#### <summary>Self-training Room Layout Estimation via Geometry-aware Ray-casting
Authors: Bolivar Solarte, Chin-Hsuan Wu, Jin-Cheng Jhang, Jonathan Lee, Yi-Hsuan Tsai, Min Sun
<details span>
<summary><b>Abstract</b></summary>
In this paper, we introduce a novel geometry-aware self-training framework for room layout estimation models on unseen scenes with unlabeled data. Our approach utilizes a ray-casting formulation to aggregate multiple estimates from different viewing positions, enabling the computation of reliable pseudo-labels for self-training. In particular, our ray-casting approach enforces multi-view consistency along all ray directions and prioritizes spatial proximity to the camera view for geometry reasoning. As a result, our geometry-aware pseudo-labels effectively handle complex room geometries and occluded walls without relying on assumptions such as Manhattan World or planar room walls. Evaluation on publicly available datasets, including synthetic and real-world scenarios, demonstrates significant improvements in current state-of-the-art layout models without using any human annotation.

![image](https://github.com/user-attachments/assets/80ab66bd-1171-44be-8577-7c173f78ef0a)



</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.15041) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Efficient Depth-Guided Urban View Synthesis
Authors: Sheng Miao, Jiaxin Huang, Dongfeng Bai, Weichao Qiu, Bingbing Liu, Andreas Geiger, Yiyi Liao
<details span>
<summary><b>Abstract</b></summary>
Recent advances in implicit scene representation enable high-fidelity street view novel view synthesis. However, existing methods optimize a neural radiance field for each scene, relying heavily on dense training images and extensive computation resources. To mitigate this shortcoming, we introduce a new method called Efficient Depth-Guided Urban View Synthesis (EDUS) for fast feed-forward inference and efficient per-scene fine-tuning. Different from prior generalizable methods that infer geometry based on feature matching, EDUS leverages noisy predicted geometric priors as guidance to enable generalizable urban view synthesis from sparse input images. The geometric priors allow us to apply our generalizable model directly in the 3D space, gaining robustness across various sparsity levels. Through comprehensive experiments on the KITTI-360 and Waymo datasets, we demonstrate promising generalization abilities on novel street scenes. Moreover, our results indicate that EDUS achieves state-of-the-art performance in sparse view settings when combined with fast test-time optimization.

![image](https://github.com/user-attachments/assets/9b7c4759-3947-4cf9-a224-4a6def6fafc6)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12395) | [⌨️ Code] | [🌐 Project Page](https://xdimlab.github.io/EDUS/)

#### <summary>PIV3CAMS: a multi-camera dataset for multiple computer vision problems and its application to novel view-point synthesis
Authors: Sohyeong Kim, Martin Danelljan, Radu Timofte, Luc Van Gool, Jean-Philippe Thiran
<details span>
<summary><b>Abstract</b></summary>
The modern approaches for computer vision tasks significantly rely on machine learning, which requires a large number of quality images. While there is a plethora of image datasets with a single type of images, there is a lack of datasets collected from multiple cameras. In this thesis, we introduce Paired Image and Video data from three CAMeraS, namely PIV3CAMS, aimed at multiple computer vision tasks. The PIV3CAMS dataset consists of 8385 pairs of images and 82 pairs of videos taken from three different cameras: Canon D5 Mark IV, Huawei P20, and ZED stereo camera. The dataset includes various indoor and outdoor scenes from different locations in Zurich (Switzerland) and Cheonan (South Korea). Some of the computer vision applications that can benefit from the PIV3CAMS dataset are image/video enhancement, view interpolation, image matching, and much more. We provide a careful explanation of the data collection process and detailed analysis of the data. The second part of this thesis studies the usage of depth information in the view synthesizing task. In addition to the regeneration of a current state-of-the-art algorithm, we investigate several proposed alternative models that integrate depth information geometrically. Through extensive experiments, we show that the effect of depth is crucial in small view changes. Finally, we apply our model to the introduced PIV3CAMS dataset to synthesize novel target views as an example application of PIV3CAMS.


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.18695) | [⌨️ Code] | [🌐 Project Page]


#### <summary>IOVS4NeRF:Incremental Optimal View Selection for Large-Scale NeRFs
Authors: Jingpeng Xie, Shiyu Tan, Yuanlei Wang, Yizhen Lao
<details span>
<summary><b>Abstract</b></summary>
Urban-level three-dimensional reconstruction for modern applications demands high rendering fidelity while minimizing computational costs. The advent of Neural Radiance Fields (NeRF) has enhanced 3D reconstruction, yet it exhibits artifacts under multiple viewpoints. In this paper, we propose a new NeRF framework method to address these issues. Our method uses image content and pose data to iteratively plan the next best view. A crucial aspect of this method involves uncertainty estimation, guiding the selection of views with maximum information gain from a candidate set. This iterative process enhances rendering quality over time. Simultaneously, we introduce the Vonoroi diagram and threshold sampling together with flight classifier to boost the efficiency, while keep the original NeRF network intact. It can serve as a plug-in tool to assist in better rendering, outperforming baselines and similar prior works.

![image](https://github.com/user-attachments/assets/4dee1e3f-1f31-46b9-b1b7-3809f2710bfd)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.18611) | [⌨️ Code] | [🌐 Project Page]


#### <summary>View-consistent Object Removal in Radiance Fields
Authors: Yiren Lu, Jing Ma, Yu Yin
<details span>
<summary><b>Abstract</b></summary>
Radiance Fields (RFs) have emerged as a crucial technology for 3D scene representation, enabling the synthesis of novel views with remarkable realism. However, as RFs become more widely used, the need for effective editing techniques that maintain coherence across different perspectives becomes evident. Current methods primarily depend on per-frame 2D image inpainting, which often fails to maintain consistency across views, thus compromising the realism of edited RF scenes. In this work, we introduce a novel RF editing pipeline that significantly enhances consistency by requiring the inpainting of only a single reference image. This image is then projected across multiple views using a depth-based approach, effectively reducing the inconsistencies observed with per-frame inpainting. However, projections typically assume photometric consistency across views, which is often impractical in real-world settings. To accommodate realistic variations in lighting and viewpoint, our pipeline adjusts the appearance of the projected views by generating multiple directional variants of the inpainted image, thereby adapting to different photometric conditions. Additionally, we present an effective and robust multi-view object segmentation approach as a valuable byproduct of our pipeline. Extensive experiments demonstrate that our method significantly surpasses existing frameworks in maintaining content consistency across views and enhancing visual quality.

![image](https://github.com/user-attachments/assets/ed71adf2-897a-4cac-84fc-fe1b99cb2c8a)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.02100) | [⌨️ Code] | [🌐 Project Page](https://vulab-ai.github.io/View-consistent_Object_Removal_in_Radiance_Fields/)

#### <summary>Improving Neural Surface Reconstruction with Feature Priors from Multi-View Image
Authors: Xinlin Ren, Chenjie Cao, Yanwei Fu, Xiangyang Xue
<details span>
<summary><b>Abstract</b></summary>
Recent advancements in Neural Surface Reconstruction (NSR) have significantly improved multi-view reconstruction when coupled with volume rendering. However, relying solely on photometric consistency in image space falls short of addressing complexities posed by real-world data, including occlusions and non-Lambertian surfaces. To tackle these challenges, we propose an investigation into feature-level consistent loss, aiming to harness valuable feature priors from diverse pretext visual tasks and overcome current limitations. It is crucial to note the existing gap in determining the most effective pretext visual task for enhancing NSR. In this study, we comprehensively explore multi-view feature priors from seven pretext visual tasks, comprising thirteen methods. Our main goal is to strengthen NSR training by considering a wide range of possibilities. Additionally, we examine the impact of varying feature resolutions and evaluate both pixel-wise and patch-wise consistent losses, providing insights into effective strategies for improving NSR performance. By incorporating pre-trained representations from MVSFormer and QuadTree, our approach can generate variations of MVS-NeuS and Match-NeuS, respectively. Our results, analyzed on DTU and EPFL datasets, reveal that feature priors from image matching and multi-view stereo outperform other pretext tasks. Moreover, we discover that extending patch-wise photometric consistency to the feature level surpasses the performance of pixel-wise approaches. These findings underscore the effectiveness of these techniques in enhancing NSR outcomes.

![image](https://github.com/user-attachments/assets/744c954e-10c8-424f-8e69-50dcf6b88659)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.02079) | [⌨️ Code](https://github.com/maybeLx/MVS_NeuS) | [🌐 Project Page]


#### <summary>ActiveNeRF: Learning Accurate 3D Geometry by Active Pattern Projection
Authors: Jianyu Tao, Changping Hu, Edward Yang, Jing Xu, Rui Chen
<details span>
<summary><b>Abstract</b></summary>
NeRFs have achieved incredible success in novel view synthesis. However, the accuracy of the implicit geometry is unsatisfactory because the passive static environmental illumination has low spatial frequency and cannot provide enough information for accurate geometry reconstruction. In this work, we propose ActiveNeRF, a 3D geometry reconstruction framework, which improves the geometry quality of NeRF by actively projecting patterns of high spatial frequency onto the scene using a projector which has a constant relative pose to the camera. We design a learnable active pattern rendering pipeline which jointly learns the scene geometry and the active pattern. We find that, by adding the active pattern and imposing its consistency across different views, our proposed method outperforms state of the art geometry reconstruction methods qualitatively and quantitatively in both simulation and real experiments.

![image](https://github.com/user-attachments/assets/8f275f8c-2670-42de-817a-a80f80604c12)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.06592) | [⌨️ Code](https://github.com/hcp16/active_nerf) | [🌐 Project Page]

#### <summary>VF-NeRF: Learning Neural Vector Fields for Indoor Scene Reconstruction
Authors: Albert Gassol Puigjaner, Edoardo Mello Rella, Erik Sandström, Ajad Chhatkuli, Luc Van Gool
<details span>
<summary><b>Abstract</b></summary>
Implicit surfaces via neural radiance fields (NeRF) have shown surprising accuracy in surface reconstruction. Despite their success in reconstructing richly textured surfaces, existing methods struggle with planar regions with weak textures, which account for the majority of indoor scenes. In this paper, we address indoor dense surface reconstruction by revisiting key aspects of NeRF in order to use the recently proposed Vector Field (VF) as the implicit representation. VF is defined by the unit vector directed to the nearest surface point. It therefore flips direction at the surface and equals to the explicit surface normals. Except for this flip, VF remains constant along planar surfaces and provides a strong inductive bias in representing planar surfaces. Concretely, we develop a novel density-VF relationship and a training scheme that allows us to learn VF via volume rendering By doing this, VF-NeRF can model large planar surfaces and sharp corners accurately. We show that, when depth cues are available, our method further improves and achieves state-of-the-art results in reconstructing indoor scenes and rendering novel views. We extensively evaluate VF-NeRF on indoor datasets and run ablations of its components.

![image](https://github.com/user-attachments/assets/1909f23c-04b0-4845-8a11-d9984cf442ee)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.08766) | [⌨️ Code](https://github.com/albertgassol1/vf-nerf) | [🌐 Project Page]

#### <summary>DiscoNeRF: Class-Agnostic Object Field for 3D Object Discovery
>  *using and processing SAM for render feature*

Authors: Corentin Dumery, Aoxiang Fan, Ren Li, Nicolas Talabot, Pascal Fua
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRFs) have become a powerful tool for modeling 3D scenes from multiple images. However, NeRFs remain difficult to segment into semantically meaningful regions. Previous approaches to 3D segmentation of NeRFs either require user interaction to isolate a single object, or they rely on 2D semantic masks with a limited number of classes for supervision. As a consequence, they generalize poorly to class-agnostic masks automatically generated in real scenes. This is attributable to the ambiguity arising from zero-shot segmentation, yielding inconsistent masks across views. In contrast, we propose a method that is robust to inconsistent segmentations and successfully decomposes the scene into a set of objects of any class. By introducing a limited number of competing object slots against which masks are matched, a meaningful object representation emerges that best explains the 2D supervision and minimizes an additional regularization term. Our experiments demonstrate the ability of our method to generate 3D panoptic segmentations on complex scenes, and extract high-quality 3D assets from NeRFs that can then be used in virtual 3D environments.

![image](https://github.com/user-attachments/assets/100860d3-d499-45b0-bd27-d13ba1ee643b)

</details>

[📃 arXiv:2408](https://web3.arxiv.org/pdf/2408.09928) | [⌨️ Code] | [🌐 Project Page] 

#### <summary>Photorealistic Object Insertion with Diffusion-Guided Inverse Rendering
Authors: Ruofan Liang, Zan Gojcic, Merlin Nimier-David, David Acuna, Nandita Vijaykumar, Sanja Fidler, Zian Wang
<details span>
<summary><b>Abstract</b></summary>
The correct insertion of virtual objects in images of real-world scenes requires a deep understanding of the scene's lighting, geometry and materials, as well as the image formation process. While recent large-scale diffusion models have shown strong generative and inpainting capabilities, we find that current models do not sufficiently "understand" the scene shown in a single picture to generate consistent lighting effects (shadows, bright reflections, etc.) while preserving the identity and details of the composited object. We propose using a personalized large diffusion model as guidance to a physically based inverse rendering process. Our method recovers scene lighting and tone-mapping parameters, allowing the photorealistic composition of arbitrary virtual objects in single frames or videos of indoor or outdoor scenes. Our physically based pipeline further enables automatic materials and tone-mapping refinement.

![image](https://github.com/user-attachments/assets/50897d1d-419d-4737-8d04-a03d088931b7)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.09702) | [⌨️ Code] | [🌐 Project Page](https://research.nvidia.com/labs/toronto-ai/DiPIR/)


#### <summary>ND-SDF: Learning Normal Deflection Fields for High-Fidelity Indoor Reconstruction
>  *Normal Deflection field for mono normal ambiguity*

Authors: Ziyu Tang, Weicai Ye, Yifan Wang, Di Huang, Hujun Bao, Tong He, Guofeng Zhang
<details span>
<summary><b>Abstract</b></summary>
Neural implicit reconstruction via volume rendering has demonstrated its effectiveness in recovering dense 3D surfaces. However, it is non-trivial to simultaneously recover meticulous geometry and preserve smoothness across regions with differing characteristics. To address this issue, previous methods typically employ geometric priors, which are often constrained by the performance of the prior models. In this paper, we propose ND-SDF, which learns a Normal Ddeflection field to represent the angular deviation between the scene normal and the prior normal. Unlike previous methods that uniformly apply geometric priors on all samples, introducing significant bias in accuracy, our proposed normal deflection field dynamically learns and adapts the utilization of samples based on their specific characteristics, thereby improving both the accuracy and effectiveness of the model. Our method not only obtains smooth weakly textured regions such as walls and floors but also preserves the geometric details of complex structures. In addition, we introduce a novel ray sampling strategy based on the deflection angle to facilitate the unbiased rendering process, which significantly improves the quality and accuracy of intricate surfaces, especially on thin structures. Consistent improvements on various challenging datasets demonstrate the superiority of our method.

![image](https://github.com/user-attachments/assets/4ed52a9f-5241-4336-831f-be3838c8b7af)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.12598) | [⌨️ Code](https://github.com/zju3dv/ND-SDF) | [🌐 Project Page](https://zju3dv.github.io/nd-sdf/)


#### <summary>Rethinking Directional Parameterization in Neural Implicit Surface Reconstruction
>  *first to provide an in-depth analysis of why the use of reflection directional parameterization tends to reconstruct incorrect geometry of objects with concave or complex structures*

Authors: Zijie Jiang, Tianhan Xu, Hiroharu Kato
<details span>
<summary><b>Abstract</b></summary>
Multi-view 3D surface reconstruction using neural implicit representations has made notable progress by modeling the geometry and view-dependent radiance fields within a unified framework. However, their effectiveness in reconstructing objects with specular or complex surfaces is typically biased by the directional parameterization used in their view-dependent radiance network. {\it Viewing direction} and {\it reflection direction} are the two most commonly used directional parameterizations but have their own limitations. Typically, utilizing the viewing direction usually struggles to correctly decouple the geometry and appearance of objects with highly specular surfaces, while using the reflection direction tends to yield overly smooth reconstructions for concave or complex structures. In this paper, we analyze their failed cases in detail and propose a novel hybrid directional parameterization to address their limitations in a unified form. Extensive experiments demonstrate the proposed hybrid directional parameterization consistently delivered satisfactory results in reconstructing objects with a wide variety of materials, geometry and appearance, whereas using other directional parameterizations faces challenges in reconstructing certain objects. Moreover, the proposed hybrid directional parameterization is nearly parameter-free and can be effortlessly applied in any existing neural surface reconstruction method.

![image](https://github.com/user-attachments/assets/1d994cda-5b79-4138-a27b-0210a25daf46)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.06923) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Expansive Supervision for Neural Radiance Field
>  *first to observe a strong correlation between error distribution and image content. a mechanism operates by selectively rendering a small but crucial subset of pixels and expanding their values to estimate the error across the entire area for each iteration.*

Authors: Weixiang Zhang, Shuzhao Xie, Shijia Ge, Wei Yao, Chen Tang, Zhi Wang
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields have achieved success in creating powerful 3D media representations with their exceptional reconstruction capabilities. However, the computational demands of volume rendering pose significant challenges during model training. Existing acceleration techniques often involve redesigning the model architecture, leading to limitations in compatibility across different frameworks. Furthermore, these methods tend to overlook the substantial memory costs incurred. In response to these challenges, we introduce an expansive supervision mechanism that efficiently balances computational load, rendering quality and flexibility for neural radiance field training. This mechanism operates by selectively rendering a small but crucial subset of pixels and expanding their values to estimate the error across the entire area for each iteration. Compare to conventional supervision, our method effectively bypasses redundant rendering processes, resulting in notable reductions in both time and memory consumption. Experimental results demonstrate that integrating expansive supervision within existing state-of-the-art acceleration frameworks can achieve 69% memory savings and 42% time savings, with negligible compromise in visual quality.

![image](https://github.com/user-attachments/assets/705cf1af-f7b2-499d-a847-91c05bfe1619)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.08056) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Surface-Centric Modeling for High-Fidelity Generalizable Neural Surface Reconstruction
>*Instead of predicting an SDF value for each voxel, we present a new region sparsification approach to sparse the volume by judging whether the voxel is inside the surface region.*

Authors: Rui Peng, Shihe Shen, Kaiqiang Xiong, Huachen Gao, Jianbo Jiao, Xiaodong Gu, Ronggang Wang
<details span>
<summary><b>Abstract</b></summary>
Reconstructing the high-fidelity surface from multi-view images, especially sparse images, is a critical and practical task that has attracted widespread attention in recent years. However, existing methods are impeded by the memory constraint or the requirement of ground-truth depths and cannot recover satisfactory geometric details. To this end, we propose SuRF, a new Surface-centric framework that incorporates a new Region sparsification based on a matching Field, achieving good trade-offs between performance, efficiency and scalability. To our knowledge, this is the first unsupervised method achieving end-to-end sparsification powered by the introduced matching field, which leverages the weight distribution to efficiently locate the boundary regions containing surface. Instead of predicting an SDF value for each voxel, we present a new region sparsification approach to sparse the volume by judging whether the voxel is inside the surface region. In this way, our model can exploit higher frequency features around the surface with less memory and computational consumption. Extensive experiments on multiple benchmarks containing complex large-scale scenes show that our reconstructions exhibit high-quality details and achieve new state-of-the-art performance, i.e., 46% improvements with 80% less memory consumption.

![image](https://github.com/user-attachments/assets/6f0b00dc-1551-413f-b26e-235f55a78f4a)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.03634) | [⌨️ Code](https://github.com/prstrive/SuRF) | [🌐 Project Page]





#### <summary>Redundancy-Aware Camera Selection for Indoor Scene Neural Rendering
>*camera frame selection*

Authors: Zehao Wang, Han Zhou, Matthew B. Blaschko, Tinne Tuytelaars, Minye Wu
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis of indoor scenes can be achieved by capturing a monocular video sequence of the environment. However, redundant information caused by artificial movements in the input video data reduces the efficiency of scene modeling. In this work, we tackle this challenge from the perspective of camera selection. We begin by constructing a similarity matrix that incorporates both the spatial diversity of the cameras and the semantic variation of the images. Based on this matrix, we use the Intra-List Diversity (ILD) metric to assess camera redundancy, formulating the camera selection task as an optimization problem. Then we apply a diversity-based sampling algorithm to optimize the camera selection. We also develop a new dataset, IndoorTraj, which includes long and complex camera movements captured by humans in virtual indoor environments, closely mimicking real-world scenarios. Experimental results demonstrate that our strategy outperforms other approaches under time and memory constraints. Remarkably, our method achieves performance comparable to models trained on the full dataset, while using only an average of 15% of the frames and 75% of the allotted time.

![image](https://github.com/user-attachments/assets/cc9658d6-7551-4a6a-bb2d-f8f2cfa4b758)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.07098) | [⌨️ Code] | [🌐 Project Page]





#### <summary>Refinement of Monocular Depth Maps via Multi-View Differentiable Rendering
Authors: Laura Fink, Linus Franke, Joachim Keinert, Marc Stamminger
<details span>
<summary><b>Abstract</b></summary>
The accurate reconstruction of per-pixel depth for an image is vital for many tasks in computer graphics, computer vision, and robotics. In this paper, we present a novel approach to generate view consistent and detailed depth maps from a number of posed images. We leverage advances in monocular depth estimation, which generate topologically complete, but metrically inaccurate depth maps and refine them in a two-stage optimization process based on a differentiable renderer. Taking the monocular depth map as input, we first scale this map to absolute distances based on structure-from-motion and transform the depths to a triangle surface mesh. We then refine this depth mesh in a local optimization, enforcing photometric and geometric consistency.
Our evaluation shows that our method is able to generate dense, detailed, high-quality depth maps, also in challenging indoor scenarios, and outperforms state-of-the-art depth reconstruction approaches.

![image](https://github.com/user-attachments/assets/6e221b72-d642-4703-a93f-b4c0e5c85565)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.03861) | [⌨️ Code] | [🌐 Project Page](https://lorafib.github.io/ref_depth/)









<br>
<br>


### Others


#### <summary>BakedSDF: Meshing Neural SDFs for Real-Time View Synthesis
Authors: Lior Yariv, Peter Hedman, Christian Reiser, Dor Verbin, Pratul P. Srinivasan, Richard Szeliski, Jonathan T. Barron, Ben Mildenhall
<details span>
<summary><b>Abstract</b></summary>
We present a method for reconstructing high-quality meshes of large unbounded real-world scenes suitable for photorealistic novel view synthesis. We first optimize a hybrid neural volume-surface scene representation designed to have well-behaved level sets that correspond to surfaces in the scene. We then bake this representation into a high-quality triangle mesh, which we equip with a simple and fast view-dependent appearance model based on spherical Gaussians. Finally, we optimize this baked representation to best reproduce the captured viewpoints, resulting in a model that can leverage accelerated polygon rasterization pipelines for real-time view synthesis on commodity hardware. Our approach outperforms previous scene representations for real-time rendering in terms of accuracy, speed, and power consumption, and produces high quality meshes that enable applications such as appearance editing and physical simulation.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/43590084-70ca-4c41-a23a-243b9fe7428a)


</details>

[📃 arXiv:2302](https://arxiv.org/abs/2302.14859) | [⌨️ Code] | [🌐 Project Page](https://bakedsdf.github.io/)



#### <summary>D2NT: A High-Performing Depth-to-Normal Translator
Authors: Yi Feng, Bohuan Xue, Ming Liu, Qijun Chen, and Rui Fan
<details span>
<summary><b>Abstract</b></summary>
Surface normal holds significant importance in visual environmental perception, serving as a source of rich geometric information. However, the state-of-the-art (SoTA) surface normal estimators (SNEs) generally suffer from an unsatisfactory trade-off between efficiency and accuracy. To resolve this dilemma, this paper first presents a superfast depthto-normal translator (D2NT), which can directly translate depth images into surface normal maps without calculating 3D coordinates. We then propose a discontinuity-aware gradient (DAG) filter, which adaptively generates gradient convolution kernels to improve depth gradient estimation. Finally, we propose a surface normal refinement module that can easily be integrated into any depth-to-normal SNEs, substantially improving the surface normal estimation accuracy. Our proposed algorithm demonstrates the best accuracy among all other existing realtime SNEs and achieves the SoTA trade-off between efficiency and accuracy. 

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/d1a0d93d-5382-4235-b3a3-a6d442ae4597)

</details>

[📃 arXiv:2304](https://arxiv.org/pdf/2304.12031.pdf) | [⌨️ Code](https://github.com/fengyi233/depth-to-normal-translator/tree/main?tab=readme-ov-file) | [🌐 Project Page](https://mias.group/D2NT/)

#### <summary>Neuralangelo: High-Fidelity Neural Surface Reconstruction
Authors: Zhaoshuo Li, Thomas Müller, Alex Evans, Russell H. Taylor, Mathias Unberath, Ming-Yu Liu, Chen-Hsuan Lin
<details span>
<summary><b>Abstract</b></summary>
Neural surface reconstruction has been shown to be powerful for recovering dense 3D surfaces via image-based neural rendering. However, current methods struggle to recover detailed structures of real-world scenes. To address the issue, we present Neuralangelo, which combines the representation power of multi-resolution 3D hash grids with neural surface rendering. Two key ingredients enable our approach: (1) numerical gradients for computing higher-order derivatives as a smoothing operation and (2) coarse-to-fine optimization on the hash grids controlling different levels of details. Even without auxiliary inputs such as depth, Neuralangelo can effectively recover dense 3D surface structures from multi-view images with fidelity significantly surpassing previous methods, enabling detailed large-scale scene reconstruction from RGB video captures.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4d6db880-07fb-484b-bc11-080e59f4ca8d)


</details>

[📃 arXiv:2306](https://arxiv.org/pdf/2306.03092) | [⌨️ Code](https://github.com/nvlabs/neuralangelo) | [🌐 Project Page](https://research.nvidia.com/labs/dir/neuralangelo/)



#### <summary>Visual Geometry Grounded Deep Structure From Motion
Authors: Jianyuan Wang, Nikita Karaev, Christian Rupprecht, David Novotny
<details span>
<summary><b>Abstract</b></summary>
Structure-from-motion (SfM) is a long-standing problem in the computer vision community, which aims to reconstruct the camera poses and 3D structure of a scene from a set of unconstrained 2D images. Classical frameworks solve this problem in an incremental manner by detecting and matching keypoints, registering images, triangulating 3D points, and conducting bundle adjustment. Recent research efforts have predominantly revolved around harnessing the power of deep learning techniques to enhance specific elements (e.g., keypoint matching), but are still based on the original, non-differentiable pipeline. Instead, we propose a new deep pipeline VGGSfM, where each component is fully differentiable and thus can be trained in an end-to-end manner. To this end, we introduce new mechanisms and simplifications. First, we build on recent advances in deep 2D point tracking to extract reliable pixel-accurate tracks, which eliminates the need for chaining pairwise matches. Furthermore, we recover all cameras simultaneously based on the image and track features instead of gradually registering cameras. Finally, we optimise the cameras and triangulate 3D points via a differentiable bundle adjustment layer. We attain state-of-the-art performance on three popular datasets, CO3D, IMC Phototourism, and ETH3D.

![image](https://github.com/user-attachments/assets/488e4803-ed40-407d-a0e1-92619bf397d6)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.04563) | [⌨️ Code] | [🌐 Project Page](https://vggsfm.github.io/)



#### <summary>Zero-Shot Metric Depth with a Field-of-View Conditioned Diffusion Model
Authors: Saurabh Saxena, Junhwa Hur, Charles Herrmann, Deqing Sun, David J. Fleet
<details span>
<summary><b>Abstract</b></summary>
While methods for monocular depth estimation have made significant strides on standard benchmarks, zero-shot metric depth estimation remains unsolved. Challenges include the joint modeling of indoor and outdoor scenes, which often exhibit significantly different distributions of RGB and depth, and the depth-scale ambiguity due to unknown camera intrinsics. Recent work has proposed specialized multi-head architectures for jointly modeling indoor and outdoor scenes. In contrast, we advocate a generic, task-agnostic diffusion model, with several advancements such as log-scale depth parameterization to enable joint modeling of indoor and outdoor scenes, conditioning on the field-of-view (FOV) to handle scale ambiguity and synthetically augmenting FOV during training to generalize beyond the limited camera intrinsics in training datasets. Furthermore, by employing a more diverse training mixture than is common, and an efficient diffusion parameterization, our method, DMD (Diffusion for Metric Depth) achieves a 25\% reduction in relative error (REL) on zero-shot indoor and 33\% reduction on zero-shot outdoor datasets over the current SOTA using only a small number of denoising steps.

</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.13252) | [⌨️ Code] | [🌐 Project Page](https://diffusion-vision.github.io/dmd/)



#### <summary>NeuSurf: On-Surface Priors for Neural Surface Reconstruction from Sparse Input Views
Authors: Han Huang, Yulun Wu, Junsheng Zhou, Ge Gao, Ming Gu, Yu-Shen Liu
<details span>
<summary><b>Abstract</b></summary>
Recently, neural implicit functions have demonstrated remarkable results in the field of multi-view reconstruction. However, most existing methods are tailored for dense views and exhibit unsatisfactory performance when dealing with sparse views. Several latest methods have been proposed for generalizing implicit reconstruction to address the sparse view reconstruction task, but they still suffer from high training costs and are merely valid under carefully selected perspectives. In this paper, we propose a novel sparse view reconstruction framework that leverages on-surface priors to achieve highly faithful surface reconstruction. Specifically, we design several constraints on global geometry alignment and local geometry refinement for jointly optimizing coarse shapes and fine details. To achieve this, we train a neural network to learn a global implicit field from the on-surface points obtained from SfM and then leverage it as a coarse geometric constraint. To exploit local geometric consistency, we project on-surface points onto seen and unseen views, treating the consistent loss of projected features as a fine geometric constraint. The experimental results with DTU and BlendedMVS datasets in two prevalent sparse settings demonstrate significant improvements over the state-of-the-art methods.
 
![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/0c8516ad-c054-4d61-adc2-afc59b43ceb9)

 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.13977.pdf) | [⌨️ Code](https://github.com/leonwu0108/NeuSurf) | [🌐 Project Page](https://alvin528.github.io/NeuSurf/)


#### <summary>SuperPrimitive: Scene Reconstruction at a Primitive Level
Authors: Kirill Mazur, Gwangbin Bae, Andrew J. Davison
<details span>
<summary><b>Abstract</b></summary>
Joint camera pose and dense geometry estimation from a set of images or a monocular video remains a challenging problem due to its computational complexity and inherent visual ambiguities. Most dense incremental reconstruction systems operate directly on image pixels and solve for their 3D positions using multi-view geometry cues. Such pixel-level approaches suffer from ambiguities or violations of multi-view consistency (e.g. caused by textureless or specular surfaces).
We address this issue with a new image representation which we call a SuperPrimitive. SuperPrimitives are obtained by splitting images into semantically correlated local regions and enhancing them with estimated surface normal directions, both of which are predicted by state-of-the-art single image neural networks. This provides a local geometry estimate per SuperPrimitive, while their relative positions are adjusted based on multi-view observations.
We demonstrate the versatility of our new representation by addressing three 3D reconstruction tasks: depth completion, few-view structure from motion, and monocular dense visual odometry.
 
![image](https://github.com/user-attachments/assets/2c54429c-a4c9-425f-825f-5c8361067b79)

 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.05889) | [⌨️ Code](https://github.com/makezur/super_primitive) | [🌐 Project Page](https://makezur.github.io/SuperPrimitive/)


#### <summary>DUSt3R: Geometric 3D Vision Made Easy
Authors: Shuzhe Wang, Vincent Leroy, Yohann Cabon, Boris Chidlovskii, Jerome Revaud
<details span>
<summary><b>Abstract</b></summary>
Multi-view stereo reconstruction (MVS) in the wild requires to first estimate the camera parameters e.g. intrinsic and extrinsic parameters. These are usually tedious and cumbersome to obtain, yet they are mandatory to triangulate corresponding pixels in 3D space, which is the core of all best performing MVS algorithms. In this work, we take an opposite stance and introduce DUSt3R, a radically novel paradigm for Dense and Unconstrained Stereo 3D Reconstruction of arbitrary image collections, i.e. operating without prior information about camera calibration nor viewpoint poses. We cast the pairwise reconstruction problem as a regression of pointmaps, relaxing the hard constraints of usual projective camera models. We show that this formulation smoothly unifies the monocular and binocular reconstruction cases. In the case where more than two images are provided, we further propose a simple yet effective global alignment strategy that expresses all pairwise pointmaps in a common reference frame. We base our network architecture on standard Transformer encoders and decoders, allowing us to leverage powerful pretrained models. Our formulation directly provides a 3D model of the scene as well as depth information, but interestingly, we can seamlessly recover from it, pixel matches, relative and absolute camera. Exhaustive experiments on all these tasks showcase that the proposed DUSt3R can unify various 3D vision tasks and set new SoTAs on monocular/multi-view depth estimation as well as relative pose estimation. In summary, DUSt3R makes many geometric 3D vision tasks easy.
 
![image](https://github.com/user-attachments/assets/4e94fe08-c8c3-49c7-ab34-9fc2e9f65e98)

</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.14132) | [⌨️ Code](https://github.com/naver/dust3r?tab=readme-ov-file) | [🌐 Project Page](https://europe.naverlabs.com/research/publications/dust3r-geometric-3d-vision-made-easy/)



#### <summary>Binary Opacity Grids: Capturing Fine Geometric Detail for Mesh-Based View Synthesis
Authors: Christian Reiser, Stephan Garbin, Pratul P. Srinivasan, Dor Verbin, Richard Szeliski, Ben Mildenhall, Jonathan T. Barron, Peter Hedman, Andreas Geiger
<details span>
<summary><b>Abstract</b></summary>
While surface-based view synthesis algorithms are appealing due to their low computational requirements, they often struggle to reproduce thin structures. In contrast, more expensive methods that model the scene's geometry as a volumetric density field (e.g. NeRF) excel at reconstructing fine geometric detail. However, density fields often represent geometry in a "fuzzy" manner, which hinders exact localization of the surface. In this work, we modify density fields to encourage them to converge towards surfaces, without compromising their ability to reconstruct thin structures. First, we employ a discrete opacity grid representation instead of a continuous density field, which allows opacity values to discontinuously transition from zero to one at the surface. Second, we anti-alias by casting multiple rays per pixel, which allows occlusion boundaries and subpixel structures to be modelled without using semi-transparent voxels. Third, we minimize the binary entropy of the opacity values, which facilitates the extraction of surface geometry by encouraging opacity values to binarize towards the end of training. Lastly, we develop a fusion-based meshing strategy followed by mesh simplification and appearance model fitting. The compact meshes produced by our model can be rendered in real-time on mobile devices and achieve significantly higher view synthesis quality compared to existing mesh-based approaches.

![image](https://github.com/user-attachments/assets/163bec21-a8f6-431b-8b89-922ba77ecdc0)

</details>

[📃 arXiv:2402](https://arxiv.org/pdf/2402.12377) | [⌨️ Code] | [🌐 Project Page](https://binary-opacity-grid.github.io/)





#### <summary>GeoWizard: Unleashing the Diffusion Priors for 3D Geometry Estimation from a Single Image
Authors: Xiao Fu, Wei Yin, Mu Hu, Kaixuan Wang, Yuexin Ma, Ping Tan, Shaojie Shen, Dahua Lin, Xiaoxiao Long
<details span>
<summary><b>Abstract</b></summary>
We introduce GeoWizard, a new generative foundation model designed for estimating geometric attributes, e.g., depth and normals, from single images. While significant research has already been conducted in this area, the progress has been substantially limited by the low diversity and poor quality of publicly available datasets. As a result, the prior works either are constrained to limited scenarios or suffer from the inability to capture geometric details. In this paper, we demonstrate that generative models, as opposed to traditional discriminative models (e.g., CNNs and Transformers), can effectively address the inherently ill-posed problem. We further show that leveraging diffusion priors can markedly improve generalization, detail preservation, and efficiency in resource usage. Specifically, we extend the original stable diffusion model to jointly predict depth and normal, allowing mutual information exchange and high consistency between the two representations. More importantly, we propose a simple yet effective strategy to segregate the complex data distribution of various scenes into distinct sub-distributions. This strategy enables our model to recognize different scene layouts, capturing 3D geometry with remarkable fidelity. GeoWizard sets new benchmarks for zero-shot depth and normal prediction, significantly enhancing many downstream applications such as 3D reconstruction, 2D content creation, and novel viewpoint synthesis.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ec58fca4-842a-4d35-97ce-90caf49467cb)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.12013) | [⌨️ Code](https://github.com/fuxiao0719/GeoWizard) | [🌐 Project Page](https://fuxiao0719.github.io/projects/geowizard/)


#### <summary>Scene Coordinate Reconstruction: Posing of Image Collections via Incremental Learning of a Relocalizer
Authors: Eric Brachmann, Jamie Wynn, Shuai Chen, Tommaso Cavallari, Áron Monszpart, Daniyar Turmukhambetov, Victor Adrian Prisacariu
<details span>
<summary><b>Abstract</b></summary>
We address the task of estimating camera parameters from a set of images depicting a scene. Popular feature-based structure-from-motion (SfM) tools solve this task by incremental reconstruction: they repeat triangulation of sparse 3D points and registration of more camera views to the sparse point cloud. We re-interpret incremental structure-from-motion as an iterated application and refinement of a visual relocalizer, that is, of a method that registers new views to the current state of the reconstruction. This perspective allows us to investigate alternative visual relocalizers that are not rooted in local feature matching. We show that scene coordinate regression, a learning-based relocalization approach, allows us to build implicit, neural scene representations from unposed images. Different from other learning-based reconstruction methods, we do not require pose priors nor sequential inputs, and we optimize efficiently over thousands of images. Our method, ACE0 (ACE Zero), estimates camera poses to an accuracy comparable to feature-based SfM, as demonstrated by novel view synthesis.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/34d4a7d4-8c1a-46d8-9242-dd43f022abf1)

 
</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.14351) | [⌨️ Code] | [🌐 Project Page](https://nianticlabs.github.io/acezero/)


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



#### <summary>Incremental Joint Learning of Depth, Pose and Implicit Scene Representation on Monocular Camera in Large-scale Scenes
Authors: Tianchen Deng, Nailin Wang, Chongdi Wang, Shenghai Yuan, Jingchuan Wang, Danwei Wang, Weidong Chen
<details span>
<summary><b>Abstract</b></summary>
Dense scene reconstruction for photo-realistic view synthesis has various applications, such as VR/AR, autonomous vehicles. However, most existing methods have difficulties in large-scale scenes due to three core challenges: \textit{(a) inaccurate depth input.} Accurate depth input is impossible to get in real-world large-scale scenes. \textit{(b) inaccurate pose estimation.} Most existing approaches rely on accurate pre-estimated camera poses. \textit{(c) insufficient scene representation capability.} A single global radiance field lacks the capacity to effectively scale to large-scale scenes. To this end, we propose an incremental joint learning framework, which can achieve accurate depth, pose estimation, and large-scale scene reconstruction. A vision transformer-based network is adopted as the backbone to enhance performance in scale information estimation. For pose estimation, a feature-metric bundle adjustment (FBA) method is designed for accurate and robust camera tracking in large-scale scenes. In terms of implicit scene representation, we propose an incremental scene representation method to construct the entire large-scale scene as multiple local radiance fields to enhance the scalability of 3D scene representation. Extended experiments have been conducted to demonstrate the effectiveness and accuracy of our method in depth estimation, pose estimation, and large-scale scene reconstruction.

![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/f206f299-4ba0-4cad-8813-397642aecc4c)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.06050.pdf) | [⌨️ Code] | [🌐 Project Page]


#### <summary>X-Ray: A Sequential 3D Representation for Generation
Authors: Tao Hu, Wenhang Ge, Yuyang Zhao, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
In this paper, we introduce X-Ray, an innovative approach to 3D generation that employs a new sequential representation, drawing inspiration from the depth-revealing capabilities of X-Ray scans to meticulously capture both the external and internal features of objects. Central to our method is the utilization of ray casting techniques originating from the camera's viewpoint, meticulously recording the geometric and textural details encountered across all intersected surfaces. This process efficiently condenses complete objects or scenes into a multi-frame format, just like videos. Such a structure ensures the 3D representation is composed solely of critical surface information. Highlighting the practicality and adaptability of our X-Ray representation, we showcase its utility in synthesizing 3D objects, employing a network architecture akin to that used in video diffusion models. The outcomes reveal our representation's superior performance in enhancing both the accuracy and efficiency of 3D synthesis, heralding new directions for ongoing research and practical implementations in the field.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/71b52e28-f69a-4aa6-acc3-257e7bf176ff)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.14329) | [⌨️ Code](https://github.com/tau-yihouxiang/X-Ray) | [🌐 Project Page](https://tau-yihouxiang.github.io/projects/X-Ray/X-Ray.html)


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



#### <summary>FDCE-Net: Underwater Image Enhancement with Embedding Frequency and Dual Color Encoder
Authors: Zheng Cheng, Guodong Fan, Jingchun Zhou, Min Gan, C. L. Philip Chen
<details span>
<summary><b>Abstract</b></summary>
Underwater images often suffer from various issues such as low brightness, color shift, blurred details, and noise due to light absorption and scattering caused by water and suspended particles. Previous underwater image enhancement (UIE) methods have primarily focused on spatial domain enhancement, neglecting the frequency domain information inherent in the images. However, the degradation factors of underwater images are closely intertwined in the spatial domain. Although certain methods focus on enhancing images in the frequency domain, they overlook the inherent relationship between the image degradation factors and the information present in the frequency domain. As a result, these methods frequently enhance certain attributes of the improved image while inadequately addressing or even exacerbating other attributes. Moreover, many existing methods heavily rely on prior knowledge to address color shift problems in underwater images, limiting their flexibility and robustness. In order to overcome these limitations, we propose the Embedding Frequency and Dual Color Encoder Network (FDCE-Net) in our paper. The FDCE-Net consists of two main structures: (1) Frequency Spatial Network (FS-Net) aims to achieve initial enhancement by utilizing our designed Frequency Spatial Residual Block (FSRB) to decouple image degradation factors in the frequency domain and enhance different attributes separately. (2) To tackle the color shift issue, we introduce the Dual-Color Encoder (DCE). The DCE establishes correlations between color and semantic representations through cross-attention and leverages multi-scale image features to guide the optimization of adaptive color query. The final enhanced images are generated by combining the outputs of FS-Net and DCE through a fusion network. These images exhibit rich details, clear textures, low noise and natural colors.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f2446a04-8398-4820-afb6-f97dd20fc309)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.17936) | [⌨️ Code](https://github.com/Alexande-rChan/FDCE-Net) | [🌐 Project Page]

#### <summary>Q-GroundCAM: Quantifying Grounding in Vision Language Models via GradCAM
Authors: Navid Rajabi, Jana Kosecka
<details span>
<summary><b>Abstract</b></summary>
Vision and Language Models (VLMs) continue to demonstrate remarkable zero-shot (ZS) performance across various tasks. However, many probing studies have revealed that even the best-performing VLMs struggle to capture aspects of compositional scene understanding, lacking the ability to properly ground and localize linguistic phrases in images. Recent VLM advancements include scaling up both model and dataset sizes, additional training objectives and levels of supervision, and variations in the model architectures. To characterize the grounding ability of VLMs, such as phrase grounding, referring expressions comprehension, and relationship understanding, Pointing Game has been used as an evaluation metric for datasets with bounding box annotations. In this paper, we introduce a novel suite of quantitative metrics that utilize GradCAM activations to rigorously evaluate the grounding capabilities of pre-trained VLMs like CLIP, BLIP, and ALBEF. These metrics offer an explainable and quantifiable approach for a more detailed comparison of the zero-shot capabilities of VLMs and enable measuring models' grounding uncertainty. This characterization reveals interesting tradeoffs between the size of the model, the dataset size, and their performance.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/7c0e8c77-e9df-4648-93d4-2627040406d2)

</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.19128) | [⌨️ Code](https://github.com/NavidRajabi/Q-GroundCAM) | [🌐 Project Page]


#### <summary>MonoPatchNeRF: Improving Neural Radiance Fields with Patch-based Monocular Guidance
Authors: Yuqun Wu, Jae Yong Lee, Chuhang Zou, Shenlong Wang, Derek Hoiem
<details span>
<summary><b>Abstract</b></summary>
The latest regularized Neural Radiance Field (NeRF) approaches produce poor geometry and view extrapolation for multiview stereo (MVS) benchmarks such as ETH3D. In this paper, we aim to create 3D models that provide accurate geometry and view synthesis, partially closing the large geometric performance gap between NeRF and traditional MVS methods. We propose a patch-based approach that effectively leverages monocular surface normal and relative depth predictions. The patch-based ray sampling also enables the appearance regularization of normalized cross-correlation (NCC) and structural similarity (SSIM) between randomly sampled virtual and training views. We further show that "density restrictions" based on sparse structure-from-motion points can help greatly improve geometric accuracy with a slight drop in novel view synthesis metrics. Our experiments show 4x the performance of RegNeRF and 8x that of FreeNeRF on average F1@2cm for ETH3D MVS benchmark, suggesting a fruitful research direction to improve the geometric accuracy of NeRF-based models, and sheds light on a potential future approach to enable NeRF-based optimization to eventually outperform traditional MVS.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/152c4033-c403-4b7c-8b48-cef2d27de373)

</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.08252) | [⌨️ Code] | [🌐 Project Page](https://yuqunw.github.io/MonoPatchNeRF/)

#### <summary>Depth Priors in Removal Neural Radiance Fields
Authors: Zhihao Guo, Peng Wang
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRF) have shown impressive results in 3D reconstruction and generating novel views. A key challenge within NeRF is the editing of reconstructed scenes, such as object removal, which requires maintaining consistency across multiple views and ensuring high-quality synthesised perspectives. Previous studies have incorporated depth priors, typically from LiDAR or sparse depth measurements provided by COLMAP, to improve the performance of object removal in NeRF. However, these methods are either costly or time-consuming. In this paper, we propose a novel approach that integrates monocular depth estimates with NeRF-based object removal models to significantly reduce time consumption and enhance the robustness and quality of scene generation and object removal. We conducted a thorough evaluation of COLMAP's dense depth reconstruction on the KITTI dataset to verify its accuracy in depth map generation. Our findings suggest that COLMAP can serve as an effective alternative to a ground truth depth map where such information is missing or costly to obtain. Additionally, we integrated various monocular depth estimation methods into the removal NeRF model, i.e., SpinNeRF, to assess their capacity to improve object removal performance. Our experimental results highlight the potential of monocular depth estimation to substantially improve NeRF applications.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0e41b9d8-486f-4608-bdeb-94ecaee77a37)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.00630) | [⌨️ Code] | [🌐 Project Page]


#### <summary>NC-SDF: Enhancing Indoor Scene Reconstruction Using Neural SDFs with View-Dependent Normal Compensation
Authors: Ziyi Chen, Xiaolong Wu, Yu Zhang
<details span>
<summary><b>Abstract</b></summary>
State-of-the-art neural implicit surface representations have achieved impressive results in indoor scene reconstruction by incorporating monocular geometric priors as additional supervision. However, we have observed that multi-view inconsistency between such priors poses a challenge for high-quality reconstructions. In response, we present NC-SDF, a neural signed distance field (SDF) 3D reconstruction framework with view-dependent normal compensation (NC). Specifically, we integrate view-dependent biases in monocular normal priors into the neural implicit representation of the scene. By adaptively learning and correcting the biases, our NC-SDF effectively mitigates the adverse impact of inconsistent supervision, enhancing both the global consistency and local details in the reconstructions. To further refine the details, we introduce an informative pixel sampling strategy to pay more attention to intricate geometry with higher information content. Additionally, we design a hybrid geometry modeling approach to improve the neural implicit representation. Experiments on synthetic and real-world datasets demonstrate that NC-SDF outperforms existing approaches in terms of reconstruction quality.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0cc64342-05d2-44c1-adeb-c5aac96d1311)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.00340) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Learning High-Quality Navigation and Zooming on Omnidirectional Images in Virtual Reality
Authors: Zidong Cao, Zhan Wang, Yexin Liu, Yan-Pei Cao, Ying Shan, Wei Zeng, Lin Wang
<details span>
<summary><b>Abstract</b></summary>
Viewing omnidirectional images (ODIs) in virtual reality (VR) represents a novel form of media that provides immersive experiences for users to navigate and interact with digital content. Nonetheless, this sense of immersion can be greatly compromised by a blur effect that masks details and hampers the user's ability to engage with objects of interest. In this paper, we present a novel system, called OmniVR, designed to enhance visual clarity during VR navigation. Our system enables users to effortlessly locate and zoom in on the objects of interest in VR. It captures user commands for navigation and zoom, converting these inputs into parameters for the Mobius transformation matrix. Leveraging these parameters, the ODI is refined using a learning-based algorithm. The resultant ODI is presented within the VR media, effectively reducing blur and increasing user engagement. To verify the effectiveness of our system, we first evaluate our algorithm with state-of-the-art methods on public datasets, which achieves the best performance. Furthermore, we undertake a comprehensive user study to evaluate viewer experiences across diverse scenarios and to gather their qualitative feedback from multiple perspectives. The outcomes reveal that our system enhances user engagement by improving the viewers' recognition, reducing discomfort, and improving the overall immersive experience. Our system makes the navigation and zoom more user-friendly.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/dbca84db-2208-4c10-8912-91fdb176d4fa)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.00351) | [⌨️ Code] | [🌐 Project Page]


#### <summary>3D Neural Edge Reconstruction
Authors: Lei Li, Songyou Peng, Zehao Yu, Shaohui Liu, Rémi Pautrat, Xiaochuan Yin, Marc Pollefeys
<details span>
<summary><b>Abstract</b></summary>
Real-world objects and environments are predominantly composed of edge features, including straight lines and curves. Such edges are crucial elements for various applications, such as CAD modeling, surface meshing, lane mapping, etc. However, existing traditional methods only prioritize lines over curves for simplicity in geometric modeling. To this end, we introduce EMAP, a new method for learning 3D edge representations with a focus on both lines and curves. Our method implicitly encodes 3D edge distance and direction in Unsigned Distance Functions (UDF) from multi-view edge maps. On top of this neural representation, we propose an edge extraction algorithm that robustly abstracts parametric 3D edges from the inferred edge points and their directions. Comprehensive evaluations demonstrate that our method achieves better 3D edge reconstruction on multiple challenging datasets. We further show that our learned UDF field enhances neural surface reconstruction by capturing more details.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/b6566200-16c5-4765-bc3b-1453681f5f54)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.19295) | [⌨️ Code](https://github.com/cvg/EMAP) | [🌐 Project Page](https://neural-edge-map.github.io/)


#### <summary>Language-Image Models with 3D Understanding
Authors: Jang Hyun Cho, Boris Ivanovic, Yulong Cao, Edward Schmerling, Yue Wang, Xinshuo Weng, Boyi Li, Yurong You, Philipp Krähenbühl, Yan Wang, Marco Pavone
<details span>
<summary><b>Abstract</b></summary>
Multi-modal large language models (MLLMs) have shown incredible capabilities in a variety of 2D vision and language tasks. We extend MLLMs' perceptual capabilities to ground and reason about images in 3-dimensional space. To that end, we first develop a large-scale pre-training dataset for 2D and 3D called LV3D by combining multiple existing 2D and 3D recognition datasets under a common task formulation: as multi-turn question-answering. Next, we introduce a new MLLM named Cube-LLM and pre-train it on LV3D. We show that pure data scaling makes a strong 3D perception capability without 3D specific architectural design or training objective. Cube-LLM exhibits intriguing properties similar to LLMs: (1) Cube-LLM can apply chain-of-thought prompting to improve 3D understanding from 2D context information. (2) Cube-LLM can follow complex and diverse instructions and adapt to versatile input and output formats. (3) Cube-LLM can be visually prompted such as 2D box or a set of candidate 3D boxes from specialists. Our experiments on outdoor benchmarks demonstrate that Cube-LLM significantly outperforms existing baselines by 21.3 points of AP-BEV on the Talk2Car dataset for 3D grounded reasoning and 17.7 points on the DriveLM dataset for complex reasoning about driving scenarios, respectively. Cube-LLM also shows competitive results in general MLLM benchmarks such as refCOCO for 2D grounding with (87.0) average score, as well as visual question answering benchmarks such as VQAv2, GQA, SQA, POPE, etc. for complex reasoning.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/be254ac5-5f0c-49bc-b8ae-2912656fe2a7)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.03685) | [⌨️ Code] | [🌐 Project Page](https://janghyuncho.github.io/Cube-LLM/)


#### <summary>ActiveNeuS: Active 3D Reconstruction using Neural Implicit Surface Uncertainty
Authors: Hyunseo Kim, Hyeonseo Yang, Taekyung Kim, YoonSung Kim, Jin-Hwa Kim, Byoung-Tak Zhang
<details span>
<summary><b>Abstract</b></summary>
Active learning in 3D scene reconstruction has been widely studied, as selecting informative training views is critical for the reconstruction. Recently, Neural Radiance Fields (NeRF) variants have shown performance increases in active 3D reconstruction using image rendering or geometric uncertainty. However, the simultaneous consideration of both uncertainties in selecting informative views remains unexplored, while utilizing different types of uncertainty can reduce the bias that arises in the early training stage with sparse inputs. In this paper, we propose ActiveNeuS, which evaluates candidate views considering both uncertainties. ActiveNeuS provides a way to accumulate image rendering uncertainty while avoiding the bias that the estimated densities can introduce. ActiveNeuS computes the neural implicit surface uncertainty, providing the color uncertainty along with the surface information. It efficiently handles the bias by using the surface information and a grid, enabling the fast selection of diverse viewpoints. Our method outperforms previous works on popular datasets, Blender and DTU, showing that the views selected by ActiveNeuS significantly improve performance.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/86250036-8935-4f2f-8c35-260ef3867ac6)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.02568) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Rip-NeRF: Anti-aliasing Radiance Fields with Ripmap-Encoded Platonic Solids
Authors: Junchen Liu, Wenbo Hu, Zhuo Yang, Jianteng Chen, Guoliang Wang, Xiaoxue Chen, Yantong Cai, Huan-ang Gao, Hao Zhao
<details span>
<summary><b>Abstract</b></summary>
Despite significant advancements in Neural Radiance Fields (NeRFs), the renderings may still suffer from aliasing and blurring artifacts, since it remains a fundamental challenge to effectively and efficiently characterize anisotropic areas induced by the cone-casting procedure. This paper introduces a Ripmap-Encoded Platonic Solid representation to precisely and efficiently featurize 3D anisotropic areas, achieving high-fidelity anti-aliasing renderings. Central to our approach are two key components: Platonic Solid Projection and Ripmap encoding. The Platonic Solid Projection factorizes the 3D space onto the unparalleled faces of a certain Platonic solid, such that the anisotropic 3D areas can be projected onto planes with distinguishable characterization. Meanwhile, each face of the Platonic solid is encoded by the Ripmap encoding, which is constructed by anisotropically pre-filtering a learnable feature grid, to enable featurzing the projected anisotropic areas both precisely and efficiently by the anisotropic area-sampling. Extensive experiments on both well-established synthetic datasets and a newly captured real-world dataset demonstrate that our Rip-NeRF attains state-of-the-art rendering quality, particularly excelling in the fine details of repetitive structures and textures, while maintaining relatively swift training times.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/968d4e4b-9f64-41df-b5eb-76f8293ab5e1)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.02386) | [⌨️ Code](https://github.com/JunchenLiu77/Rip-NeRF) | [🌐 Project Page](https://junchenliu77.github.io/Rip-NeRF/)

#### <summary>Matten: Video Generation with Mamba-Attention
Authors: Yu Gao, Jiancheng Huang, Xiaopeng Sun, Zequn Jie, Yujie Zhong, Lin Ma
<details span>
<summary><b>Abstract</b></summary>
In this paper, we introduce Matten, a cutting-edge latent diffusion model with Mamba-Attention architecture for video generation. With minimal computational cost, Matten employs spatial-temporal attention for local video content modeling and bidirectional Mamba for global video content modeling. Our comprehensive experimental evaluation demonstrates that Matten has competitive performance with the current Transformer-based and GAN-based models in benchmark performance, achieving superior FVD scores and efficiency. Additionally, we observe a direct positive correlation between the complexity of our designed model and the improvement in video quality, indicating the excellent scalability of Matten.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0ee1f7a4-25e7-4ada-af07-9386762e214c)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.03025) | [⌨️ Code] | [🌐 Project Page]

#### <summary>FinePOSE: Fine-Grained Prompt-Driven 3D Human Pose Estimation via Diffusion Models
Authors: Jinglin Xu, Yijie Guo, Yuxin Peng
<details span>
<summary><b>Abstract</b></summary>
The 3D Human Pose Estimation (3D HPE) task uses 2D images or videos to predict human joint coordinates in 3D space. Despite recent advancements in deep learning-based methods, they mostly ignore the capability of coupling accessible texts and naturally feasible knowledge of humans, missing out on valuable implicit supervision to guide the 3D HPE task. Moreover, previous efforts often study this task from the perspective of the whole human body, neglecting fine-grained guidance hidden in different body parts. To this end, we present a new Fine-Grained Prompt-Driven Denoiser based on a diffusion model for 3D HPE, named \textbf{FinePOSE}. It consists of three core blocks enhancing the reverse process of the diffusion model: (1) Fine-grained Part-aware Prompt learning (FPP) block constructs fine-grained part-aware prompts via coupling accessible texts and naturally feasible knowledge of body parts with learnable prompts to model implicit guidance. (2) Fine-grained Prompt-pose Communication (FPC) block establishes fine-grained communications between learned part-aware prompts and poses to improve the denoising quality. (3) Prompt-driven Timestamp Stylization (PTS) block integrates learned prompt embedding and temporal information related to the noise level to enable adaptive adjustment at each denoising step. Extensive experiments on public single-human pose estimation datasets show that FinePOSE outperforms state-of-the-art methods. We further extend FinePOSE to multi-human pose estimation. Achieving 34.3mm average MPJPE on the EgoHumans dataset demonstrates the potential of FinePOSE to deal with complex multi-human scenarios.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/5e07eac6-fc31-4de4-b8db-fed2ccb566bd)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.05216) | [⌨️ Code](https://github.com/PKU-ICST-MIPL/FinePOSE_CVPR2024) | [🌐 Project Page]

#### <summary>M2DNeRF: Multi-Modal Decomposition NeRF with 3D Feature Fields
Authors: Ning Wang, Lefei Zhang, Angel X Chang
<details span>
<summary><b>Abstract</b></summary>
Neural fields (NeRF) have emerged as a promising approach for representing continuous 3D scenes. Nevertheless, the lack of semantic encoding in NeRFs poses a significant challenge for scene decomposition. To address this challenge, we present a single model, Multi-Modal Decomposition NeRF (M2DNeRF), that is capable of both text-based and visual patch-based edits. Specifically, we use multi-modal feature distillation to integrate teacher features from pretrained visual and language models into 3D semantic feature volumes, thereby facilitating consistent 3D editing. To enforce consistency between the visual and language features in our 3D feature volumes, we introduce a multi-modal similarity constraint. We also introduce a patch-based joint contrastive loss that helps to encourage object-regions to coalesce in the 3D feature space, resulting in more precise boundaries. Experiments on various real-world scenes show superior performance in 3D scene decomposition tasks compared to prior NeRF-based methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9a3eeb43-520a-466e-bc61-9bd2754cd3d8)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.05010) | [⌨️ Code] | [🌐 Project Page]




#### <summary>MambaOut: Do We Really Need Mamba for Vision?
Authors: Weihao Yu, Xinchao Wang
<details span>
<summary><b>Abstract</b></summary>
Mamba, an architecture with RNN-like token mixer of state space model (SSM), was recently introduced to address the quadratic complexity of the attention mechanism and subsequently applied to vision tasks. Nevertheless, the performance of Mamba for vision is often underwhelming when compared with convolutional and attention-based models. In this paper, we delve into the essence of Mamba, and conceptually conclude that Mamba is ideally suited for tasks with long-sequence and autoregressive characteristics. For vision tasks, as image classification does not align with either characteristic, we hypothesize that Mamba is not necessary for this task; Detection and segmentation tasks are also not autoregressive, yet they adhere to the long-sequence characteristic, so we believe it is still worthwhile to explore Mamba's potential for these tasks. To empirically verify our hypotheses, we construct a series of models named \emph{MambaOut} through stacking Mamba blocks while removing their core token mixer, SSM. Experimental results strongly support our hypotheses. Specifically, our MambaOut model surpasses all visual Mamba models on ImageNet image classification, indicating that Mamba is indeed unnecessary for this task. As for detection and segmentation, MambaOut cannot match the performance of state-of-the-art visual Mamba models, demonstrating the potential of Mamba for long-sequence visual tasks.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/35d2e85b-1a24-4041-96bf-2dc79c7ec56c)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.07992) | [⌨️ Code](https://github.com/yuweihao/MambaOut) | [🌐 Project Page]

#### <summary>Synergistic Integration of Coordinate Network and Tensorial Feature for Improving Neural Radiance Fields from Sparse Inputs
Authors: Mingyu Kim, Jun-Seong Kim, Se-Young Yun, Jin-Hwa Kim
<details span>
<summary><b>Abstract</b></summary>
The multi-plane representation has been highlighted for its fast training and inference across static and dynamic neural radiance fields. This approach constructs relevant features via projection onto learnable grids and interpolating adjacent vertices. However, it has limitations in capturing low-frequency details and tends to overuse parameters for low-frequency features due to its bias toward fine details, despite its multi-resolution concept. This phenomenon leads to instability and inefficiency when training poses are sparse. In this work, we propose a method that synergistically integrates multi-plane representation with a coordinate-based network known for strong bias toward low-frequency signals. The coordinate-based network is responsible for capturing low-frequency details, while the multi-plane representation focuses on capturing fine-grained details. We demonstrate that using residual connections between them seamlessly preserves their own inherent properties. Additionally, the proposed progressive training scheme accelerates the disentanglement of these two features. We empirically show that the proposed method achieves comparable results to explicit encoding with fewer parameters, and particularly, it outperforms others for the static and dynamic NeRFs under sparse inputs.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/47f6b29c-231d-45bd-a2d3-42f10dab51cb)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.07857) | [⌨️ Code](https://github.com/MingyuKim87/SynergyNeRF) | [🌐 Project Page](https://mingyukim87.github.io/SynergyNeRF/)

#### <summary>A Simple Approach to Differentiable Rendering of SDFs
Authors: Zichen Wang, Xi Deng, Ziyi Zhang, Wenzel Jakob, Steve Marschner
<details span>
<summary><b>Abstract</b></summary>
We present a simple algorithm for differentiable rendering of surfaces represented by Signed Distance Fields (SDF), which makes it easy to integrate rendering into gradient-based optimization pipelines. To tackle visibility-related derivatives that make rendering non-differentiable, existing physically based differentiable rendering methods often rely on elaborate guiding data structures or reparameterization with a global impact on variance. In this article, we investigate an alternative that embraces nonzero bias in exchange for low variance and architectural simplicity. Our method expands the lower-dimensional boundary integral into a thin band that is easy to sample when the underlying surface is represented by an SDF. We demonstrate the performance and robustness of our formulation in end-to-end inverse rendering tasks, where it obtains results that are competitive with or superior to existing work.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d53189f0-df37-498d-9704-18dcb369f54f)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.08733) | [⌨️ Code] | [🌐 Project Page]

#### <summary>RobustMVS: Single Domain Generalized Deep Multi-view Stereo
Authors: Hongbin Xu, Weitao Chen, Baigui Sun, Xuansong Xie, Wenxiong Kang
<details span>
<summary><b>Abstract</b></summary>
Despite the impressive performance of Multi-view Stereo (MVS) approaches given plenty of training samples, the performance degradation when generalizing to unseen domains has not been clearly explored yet. In this work, we focus on the domain generalization problem in MVS. To evaluate the generalization results, we build a novel MVS domain generalization benchmark including synthetic and real-world datasets. In contrast to conventional domain generalization benchmarks, we consider a more realistic but challenging scenario, where only one source domain is available for training. The MVS problem can be analogized back to the feature matching task, and maintaining robust feature consistency among views is an important factor for improving generalization performance. To address the domain generalization problem in MVS, we propose a novel MVS framework, namely RobustMVS. A DepthClustering-guided Whitening (DCW) loss is further introduced to preserve the feature consistency among different views, which decorrelates multi-view features from viewpoint-specific style information based on geometric priors from depth maps. The experimental results further show that our method achieves superior performance on the domain generalization benchmark.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3dfaa398-6f1a-491c-89c5-996ebfb8bb2a)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.09131) | [⌨️ Code](https://github.com/ToughStoneX/Robust-MVS) | [🌐 Project Page]


#### <summary>Grounding DINO 1.5: Advance the "Edge" of Open-Set Object Detection
Authors: Tianhe Ren, Qing Jiang, Shilong Liu, Zhaoyang Zeng, Wenlong Liu, Han Gao, Hongjie Huang, Zhengyu Ma, Xiaoke Jiang, Yihao Chen, Yuda Xiong, Hao Zhang, Feng Li, Peijun Tang, Kent Yu, Lei Zhang
<details span>
<summary><b>Abstract</b></summary>
This paper introduces Grounding DINO 1.5, a suite of advanced open-set object detection models developed by IDEA Research, which aims to advance the "Edge" of open-set object detection. The suite encompasses two models: Grounding DINO 1.5 Pro, a high-performance model designed for stronger generalization capability across a wide range of scenarios, and Grounding DINO 1.5 Edge, an efficient model optimized for faster speed demanded in many applications requiring edge deployment. The Grounding DINO 1.5 Pro model advances its predecessor by scaling up the model architecture, integrating an enhanced vision backbone, and expanding the training dataset to over 20 million images with grounding annotations, thereby achieving a richer semantic understanding. The Grounding DINO 1.5 Edge model, while designed for efficiency with reduced feature scales, maintains robust detection capabilities by being trained on the same comprehensive dataset. Empirical results demonstrate the effectiveness of Grounding DINO 1.5, with the Grounding DINO 1.5 Pro model attaining a 54.3 AP on the COCO detection benchmark and a 55.7 AP on the LVIS-minival zero-shot transfer benchmark, setting new records for open-set object detection. Furthermore, the Grounding DINO 1.5 Edge model, when optimized with TensorRT, achieves a speed of 75.2 FPS while attaining a zero-shot performance of 36.2 AP on the LVIS-minival benchmark, making it more suitable for edge computing scenarios.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/095d0f10-5fe2-440c-a3f0-bc7e0f3ddb05)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.10300) | [⌨️ Code] | [🌐 Project Page](https://deepdataspace.com/home)


#### <summary>GEOcc: Geometrically Enhanced 3D Occupancy Network with Implicit-Explicit Depth Fusion and Contextual Self-Supervision
Authors: Xin Tan, Wenbin Wu, Zhiwei Zhang, Chaojie Fan, Yong Peng, Zhizhong Zhang, Yuan Xie, Lizhuang Ma
<details span>
<summary><b>Abstract</b></summary>
3D occupancy perception holds a pivotal role in recent vision-centric autonomous driving systems by converting surround-view images into integrated geometric and semantic representations within dense 3D grids. Nevertheless, current models still encounter two main challenges: modeling depth accurately in the 2D-3D view transformation stage, and overcoming the lack of generalizability issues due to sparse LiDAR supervision. To address these issues, this paper presents GEOcc, a Geometric-Enhanced Occupancy network tailored for vision-only surround-view perception. Our approach is three-fold: 1) Integration of explicit lift-based depth prediction and implicit projection-based transformers for depth modeling, enhancing the density and robustness of view transformation. 2) Utilization of mask-based encoder-decoder architecture for fine-grained semantic predictions; 3) Adoption of context-aware self-training loss functions in the pertaining stage to complement LiDAR supervision, involving the re-rendering of 2D depth maps from 3D occupancy features and leveraging image reconstruction loss to obtain denser depth supervision besides sparse LiDAR ground-truths. Our approach achieves State-Of-The-Art performance on the Occ3D-nuScenes dataset with the least image resolution needed and the most weightless image backbone compared with current models, marking an improvement of 3.3% due to our proposed contributions. Comprehensive experimentation also demonstrates the consistent superiority of our method over baselines and alternative approaches.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/715c4890-3386-4326-91da-0c7888ed9594)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.10591) | [⌨️ Code] | [🌐 Project Page]

#### <summary>NeRO: Neural Road Surface Reconstruction
Authors: Ruibo Wang, Song Zhang, Ping Huang, Donghai Zhang, Haoyu Chen
<details span>
<summary><b>Abstract</b></summary>
In computer vision and graphics, the accurate reconstruction of road surfaces is pivotal for various applications, especially in autonomous driving. This paper introduces a novel method leveraging the Multi-Layer Perceptrons (MLPs) framework to reconstruct road surfaces in height, color, and semantic information by input world coordinates x and y. Our approach NeRO uses encoding techniques based on MLPs, significantly improving the performance of the complex details, speeding up the training speed, and reducing neural network size. The effectiveness of this method is demonstrated through its superior performance, which indicates a promising direction for rendering road surfaces with semantics applications, particularly in applications demanding visualization of road conditions, 4D labeling, and semantic groupings.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/337a5755-d649-4002-8c1b-c0d35c935da4)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.10554) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Nonparametric Teaching of Implicit Neural Representations
Authors: Chen Zhang, Steven Tin Sui Luo, Jason Chun Lok Li, Yik-Chung Wu, Ngai Wong
<details span>
<summary><b>Abstract</b></summary>
We investigate the learning of implicit neural representation (INR) using an overparameterized multilayer perceptron (MLP) via a novel nonparametric teaching perspective. The latter offers an efficient example selection framework for teaching nonparametrically defined (viz. non-closed-form) target functions, such as image functions defined by 2D grids of pixels. To address the costly training of INRs, we propose a paradigm called Implicit Neural Teaching (INT) that treats INR learning as a nonparametric teaching problem, where the given signal being fitted serves as the target function. The teacher then selects signal fragments for iterative training of the MLP to achieve fast convergence. By establishing a connection between MLP evolution through parameter-based gradient descent and that of function evolution through functional gradient descent in nonparametric teaching, we show for the first time that teaching an overparameterized MLP is consistent with teaching a nonparametric learner. This new discovery readily permits a convenient drop-in of nonparametric teaching algorithms to broadly enhance INR training efficiency, demonstrating 30%+ training time savings across various input modalities.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/851d1748-05ef-49a3-8f3c-fcd76bb5284e)


</details>

[📃 arXiv:2405](https://export.arxiv.org/pdf/2405.10531) | [⌨️ Code] | [🌐 Project Page]

#### <summary>NPLMV-PS: Neural Point-Light Multi-View Photometric Stereo
Authors: Fotios Logothetis, Ignas Budvytis, Roberto Cipolla
<details span>
<summary><b>Abstract</b></summary>
In this work we present a novel multi-view photometric stereo (PS) method. Like many works in 3D reconstruction we are leveraging neural shape representations and learnt renderers. However, our work differs from the state-of-the-art multi-view PS methods such as PS-NeRF or SuperNormal we explicity leverage per-pixel intensity renderings rather than relying mainly on estimated normals.
We model point light attenuation and explicitly raytrace cast shadows in order to best approximate each points incoming radiance. This is used as input to a fully neural material renderer that uses minimal prior assumptions and it is jointly optimised with the surface. Finally, estimated normal and segmentation maps can also incorporated in order to maximise the surface accuracy.
Our method is among the first to outperform the classical approach of DiLiGenT-MV and achieves average 0.2mm Chamfer distance for objects imaged at approx 1.5m distance away with approximate 400x400 resolution. Moreover, we show robustness to poor normals in low light count scenario, achieving 0.27mm Chamfer distance when pixel rendering is used instead of estimated normals.



</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12057) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Dusk Till Dawn: Self-supervised Nighttime Stereo Depth Estimation using Visual Foundation Models
Authors: Madhu Vankadari, Samuel Hodgson, Sangyun Shin, Kaichen Zhou Andrew Markham, Niki Trigoni
<details span>
<summary><b>Abstract</b></summary>
Self-supervised depth estimation algorithms rely heavily on frame-warping relationships, exhibiting substantial performance degradation when applied in challenging circumstances, such as low-visibility and nighttime scenarios with varying illumination conditions. Addressing this challenge, we introduce an algorithm designed to achieve accurate self-supervised stereo depth estimation focusing on nighttime conditions. Specifically, we use pretrained visual foundation models to extract generalised features across challenging scenes and present an efficient method for matching and integrating these features from stereo frames. Moreover, to prevent pixels violating photometric consistency assumption from negatively affecting the depth predictions, we propose a novel masking approach designed to filter out such pixels. Lastly, addressing weaknesses in the evaluation of current depth estimation algorithms, we present novel evaluation metrics. Our experiments, conducted on challenging datasets including Oxford RobotCar and Multi-Spectral Stereo, demonstrate the robust improvements realized by our approach.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/136ab000-6390-4df6-85af-643362bdbbad)

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.11158) | [⌨️ Code](https://github.com/madhubabuv/dtd) | [🌐 Project Page]






#### <summary>OmniGlue: Generalizable Feature Matching with Foundation Model Guidance
Authors: Hanwen Jiang, Arjun Karpur, Bingyi Cao, Qixing Huang, Andre Araujo
<details span>
<summary><b>Abstract</b></summary>
The image matching field has been witnessing a continuous emergence of novel learnable feature matching techniques, with ever-improving performance on conventional benchmarks. However, our investigation shows that despite these gains, their potential for real-world applications is restricted by their limited generalization capabilities to novel image domains. In this paper, we introduce OmniGlue, the first learnable image matcher that is designed with generalization as a core principle. OmniGlue leverages broad knowledge from a vision foundation model to guide the feature matching process, boosting generalization to domains not seen at training time. Additionally, we propose a novel keypoint position-guided attention mechanism which disentangles spatial and appearance information, leading to enhanced matching descriptors. We perform comprehensive experiments on a suite of 7 datasets with varied image domains, including scene-level, object-centric and aerial images. OmniGlue's novel components lead to relative gains on unseen domains of 20.9% with respect to a directly comparable reference model, while also outperforming the recent LightGlue method by 9.5% relatively.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/00e16630-dc75-4ec2-bd85-858228ff4809)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12979) | [⌨️ Code](https://github.com/google-research/omniglue) | [🌐 Project Page](https://hwjiang1510.github.io/OmniGlue/)


#### <summary>Rethink Predicting the Optical Flow with the Kinetics Perspective
Authors: Yuhao Cheng, Siru Zhang, Yiqiang Yan
<details span>
<summary><b>Abstract</b></summary>
Optical flow estimation is one of the fundamental tasks in low-level computer vision, which describes the pixel-wise displacement and can be used in many other tasks. From the apparent aspect, the optical flow can be viewed as the correlation between the pixels in consecutive frames, so continuously refining the correlation volume can achieve an outstanding performance. However, it will make the method have a catastrophic computational complexity. Not only that, the error caused by the occlusion regions of the successive frames will be amplified through the inaccurate warp operation. These challenges can not be solved only from the apparent view, so this paper rethinks the optical flow estimation from the kinetics viewpoint.We propose a method combining the apparent and kinetics information from this motivation. The proposed method directly predicts the optical flow from the feature extracted from images instead of building the correlation volume, which will improve the efficiency of the whole network. Meanwhile, the proposed method involves a new differentiable warp operation that simultaneously considers the warping and occlusion. Moreover, the proposed method blends the kinetics feature with the apparent feature through the novel self-supervised loss function. Furthermore, comprehensive experiments and ablation studies prove that the proposed novel insight into how to predict the optical flow can achieve the better performance of the state-of-the-art methods, and in some metrics, the proposed method outperforms the correlation-based method, especially in situations containing occlusion and fast moving.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a3c2e981-f565-45cc-a5f6-8bf19661a35d)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.12512) | [⌨️ Code](https://github.com/YuhaoCheng/OpticalFlow_Kinetic) | [🌐 Project Page]


#### <summary>NeurCross: A Self-Supervised Neural Approach for Representing Cross Fields in Quad Mesh Generation
Authors: Qiujie Dong, Huibiao Wen, Rui Xu, Xiaokang Yu, Jiaran Zhou, Shuangmin Chen, Shiqing Xin, Changhe Tu, Wenping Wang
<details span>
<summary><b>Abstract</b></summary>
Quadrilateral mesh generation plays a crucial role in numerical simulations within Computer-Aided Design and Engineering (CAD/E). The quality of the cross field is essential for generating a quadrilateral mesh. In this paper, we propose a self-supervised neural representation of the cross field, named NeurCross, comprising two modules: one to fit the signed distance function (SDF) and another to predict the cross field. Unlike most existing approaches that operate directly on the given polygonal surface, NeurCross takes the SDF as a bridge to allow for SDF overfitting and the prediction of the cross field to proceed simultaneously. By utilizing a neural SDF, we achieve a smooth representation of the base surface, minimizing the impact of piecewise planar discretization and minor surface variations. Moreover, the principal curvatures and directions are fully encoded by the Hessian of the SDF, enabling the regularization of the overall cross field through minor adjustments to the SDF. Compared to state-of-the-art methods, NeurCross significantly improves the placement of singular points and the approximation accuracy between the input triangular surface and the output quad mesh, as demonstrated in the teaser figure.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f7c2fadd-c604-4610-8bc6-5d2c71810df3)


</details>


[📃 arXiv:2405](https://arxiv.org/pdf/2405.13745) | [⌨️ Code] | [🌐 Project Page]

#### <summary>3D Reconstruction with Fast Dipole Sums
Authors: Hanyu Chen, Bailey Miller, Ioannis Gkioulekas
<details span>
<summary><b>Abstract</b></summary>
We introduce a technique for the reconstruction of high-fidelity surfaces from multi-view images. Our technique uses a new point-based representation, the dipole sum, which generalizes the winding number to allow for interpolation of arbitrary per-point attributes in point clouds with noisy or outlier points. Using dipole sums allows us to represent implicit geometry and radiance fields as per-point attributes of a point cloud, which we initialize directly from structure from motion. We additionally derive Barnes-Hut fast summation schemes for accelerated forward and reverse-mode dipole sum queries. These queries facilitate the use of ray tracing to efficiently and differentiably render images with our point-based representations, and thus update their point attributes to optimize scene geometry and appearance. We evaluate this inverse rendering framework against state-of-the-art alternatives, based on ray tracing of neural representations or rasterization of Gaussian point-based representations. Our technique significantly improves reconstruction quality at equal runtimes, while also supporting more general rendering techniques such as shadow rays for direct illumination. In the supplement, we provide interactive visualizations of our results.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/85d3446e-6ea8-4d39-82ee-12fd1aada720)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16788) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Part123: Part-aware 3D Reconstruction from a Single-view Image
Authors: Anran Liu, Cheng Lin, Yuan Liu, Xiaoxiao Long, Zhiyang Dou, Hao-Xiang Guo, Ping Luo, Wenping Wang
<details span>
<summary><b>Abstract</b></summary>
Recently, the emergence of diffusion models has opened up new opportunities for single-view reconstruction. However, all the existing methods represent the target object as a closed mesh devoid of any structural information, thus neglecting the part-based structure, which is crucial for many downstream applications, of the reconstructed shape. Moreover, the generated meshes usually suffer from large noises, unsmooth surfaces, and blurry textures, making it challenging to obtain satisfactory part segments using 3D segmentation techniques. In this paper, we present Part123, a novel framework for part-aware 3D reconstruction from a single-view image. We first use diffusion models to generate multiview-consistent images from a given image, and then leverage Segment Anything Model (SAM), which demonstrates powerful generalization ability on arbitrary objects, to generate multiview segmentation masks. To effectively incorporate 2D part-based information into 3D reconstruction and handle inconsistency, we introduce contrastive learning into a neural rendering framework to learn a part-aware feature space based on the multiview segmentation masks. A clustering-based algorithm is also developed to automatically derive 3D part segmentation results from the reconstructed models. Experiments show that our method can generate 3D models with high-quality segmented parts on various objects. Compared to existing unstructured reconstruction methods, the part-aware 3D models from our method benefit some important applications, including feature-preserving reconstruction, primitive fitting, and 3D shape editing.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/c354e6e3-1255-42ec-986d-fa0ddb89d737)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16888) | [⌨️ Code] | [🌐 Project Page]



#### <summary>PanoNormal: Monocular Indoor 360° Surface Normal Estimation
Authors: Kun Huang, Fanglue Zhang, Neil Dodgson
<details span>
<summary><b>Abstract</b></summary>
The presence of spherical distortion on the Equirectangular image is an acknowledged challenge in dense regression computer vision tasks, such as surface normal estimation. Recent advances in convolutional neural networks (CNNs) strive to mitigate spherical distortion but often fall short in capturing holistic structures effectively, primarily due to their fixed receptive field. On the other hand, vision transformers (ViTs) excel in establishing long-range dependencies through a global self-attention mechanism, yet they encounter limitations in preserving local details. We introduce \textit{PanoNormal}, a monocular surface normal estimation architecture designed for 360° images, which combines the strengths of CNNs and ViTs. Specifically, we employ a multi-level global self-attention scheme with the consideration of the spherical feature distribution, enhancing the comprehensive understanding of the scene. Our experimental results demonstrate that our approach achieves state-of-the-art performance across multiple popular 360° monocular datasets. The code and models will be released.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/748bfcd3-7934-43eb-ba8d-17ebcf2798b7)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.18745) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Correctable Landmark Discovery via Large Models for Vision-Language Navigation
Authors: Bingqian Lin, Yunshuang Nie, Ziming Wei, Yi Zhu, Hang Xu, Shikui Ma, Jianzhuang Liu, Xiaodan Liang
<details span>
<summary><b>Abstract</b></summary>
Vision-Language Navigation (VLN) requires the agent to follow language instructions to reach a target position. A key factor for successful navigation is to align the landmarks implied in the instruction with diverse visual observations. However, previous VLN agents fail to perform accurate modality alignment especially in unexplored scenes, since they learn from limited navigation data and lack sufficient open-world alignment knowledge. In this work, we propose a new VLN paradigm, called COrrectable LaNdmark DiScOvery via Large ModEls (CONSOLE). In CONSOLE, we cast VLN as an open-world sequential landmark discovery problem, by introducing a novel correctable landmark discovery scheme based on two large models ChatGPT and CLIP. Specifically, we use ChatGPT to provide rich open-world landmark cooccurrence commonsense, and conduct CLIP-driven landmark discovery based on these commonsense priors. To mitigate the noise in the priors due to the lack of visual constraints, we introduce a learnable cooccurrence scoring module, which corrects the importance of each cooccurrence according to actual observations for accurate landmark discovery. We further design an observation enhancement strategy for an elegant combination of our framework with different VLN agents, where we utilize the corrected landmark features to obtain enhanced observation features for action decision. Extensive experimental results on multiple popular VLN benchmarks (R2R, REVERIE, R4R, RxR) show the significant superiority of CONSOLE over strong baselines. Especially, our CONSOLE establishes the new state-of-the-art results on R2R and R4R in unseen scenarios.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0dcaf652-c553-4016-bc82-94b501c23338)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.18721) | [⌨️ Code](https://github.com/expectorlin/CONSOLE) | [🌐 Project Page]

#### <summary>NeRF On-the-go: Exploiting Uncertainty for Distractor-free NeRFs in the Wild
Authors: Weining Ren, Zihan Zhu, Boyang Sun, Jiaqi Chen, Marc Pollefeys, Songyou Peng
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRFs) have shown remarkable success in synthesizing photorealistic views from multi-view images of static scenes, but face challenges in dynamic, real-world environments with distractors like moving objects, shadows, and lighting changes. Existing methods manage controlled environments and low occlusion ratios but fall short in render quality, especially under high occlusion scenarios. In this paper, we introduce NeRF On-the-go, a simple yet effective approach that enables the robust synthesis of novel views in complex, in-the-wild scenes from only casually captured image sequences. Delving into uncertainty, our method not only efficiently eliminates distractors, even when they are predominant in captures, but also achieves a notably faster convergence speed. Through comprehensive experiments on various scenes, our method demonstrates a significant improvement over state-of-the-art techniques. This advancement opens new avenues for NeRF in diverse and dynamic real-world applications.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e440ed80-e7a5-4aaa-80e5-1e693d928258)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.18715) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Towards Point Cloud Compression for Machine Perception: A Simple and Strong Baseline by Learning the Octree Depth Level Predictor
Authors: Lei Liu, Zhihao Hu, Zhenghao Chen
<details span>
<summary><b>Abstract</b></summary>
Point cloud compression has garnered significant interest in computer vision. However, existing algorithms primarily cater to human vision, while most point cloud data is utilized for machine vision tasks. To address this, we propose a point cloud compression framework that simultaneously handles both human and machine vision tasks. Our framework learns a scalable bit-stream, using only subsets for different machine vision tasks to save bit-rate, while employing the entire bit-stream for human vision tasks. Building on mainstream octree-based frameworks like VoxelContext-Net, OctAttention, and G-PCC, we introduce a new octree depth-level predictor. This predictor adaptively determines the optimal depth level for each octree constructed from a point cloud, controlling the bit-rate for machine vision tasks. For simpler tasks (\textit{e.g.}, classification) or objects/scenarios, we use fewer depth levels with fewer bits, saving bit-rate. Conversely, for more complex tasks (\textit{e.g}., segmentation) or objects/scenarios, we use deeper depth levels with more bits to enhance performance. Experimental results on various datasets (\textit{e.g}., ModelNet10, ModelNet40, ShapeNet, ScanNet, and KITTI) show that our point cloud compression approach improves performance for machine vision tasks without compromising human vision quality.


![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/6de1cbd5-08fa-4082-804e-226f0102f5fe)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.00791) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Details Enhancement in Unsigned Distance Field Learning for High-fidelity 3D Surface Reconstruction
Authors: Cheng Xu, Fei Hou, Wencheng Wang, Hong Qin, Zhebin Zhang, Ying He
<details span>
<summary><b>Abstract</b></summary>
While Signed Distance Fields (SDF) are well-established for modeling watertight surfaces, Unsigned Distance Fields (UDF) broaden the scope to include open surfaces and models with complex inner structures. Despite their flexibility, UDFs encounter significant challenges in high-fidelity 3D reconstruction, such as non-differentiability at the zero level set, difficulty in achieving the exact zero value, numerous local minima, vanishing gradients, and oscillating gradient directions near the zero level set. To address these challenges, we propose Details Enhanced UDF (DEUDF) learning that integrates normal alignment and the SIREN network for capturing fine geometric details, adaptively weighted Eikonal constraints to address vanishing gradients near the target surface, unconditioned MLP-based UDF representation to relax non-negativity constraints, and a UDF-tailored method for extracting iso-surface with non-constant iso-values. These strategies collectively stabilize the learning process from unoriented point clouds and enhance the accuracy of UDFs. Our computational results demonstrate that DEUDF outperforms existing UDF learning methods in both accuracy and the quality of reconstructed surfaces.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/46011ab9-662c-4b0a-8b5e-0b81652ef34e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.00346) | [⌨️ Code] | [🌐 Project Page]


#### <summary>GenS: Generalizable Neural Surface Reconstruction from Multi-View Images
Authors: Rui Peng, Xiaodong Gu, Luyang Tang, Shihe Shen, Fanqi Yu, Ronggang Wang
<details span>
<summary><b>Abstract</b></summary>
Combining the signed distance function (SDF) and differentiable volume rendering has emerged as a powerful paradigm for surface reconstruction from multi-view images without 3D supervision. However, current methods are impeded by requiring long-time per-scene optimizations and cannot generalize to new scenes. In this paper, we present GenS, an end-to-end generalizable neural surface reconstruction model. Unlike coordinate-based methods that train a separate network for each scene, we construct a generalized multi-scale volume to directly encode all scenes. Compared with existing solutions, our representation is more powerful, which can recover high-frequency details while maintaining global smoothness. Meanwhile, we introduce a multi-scale feature-metric consistency to impose the multi-view consistency in a more discriminative multi-scale feature space, which is robust to the failures of the photometric consistency. And the learnable feature can be self-enhanced to continuously improve the matching accuracy and mitigate aggregation ambiguity. Furthermore, we design a view contrast loss to force the model to be robust to those regions covered by few viewpoints through distilling the geometric prior from dense input to sparse input. Extensive experiments on popular benchmarks show that our model can generalize well to new scenes and outperform existing state-of-the-art methods even those employing ground-truth depth supervision.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/6bd2d4a8-d5e7-4c2e-9b06-cc75bbe10f62)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02495) | [⌨️ Code](https://github.com/prstrive/GenS) | [🌐 Project Page]

#### <summary>CoFie: Learning Compact Neural Surface Representations with Coordinate Fields
Authors: Hanwen Jiang, Haitao Yang, Georgios Pavlakos, Qixing Huang
<details span>
<summary><b>Abstract</b></summary>
This paper introduces CoFie, a novel local geometry-aware neural surface representation. CoFie is motivated by the theoretical analysis of local SDFs with quadratic approximation. We find that local shapes are highly compressive in an aligned coordinate frame defined by the normal and tangent directions of local shapes. Accordingly, we introduce Coordinate Field, which is a composition of coordinate frames of all local shapes. The Coordinate Field is optimizable and is used to transform the local shapes from the world coordinate frame to the aligned shape coordinate frame. It largely reduces the complexity of local shapes and benefits the learning of MLP-based implicit representations. Moreover, we introduce quadratic layers into the MLP to enhance expressiveness concerning local shape geometry. CoFie is a generalizable surface representation. It is trained on a curated set of 3D shapes and works on novel shape instances during testing. When using the same amount of parameters with prior works, CoFie reduces the shape error by 48% and 56% on novel instances of both training and unseen shape categories. Moreover, CoFie demonstrates comparable performance to prior works when using only 70% fewer parameters.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/91adbfc3-64ff-4d27-854c-807604d7830c)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.03417) | [⌨️ Code](https://github.com/hwjiang1510/CoFie) | [🌐 Project Page](https://hwjiang1510.github.io/CoFie/)


#### <summary>How Far Can We Compress Instant-NGP-Based NeRF?

>  *read together with HAC*

Authors: Yihang Chen, Qianyi Wu, Mehrtash Harandi, Jianfei Cai
<details span>
<summary><b>Abstract</b></summary>
In recent years, Neural Radiance Field (NeRF) has demonstrated remarkable capabilities in representing 3D scenes. To expedite the rendering process, learnable explicit representations have been introduced for combination with implicit NeRF representation, which however results in a large storage space requirement. In this paper, we introduce the Context-based NeRF Compression (CNC) framework, which leverages highly efficient context models to provide a storage-friendly NeRF representation. Specifically, we excavate both level-wise and dimension-wise context dependencies to enable probability prediction for information entropy reduction. Additionally, we exploit hash collision and occupancy grids as strong prior knowledge for better context modeling. To the best of our knowledge, we are the first to construct and exploit context models for NeRF compression. We achieve a size reduction of 100× and 70× with improved fidelity against the baseline Instant-NGP on Synthesic-NeRF and Tanks and Temples datasets, respectively. Additionally, we attain 86.7\% and 82.3\% storage size reduction against the SOTA NeRF compression method BiRF.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/6b0036b5-3dd7-4b3c-bb80-80585710c393)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04101) | [⌨️ Code](https://github.com/YihangChen-ee/CNC) | [🌐 Project Page](https://yihangchen-ee.github.io/project_cnc/)


#### <summary>Matching Anything by Segmenting Anything

Authors: Siyuan Li, Lei Ke, Martin Danelljan, Luigi Piccinelli, Mattia Segu, Luc Van Gool, Fisher Yu
<details span>
<summary><b>Abstract</b></summary>
The robust association of the same objects across video frames in complex scenes is crucial for many applications, especially Multiple Object Tracking (MOT). Current methods predominantly rely on labeled domain-specific video datasets, which limits the cross-domain generalization of learned similarity embeddings. We propose MASA, a novel method for robust instance association learning, capable of matching any objects within videos across diverse domains without tracking labels. Leveraging the rich object segmentation from the Segment Anything Model (SAM), MASA learns instance-level correspondence through exhaustive data transformations. We treat the SAM outputs as dense object region proposals and learn to match those regions from a vast image collection. We further design a universal MASA adapter which can work in tandem with foundational segmentation or detection models and enable them to track any detected objects. Those combinations present strong zero-shot tracking ability in complex domains. Extensive tests on multiple challenging MOT and MOTS benchmarks indicate that the proposed method, using only unlabeled static images, achieves even better performance than state-of-the-art methods trained with fully annotated in-domain video sequences, in zero-shot association.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3c149bc6-6c3a-4c92-b505-bcfaaf9dc248)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04221) | [⌨️ Code](https://github.com/siyuanliii/masa) | [🌐 Project Page](https://matchinganything.github.io/)

#### <summary>Bilateral Guided Radiance Field Processing
Authors: Yuehao Wang, Chaoyi Wang, Bingchen Gong, Tianfan Xue
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRF) achieves unprecedented performance in synthesizing novel view synthesis, utilizing multi-view consistency. When capturing multiple inputs, image signal processing (ISP) in modern cameras will independently enhance them, including exposure adjustment, color correction, local tone mapping, etc. While these processings greatly improve image quality, they often break the multi-view consistency assumption, leading to "floaters" in the reconstructed radiance fields. To address this concern without compromising visual aesthetics, we aim to first disentangle the enhancement by ISP at the NeRF training stage and re-apply user-desired enhancements to the reconstructed radiance fields at the finishing stage. Furthermore, to make the re-applied enhancements consistent between novel views, we need to perform imaging signal processing in 3D space (i.e. "3D ISP"). For this goal, we adopt the bilateral grid, a locally-affine model, as a generalized representation of ISP processing. Specifically, we optimize per-view 3D bilateral grids with radiance fields to approximate the effects of camera pipelines for each input view. To achieve user-adjustable 3D finishing, we propose to learn a low-rank 4D bilateral grid from a given single view edit, lifting photo enhancements to the whole 3D scene. We demonstrate our approach can boost the visual quality of novel view synthesis by effectively removing floaters and performing enhancements from user retouching.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0c18cabc-7d81-4e5f-8e6c-a87abbef0573)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.00448) | [⌨️ Code](https://github.com/yuehaowang/bilarf) | [🌐 Project Page](https://bilarfpro.github.io/)

#### <summary>3DRealCar: An In-the-wild RGB-D Car Dataset with 360-degree Views
Authors: Xiaobiao Du, Haiyang Sun, Shuyun Wang, Zhuojie Wu, Hongwei Sheng, Jiaying Ying, Ming Lu, Tianqing Zhu, Kun Zhan, Xin Yu
<details span>
<summary><b>Abstract</b></summary>
3D cars are commonly used in self-driving systems, virtual/augmented reality, and games. However, existing 3D car datasets are either synthetic or low-quality, presenting a significant gap toward the high-quality real-world 3D car datasets and limiting their applications in practical scenarios. In this paper, we propose the first large-scale 3D real car dataset, termed 3DRealCar, offering three distinctive features. (1) \textbf{High-Volume}: 2,500 cars are meticulously scanned by 3D scanners, obtaining car images and point clouds with real-world dimensions; (2) \textbf{High-Quality}: Each car is captured in an average of 200 dense, high-resolution 360-degree RGB-D views, enabling high-fidelity 3D reconstruction; (3) \textbf{High-Diversity}: The dataset contains various cars from over 100 brands, collected under three distinct lighting conditions, including reflective, standard, and dark. Additionally, we offer detailed car parsing maps for each instance to promote research in car parsing tasks. Moreover, we remove background point clouds and standardize the car orientation to a unified axis for the reconstruction only on cars without background and controllable rendering. We benchmark 3D reconstruction results with state-of-the-art methods across each lighting condition in 3DRealCar. Extensive experiments demonstrate that the standard lighting condition part of 3DRealCar can be used to produce a large number of high-quality 3D cars, improving various 2D and 3D tasks related to cars. Notably, our dataset brings insight into the fact that recent 3D reconstruction methods face challenges in reconstructing high-quality 3D cars under reflective and dark lighting conditions.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ef047611-37aa-46bd-a467-fe3e8fb00e27)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04875) | [⌨️ Code] | [🌐 Project Page](https://xiaobiaodu.github.io/3drealcar/)


#### <summary>Normal-guided Detail-Preserving Neural Implicit Functions for High-Fidelity 3D Surface Reconstruction
Authors: Aarya Patel, Hamid Laga, Ojaswa Sharma
<details span>
<summary><b>Abstract</b></summary>
Neural implicit representations have emerged as a powerful paradigm for 3D reconstruction. However, despite their success, existing methods fail to capture fine geometric details and thin structures, especially in scenarios where only sparse RGB views of the objects of interest are available. We hypothesize that current methods for learning neural implicit representations from RGB or RGBD images produce 3D surfaces with missing parts and details because they only rely on 0-order differential properties, i.e. the 3D surface points and their projections, as supervisory signals. Such properties, however, do not capture the local 3D geometry around the points and also ignore the interactions between points. This paper demonstrates that training neural representations with first-order differential properties, i.e. surface normals, leads to highly accurate 3D surface reconstruction even in situations where only as few as two RGB (front and back) images are available. Given multiview RGB images of an object of interest, we first compute the approximate surface normals in the image space using the gradient of the depth maps produced using an off-the-shelf monocular depth estimator such as Depth Anything model. An implicit surface regressor is then trained using a loss function that enforces the first-order differential properties of the regressed surface to match those estimated from Depth Anything. Our extensive experiments on a wide range of real and synthetic datasets show that the proposed method achieves an unprecedented level of reconstruction accuracy even when using as few as two RGB views. The detailed ablation study also demonstrates that normal-based supervision plays a key role in this significant improvement in performance, enabling the 3D reconstruction of intricate geometric details and thin structures that were previously challenging to capture.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3822b40d-dde8-444f-ac10-e7756ad2e233)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04861) | [⌨️ Code](https://github.com/sn-nir/sn-nir) | [🌐 Project Page](https://sn-nir.github.io/)

#### <summary>1st Place Solution for MOSE Track in CVPR 2024 PVUW Workshop: Complex Video Object Segmentation
Authors: Deshui Miao, Xin Li, Zhenyu He, Yaowei Wang, Ming-Hsuan Yang
<details span>
<summary><b>Abstract</b></summary>
Tracking and segmenting multiple objects in complex scenes has always been a challenge in the field of video object segmentation, especially in scenarios where objects are occluded and split into parts. In such cases, the definition of objects becomes very ambiguous. The motivation behind the MOSE dataset is how to clearly recognize and distinguish objects in complex scenes. In this challenge, we propose a semantic embedding video object segmentation model and use the salient features of objects as query representations. The semantic understanding helps the model to recognize parts of the objects and the salient feature captures the more discriminative features of the objects. Trained on a large-scale video object segmentation dataset, our model achieves first place (\textbf{84.45\%}) in the test set of PVUW Challenge 2024: Complex Video Object Segmentation Track.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/872d3b14-2e2a-415c-9de9-7d507c4d58b2)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04600) | [⌨️ Code] | [🌐 Project Page]


#### <summary>InstructNav: Zero-shot System for Generic Instruction Navigation in Unexplored Environment
Authors: Yuxing Long, Wenzhe Cai, Hongcheng Wang, Guanqi Zhan, Hao Dong
<details span>
<summary><b>Abstract</b></summary>
Enabling robots to navigate following diverse language instructions in unexplored environments is an attractive goal for human-robot interaction. However, this goal is challenging because different navigation tasks require different strategies. The scarcity of instruction navigation data hinders training an instruction navigation model with varied strategies. Therefore, previous methods are all constrained to one specific type of navigation instruction. In this work, we propose InstructNav, a generic instruction navigation system. InstructNav makes the first endeavor to handle various instruction navigation tasks without any navigation training or pre-built maps. To reach this goal, we introduce Dynamic Chain-of-Navigation (DCoN) to unify the planning process for different types of navigation instructions. Furthermore, we propose Multi-sourced Value Maps to model key elements in instruction navigation so that linguistic DCoN planning can be converted into robot actionable trajectories. With InstructNav, we complete the R2R-CE task in a zero-shot way for the first time and outperform many task-training methods. Besides, InstructNav also surpasses the previous SOTA method by 10.48% on the zero-shot Habitat ObjNav and by 86.34% on demand-driven navigation DDN. Real robot experiments on diverse indoor scenes further demonstrate our method's robustness in coping with the environment and instruction variations.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/1eecab15-c927-4042-8d10-126a54351cc8)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04882) | [⌨️ Code] | [🌐 Project Page](https://sites.google.com/view/instructnavA)



#### <summary>Neural Surface Reconstruction from Sparse Views Using Epipolar Geometry
Authors: Kaichen Zhou
<details span>
<summary><b>Abstract</b></summary>
This paper addresses the challenge of reconstructing surfaces from sparse view inputs, where ambiguity and occlusions due to missing information pose significant hurdles. We present a novel approach, named EpiS, that incorporates Epipolar information into the reconstruction process. Existing methods in sparse-view neural surface learning have mainly focused on mean and variance considerations using cost volumes for feature extraction. In contrast, our method aggregates coarse information from the cost volume into Epipolar features extracted from multiple source views, enabling the generation of fine-grained Signal Distance Function (SDF)-aware features. Additionally, we employ an attention mechanism along the line dimension to facilitate feature fusion based on the SDF feature. Furthermore, to address the information gaps in sparse conditions, we integrate depth information from monocular depth estimation using global and local regularization techniques. The global regularization utilizes a triplet loss function, while the local regularization employs a derivative loss function. Extensive experiments demonstrate that our approach outperforms state-of-the-art methods, especially in cases with sparse and generalizable conditions.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/26ebd05c-de45-4012-82f3-8046009669f2)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04301) | [⌨️ Code] | [🌐 Project Page]


#### <summary>VoxNeuS: Enhancing Voxel-Based Neural Surface Reconstruction via Gradient Interpolation
Authors: Sidun Liu, Peng Qiao, Zongxin Ye, Wenyu Li, Yong Dou
<details span>
<summary><b>Abstract</b></summary>
Neural Surface Reconstruction learns a Signed Distance Field~(SDF) to reconstruct the 3D model from multi-view images. Previous works adopt voxel-based explicit representation to improve efficiency. However, they ignored the gradient instability of interpolation in the voxel grid, leading to degradation on convergence and smoothness. Besides, previous works entangled the optimization of geometry and radiance, which leads to the deformation of geometry to explain radiance, causing artifacts when reconstructing textured planes.
In this work, we reveal that the instability of gradient comes from its discontinuity during trilinear interpolation, and propose to use the interpolated gradient instead of the original analytical gradient to eliminate the discontinuity. Based on gradient interpolation, we propose VoxNeuS, a lightweight surface reconstruction method for computational and memory efficient neural surface reconstruction. Thanks to the explicit representation, the gradient of regularization terms, i.e. Eikonal and curvature loss, are directly solved, avoiding computation and memory-access overhead.
Further, VoxNeuS adopts a geometry-radiance disentangled architecture to handle the geometry deformation from radiance optimization.
The experimental results show that VoxNeuS achieves better reconstruction quality than previous works. The entire training process takes 15 minutes and less than 3 GB of memory on a single 2080ti GPU.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/b937f571-8da2-46e2-81a8-0bacde54ad5b)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07170) | [⌨️ Code] | [🌐 Project Page]





#### <summary>SPIN: Spacecraft Imagery for Navigation
Authors: Javier Montalvo, Juan Ignacio Bravo Pérez-Villar, Álvaro García-Martín, Pablo Carballeira, Jesús Besc'os
<details span>
<summary><b>Abstract</b></summary>
Data acquired in space operational conditions is scarce due to the costs and complexity of space operations. This poses a challenge to learning-based visual-based navigation algorithms employed in autonomous spacecraft navigation. Existing datasets, which largely depend on computer-simulated data, have partially filled this gap. However, the image generation tools they use are proprietary, which limits the evaluation of methods to unseen scenarios. Furthermore, these datasets provide limited ground-truth data, primarily focusing on the spacecraft's translation and rotation relative to the camera. To address these limitations, we present SPIN (SPacecraft Imagery for Navigation), an open-source realistic spacecraft image generation tool for relative navigation between two spacecrafts. SPIN provides a wide variety of ground-truth data and allows researchers to employ custom 3D models of satellites, define specific camera-relative poses, and adjust various settings such as camera parameters and environmental illumination conditions. For the task of spacecraft pose estimation, we compare the results of training with a SPIN-generated dataset against existing synthetic datasets. We show a %50 average error reduction in common testbed data (that simulates realistic space conditions).

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/03a0c698-ffbb-4b31-8f3c-53ca727dfa4e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07500) | [⌨️ Code](https://github.com/vpulab/SPIN) | [🌐 Project Page]


#### <summary>PanoSSC: Exploring Monocular Panoptic 3D Scene Reconstruction for Autonomous Driving
Authors: Yining Shi, Jiusi Li, Kun Jiang, Ke Wang, Yunlong Wang, Mengmeng Yang, Diange Yang
<details span>
<summary><b>Abstract</b></summary>
Vision-centric occupancy networks, which represent the surrounding environment with uniform voxels with semantics, have become a new trend for safe driving of camera-only autonomous driving perception systems, as they are able to detect obstacles regardless of their shape and occlusion. Modern occupancy networks mainly focus on reconstructing visible voxels from object surfaces with voxel-wise semantic prediction. Usually, they suffer from inconsistent predictions of one object and mixed predictions for adjacent objects. These confusions may harm the safety of downstream planning modules. To this end, we investigate panoptic segmentation on 3D voxel scenarios and propose an instance-aware occupancy network, PanoSSC. We predict foreground objects and backgrounds separately and merge both in post-processing. For foreground instance grouping, we propose a novel 3D instance mask decoder that can efficiently extract individual objects. we unify geometric reconstruction, 3D semantic segmentation, and 3D instance segmentation into PanoSSC framework and propose new metrics for evaluating panoptic voxels. Extensive experiments show that our method achieves competitive results on SemanticKITTI semantic scene completion benchmark.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/cd729eca-3a6c-4509-ac70-7e8e6c543df2)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07037) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Active Scout: Multi-Target Tracking Using Neural Radiance Fields in Dense Urban Environments
Authors: 
<details span>
<summary><b>Abstract</b></summary>
We study pursuit-evasion games in highly occluded urban environments, e.g. tall buildings in a city, where a scout (quadrotor) tracks multiple dynamic targets on the ground. We show that we can build a neural radiance field (NeRF) representation of the city -- online -- using RGB and depth images from different vantage points. This representation is used to calculate the information gain to both explore unknown parts of the city and track the targets -- thereby giving a completely first-principles approach to actively tracking dynamic targets. We demonstrate, using a custom-built simulator using Open Street Maps data of Philadelphia and New York City, that we can explore and locate 20 stationary targets within 300 steps. This is slower than a greedy baseline which which does not use active perception. But for dynamic targets that actively hide behind occlusions, we show that our approach maintains, at worst, a tracking error of 200m; the greedy baseline can have a tracking error as large as 600m. We observe a number of interesting properties in the scout's policies, e.g., it switches its attention to track a different target periodically, as the quality of the NeRF representation improves over time, the scout also becomes better in terms of target tracking.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d9f60d6e-0c71-40d4-be42-fb64e91063de)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07431) | [⌨️ Code] | [🌐 Project Page]

#### <summary>The Unreasonable Effectiveness of Pre-Trained Features for Camera Pose Refinement
Authors: Gabriele Trivigno, Carlo Masone, Barbara Caputo, Torsten Sattler
<details span>
<summary><b>Abstract</b></summary>
Pose refinement is an interesting and practically relevant research direction. Pose refinement can be used to (1) obtain a more accurate pose estimate from an initial prior (e.g., from retrieval), (2) as pre-processing, i.e., to provide a better starting point to a more expensive pose estimator, (3) as post-processing of a more accurate localizer. Existing approaches focus on learning features / scene representations for the pose refinement task. This involves training an implicit scene representation or learning features while optimizing a camera pose-based loss. A natural question is whether training specific features / representations is truly necessary or whether similar results can be already achieved with more generic features. In this work, we present a simple approach that combines pre-trained features with a particle filter and a renderable representation of the scene. Despite its simplicity, it achieves state-of-the-art results, demonstrating that one can easily build a pose refiner without the need for specific training.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0e0d871a-da39-4f4a-8bdf-4a1ccfaa3fb7)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2404.10438) | [⌨️ Code](https://github.com/ga1i13o/mcloc_poseref) | [🌐 Project Page]


#### <summary>Self-supervised Learning of Neural Implicit Feature Fields for Camera Pose Refinement
Authors: Maxime Pietrantoni, Gabriela Csurka, Martin Humenberger, Torsten Sattler
<details span>
<summary><b>Abstract</b></summary>
Visual localization techniques rely upon some underlying scene representation to localize against. These representations can be explicit such as 3D SFM map or implicit, such as a neural network that learns to encode the scene. The former requires sparse feature extractors and matchers to build the scene representation. The latter might lack geometric grounding not capturing the 3D structure of the scene well enough. This paper proposes to jointly learn the scene representation along with a 3D dense feature field and a 2D feature extractor whose outputs are embedded in the same metric space. Through a contrastive framework we align this volumetric field with the image-based extractor and regularize the latter with a ranking loss from learned surface information. We learn the underlying geometry of the scene with an implicit field through volumetric rendering and design our feature field to leverage intermediate geometric information encoded in the implicit field. The resulting features are discriminative and robust to viewpoint change while maintaining rich encoded information. Visual localization is then achieved by aligning the image-based features and the rendered volumetric features. We show the effectiveness of our approach on real-world scenes, demonstrating that our approach outperforms prior and concurrent work on leveraging implicit scene representations for localization.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/84ea350d-d78b-4009-9399-9e96346a5e8f)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.08463) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Category-level Neural Field for Reconstruction of Partially Observed Objects in Indoor Environment
Authors: Taekbeom Lee, Youngseok Jang, H. Jin Kim
<details span>
<summary><b>Abstract</b></summary>
Neural implicit representation has attracted attention in 3D reconstruction through various success cases. For further applications such as scene understanding or editing, several works have shown progress towards object compositional reconstruction. Despite their superior performance in observed regions, their performance is still limited in reconstructing objects that are partially observed. To better treat this problem, we introduce category-level neural fields that learn meaningful common 3D information among objects belonging to the same category present in the scene. Our key idea is to subcategorize objects based on their observed shape for better training of the category-level model. Then we take advantage of the neural field to conduct the challenging task of registering partially observed objects by selecting and aligning against representative objects selected by ray-based uncertainty. Experiments on both simulation and real-world datasets demonstrate that our method improves the reconstruction of unobserved parts for several categories.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0b659197-b8c0-41a8-b310-9f20f8148f18)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.08176) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Spatial Annealing Smoothing for Efficient Few-shot Neural Rendering
Authors: Yuru Xiao, Xianming Liu, Deming Zhai, Kui Jiang, Junjun Jiang, Xiangyang Ji
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRF) with hybrid representations have shown impressive capabilities in reconstructing scenes for view synthesis, delivering high efficiency. Nonetheless, their performance significantly drops with sparse view inputs, due to the issue of overfitting. While various regularization strategies have been devised to address these challenges, they often depend on inefficient assumptions or are not compatible with hybrid models. There is a clear need for a method that maintains efficiency and improves resilience to sparse views within a hybrid framework. In this paper, we introduce an accurate and efficient few-shot neural rendering method named Spatial Annealing smoothing regularized NeRF (SANeRF), which is specifically designed for a pre-filtering-driven hybrid representation architecture. We implement an exponential reduction of the sample space size from an initially large value. This methodology is crucial for stabilizing the early stages of the training phase and significantly contributes to the enhancement of the subsequent process of detail refinement. Our extensive experiments reveal that, by adding merely one line of code, SANeRF delivers superior rendering quality and much faster reconstruction speed compared to current few-shot NeRF methods. Notably, SANeRF outperforms FreeNeRF by 0.3 dB in PSNR on the Blender dataset, while achieving 700x faster reconstruction speed.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f78d7a98-4b10-479f-8a46-9781bd7ba3c2)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07828) | [⌨️ Code](https://github.com/pulangk97/SANeRF) | [🌐 Project Page]

#### <summary>From Variance to Veracity: Unbundling and Mitigating Gradient Variance in Differentiable Bundle Adjustment Layers
Authors: Swaminathan Gurumurthy, Karnik Ram, Bingqing Chen, Zachary Manchester, Zico Kolter
<details span>
<summary><b>Abstract</b></summary>
Various pose estimation and tracking problems in robotics can be decomposed into a correspondence estimation problem (often computed using a deep network) followed by a weighted least squares optimization problem to solve for the poses. Recent work has shown that coupling the two problems by iteratively refining one conditioned on the other's output yields SOTA results across domains. However, training these models has proved challenging, requiring a litany of tricks to stabilize and speed up training. In this work, we take the visual odometry problem as an example and identify three plausible causes: (1) flow loss interference, (2) linearization errors in the bundle adjustment (BA) layer, and (3) dependence of weight gradients on the BA residual. We show how these issues result in noisy and higher variance gradients, potentially leading to a slow down in training and instabilities. We then propose a simple, yet effective solution to reduce the gradient variance by using the weights predicted by the network in the inner optimization loop to weight the correspondence objective in the training problem. This helps the training objective `focus' on the more important points, thereby reducing the variance and mitigating the influence of outliers. We show that the resulting method leads to faster training and can be more flexibly trained in varying training setups without sacrificing performance. In particular we show 2--2.5× training speedups over a baseline visual odometry model we modify.


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.07785) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Depth Anything V2
Authors: Lihe Yang, Bingyi Kang, Zilong Huang, Zhen Zhao, Xiaogang Xu, Jiashi Feng, Hengshuang Zhao
<details span>
<summary><b>Abstract</b></summary>
This work presents Depth Anything V2. Without pursuing fancy techniques, we aim to reveal crucial findings to pave the way towards building a powerful monocular depth estimation model. Notably, compared with V1, this version produces much finer and more robust depth predictions through three key practices: 1) replacing all labeled real images with synthetic images, 2) scaling up the capacity of our teacher model, and 3) teaching student models via the bridge of large-scale pseudo-labeled real images. Compared with the latest models built on Stable Diffusion, our models are significantly more efficient (more than 10x faster) and more accurate. We offer models of different scales (ranging from 25M to 1.3B params) to support extensive scenarios. Benefiting from their strong generalization capability, we fine-tune them with metric depth labels to obtain our metric depth models. In addition to our models, considering the limited diversity and frequent noise in current test sets, we construct a versatile evaluation benchmark with precise annotations and diverse scenes to facilitate future research.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/795809b4-b51e-4e85-be66-d33745f02cb7)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.09414) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Explore the Limits of Omni-modal Pretraining at Scale
Authors: Yiyuan Zhang, Handong Li, Jing Liu, Xiangyu Yue
<details span>
<summary><b>Abstract</b></summary>
We propose to build omni-modal intelligence, which is capable of understanding any modality and learning universal representations. In specific, we propose a scalable pretraining paradigm, named Multimodal Context (MiCo), which can scale up the numbers of modalities and amount of data, together with the model parameters, in the pretraining process. With MiCo, the pretrained models show significant emergent abilities in multimodal learning, which are evaluated on the following tasks: i) single-modality perception benchmarks of 10 different modalities, ii) 25 cross-modality understanding tasks of retrieval, question-answering, captioning, and iii) 18 multimodal large language model benchmarks. Our models establish 37 new records for state-of-the-art performance. We hope that our research could contribute to the development of omni-modal intelligence.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/93f25897-b8cb-4cc0-ac13-3038d7cdea59)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.09412) | [⌨️ Code](https://github.com/invictus717/MiCo) | [🌐 Project Page]

#### <summary>Scale-Invariant Monocular Depth Estimation via SSI Depth
Authors: S. Mahdi H. Miangoleh, Mahesh Reddy, Yağız Aksoy
<details span>
<summary><b>Abstract</b></summary>
Existing methods for scale-invariant monocular depth estimation (SI MDE) often struggle due to the complexity of the task, and limited and non-diverse datasets, hindering generalizability in real-world scenarios. This is while shift-and-scale-invariant (SSI) depth estimation, simplifying the task and enabling training with abundant stereo datasets achieves high performance. We present a novel approach that leverages SSI inputs to enhance SI depth estimation, streamlining the network's role and facilitating in-the-wild generalization for SI depth estimation while only using a synthetic dataset for training. Emphasizing the generation of high-resolution details, we introduce a novel sparse ordinal loss that substantially improves detail generation in SSI MDE, addressing critical limitations in existing approaches. Through in-the-wild qualitative examples and zero-shot evaluation we substantiate the practical utility of our approach in computational photography applications, showcasing its ability to generate highly detailed SI depth maps and achieve generalization in diverse scenarios.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/4ab2e79c-87a6-4a33-af7a-ebfe92a9035e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.09374) | [⌨️ Code] | [🌐 Project Page](https://yaksoy.github.io/sidepth/)

#### <summary>MultiPly: Reconstruction of Multiple People from Monocular Video in the Wild
Authors: Zeren Jiang, Chen Guo, Manuel Kaufmann, Tianjian Jiang, Julien Valentin, Otmar Hilliges, Jie Song
<details span>
<summary><b>Abstract</b></summary>
We present MultiPly, a novel framework to reconstruct multiple people in 3D from monocular in-the-wild videos. Reconstructing multiple individuals moving and interacting naturally from monocular in-the-wild videos poses a challenging task. Addressing it necessitates precise pixel-level disentanglement of individuals without any prior knowledge about the subjects. Moreover, it requires recovering intricate and complete 3D human shapes from short video sequences, intensifying the level of difficulty. To tackle these challenges, we first define a layered neural representation for the entire scene, composited by individual human and background models. We learn the layered neural representation from videos via our layer-wise differentiable volume rendering. This learning process is further enhanced by our hybrid instance segmentation approach which combines the self-supervised 3D segmentation and the promptable 2D segmentation module, yielding reliable instance segmentation supervision even under close human interaction. A confidence-guided optimization formulation is introduced to optimize the human poses and shape/appearance alternately. We incorporate effective objectives to refine human poses via photometric information and impose physically plausible constraints on human dynamics, leading to temporally consistent 3D reconstructions with high fidelity. The evaluation of our method shows the superiority over prior art on publicly available datasets and in-the-wild videos.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3f7e4bbc-b3dc-4316-8769-37dd1eec55d4)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.01595) | [⌨️ Code] | [🌐 Project Page](https://eth-ait.github.io/MultiPly/)

#### <summary>Flash3D: Feed-Forward Generalisable 3D Scene Reconstruction from a Single Image
Authors: Stanislaw Szymanowicz, Eldar Insafutdinov, Chuanxia Zheng, Dylan Campbell, João F. Henriques, Christian Rupprecht, Andrea Vedaldi
<details span>
<summary><b>Abstract</b></summary>
In this paper, we propose Flash3D, a method for scene reconstruction and novel view synthesis from a single image which is both very generalisable and efficient. For generalisability, we start from a "foundation" model for monocular depth estimation and extend it to a full 3D shape and appearance reconstructor. For efficiency, we base this extension on feed-forward Gaussian Splatting. Specifically, we predict a first layer of 3D Gaussians at the predicted depth, and then add additional layers of Gaussians that are offset in space, allowing the model to complete the reconstruction behind occlusions and truncations. Flash3D is very efficient, trainable on a single GPU in a day, and thus accessible to most researchers. It achieves state-of-the-art results when trained and tested on RealEstate10k. When transferred to unseen datasets like NYU it outperforms competitors by a large margin. More impressively, when transferred to KITTI, Flash3D achieves better PSNR than methods trained specifically on that dataset. In some instances, it even outperforms recent methods that use multiple views as input.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/86b28ad4-3ec3-42a3-8941-595eb9c2a891)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04343) | [⌨️ Code] | [🌐 Project Page](https://www.robots.ox.ac.uk/~vgg/research/flash3d/)

#### <summary>MeshAnything: Artist-Created Mesh Generation with Autoregressive Transformers
Authors: Yiwen Chen, Tong He, Di Huang, Weicai Ye, Sijin Chen, Jiaxiang Tang, Xin Chen, Zhongang Cai, Lei Yang, Gang Yu, Guosheng Lin, Chi Zhang
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D assets created via reconstruction and generation have matched the quality of manually crafted assets, highlighting their potential for replacement. However, this potential is largely unrealized because these assets always need to be converted to meshes for 3D industry applications, and the meshes produced by current mesh extraction methods are significantly inferior to Artist-Created Meshes (AMs), i.e., meshes created by human artists. Specifically, current mesh extraction methods rely on dense faces and ignore geometric features, leading to inefficiencies, complicated post-processing, and lower representation quality. To address these issues, we introduce MeshAnything, a model that treats mesh extraction as a generation problem, producing AMs aligned with specified shapes. By converting 3D assets in any 3D representation into AMs, MeshAnything can be integrated with various 3D asset production methods, thereby enhancing their application across the 3D industry. The architecture of MeshAnything comprises a VQ-VAE and a shape-conditioned decoder-only transformer. We first learn a mesh vocabulary using the VQ-VAE, then train the shape-conditioned decoder-only transformer on this vocabulary for shape-conditioned autoregressive mesh generation. Our extensive experiments show that our method generates AMs with hundreds of times fewer faces, significantly improving storage, rendering, and simulation efficiencies, while achieving precision comparable to previous methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/874f4b8c-2cbd-43d4-8412-477d832a33a7)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.10163) | [⌨️ Code](https://github.com/buaacyw/MeshAnything) | [🌐 Project Page](https://buaacyw.github.io/mesh-anything/)

#### <summary>RaNeuS: Ray-adaptive Neural Surface Reconstruction
Authors: Yida Wang, David Joseph Tan, Nassir Navab, Federico Tombari
<details span>
<summary><b>Abstract</b></summary>
Our objective is to leverage a differentiable radiance field \eg NeRF to reconstruct detailed 3D surfaces in addition to producing the standard novel view renderings. There have been related methods that perform such tasks, usually by utilizing a signed distance field (SDF). However, the state-of-the-art approaches still fail to correctly reconstruct the small-scale details, such as the leaves, ropes, and textile surfaces. Considering that different methods formulate and optimize the projection from SDF to radiance field with a globally constant Eikonal regularization, we improve with a ray-wise weighting factor to prioritize the rendering and zero-crossing surface fitting on top of establishing a perfect SDF. We propose to adaptively adjust the regularization on the signed distance field so that unsatisfying rendering rays won't enforce strong Eikonal regularization which is ineffective, and allow the gradients from regions with well-learned radiance to effectively back-propagated to the SDF. Consequently, balancing the two objectives in order to generate accurate and detailed surfaces. Additionally, concerning whether there is a geometric bias between the zero-crossing surface in SDF and rendering points in the radiance field, the projection becomes adjustable as well depending on different 3D locations during optimization. Our proposed \textit{RaNeuS} are extensively evaluated on both synthetic and real datasets, achieving state-of-the-art results on both novel view synthesis and geometric reconstruction.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e2c00fd1-7076-4fb3-9ed3-b5cbd09140b4)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.09801) | [⌨️ Code](https://github.com/wangyida/ra-neus) | [🌐 Project Page]

#### <summary>Matching Query Image Against Selected NeRF Feature for Efficient and Scalable Localization
Authors: Huaiji Zhou, Bing Wang, Changhao Chen
<details span>
<summary><b>Abstract</b></summary>
Neural implicit representations such as NeRF have revolutionized 3D scene representation with photo-realistic quality. However, existing methods for visual localization within NeRF representations suffer from inefficiency and scalability issues, particularly in large-scale environments. This work proposes MatLoc-NeRF, a novel matching-based localization framework using selected NeRF features. It addresses efficiency by employing a learnable feature selection mechanism that identifies informative NeRF features for matching with query images. This eliminates the need for all NeRF features or additional descriptors, leading to faster and more accurate pose estimation. To tackle large-scale scenes, MatLoc-NeRF utilizes a pose-aware scene partitioning strategy. It ensures that only the most relevant NeRF sub-block generates key features for a specific pose. Additionally, scene segmentation and a place predictor provide fast coarse initial pose estimation. Evaluations on public large-scale datasets demonstrate that MatLoc-NeRF achieves superior efficiency and accuracy compared to existing NeRF-based localization methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/77ff1049-5e9f-47cc-8606-dedff9fa180e)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.11766) | [⌨️ Code] | [🌐 Project Page]


#### <summary>fNeRF: High Quality Radiance Fields from Practical Cameras
Authors: Yi Hua, Christoph Lassner, Carsten Stoll, Iain Matthews
<details span>
<summary><b>Abstract</b></summary>
In recent years, the development of Neural Radiance Fields has enabled a previously unseen level of photo-realistic 3D reconstruction of scenes and objects from multi-view camera data. However, previous methods use an oversimplified pinhole camera model resulting in defocus blur being `baked' into the reconstructed radiance field. We propose a modification to the ray casting that leverages the optics of lenses to enhance scene reconstruction in the presence of defocus blur. This allows us to improve the quality of radiance field reconstructions from the measurements of a practical camera with finite aperture. We show that the proposed model matches the defocus blur behavior of practical cameras more closely than pinhole models and other approximations of defocus blur models, particularly in the presence of partial occlusions. This allows us to achieve sharper reconstructions, improving the PSNR on validation of all-in-focus images, on both synthetic and real datasets, by up to 3 dB.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/a92f2afe-f2e1-4a75-ad9c-0babea8dd8ca)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.10633) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Neural Geometry Fields for Meshes
Authors: Venkataram Sivaram, Ravi Ramamoorthi, Tzu-Mao Li
<details span>
<summary><b>Abstract</b></summary>
Recent work on using neural fields to represent surfaces has re- sulted in significant improvements in representational capability and computational efficiency. However, to our knowledge, most existing work has focused on implicit representations such as signed distance fields or volumes, and little work has explored their appli- cation to discrete surface geometry, i.e., 3D meshes, limiting the applicability of neural surface representations.

We present Neural Geometry Fields, a neural representation for discrete surface geometry represented by triangle meshes. Our idea is to represent the target surface using a coarse set of quadrangular patches, and add surface details using coordinate neural networks by displacing the patches. We then extract a traditional triangular mesh from a neural geometry field instance by sampling the displacement. We show that our representation excels in mesh compression, where it significantly reduces the memory footprint of meshes without compromising on surface details.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/39b86d61-f22d-45e1-b500-375276df7e89)


</details>

[📃 arXiv:24xx](https://iveevi.github.io/ngf/pdf/main.pdf) | [⌨️ Code](https://github.com/iveevi/ngf) | [🌐 Project Page](https://iveevi.github.io/ngf/index.html)

#### <summary>MegaScenes: Scene-Level View Synthesis at Scale
Authors: Joseph Tung, Gene Chou, Ruojin Cai, Guandao Yang, Kai Zhang, Gordon Wetzstein, Bharath Hariharan, Noah Snavely
<details span>
<summary><b>Abstract</b></summary>
Scene-level novel view synthesis (NVS) is fundamental to many vision and graphics applications. Recently, pose-conditioned diffusion models have led to significant progress by extracting 3D information from 2D foundation models, but these methods are limited by the lack of scene-level training data. Common dataset choices either consist of isolated objects (Objaverse), or of object-centric scenes with limited pose distributions (DTU, CO3D). In this paper, we create a large-scale scene-level dataset from Internet photo collections, called MegaScenes, which contains over 100K structure from motion (SfM) reconstructions from around the world. Internet photos represent a scalable data source but come with challenges such as lighting and transient objects. We address these issues to further create a subset suitable for the task of NVS. Additionally, we analyze failure cases of state-of-the-art NVS methods and significantly improve generation consistency. Through extensive experiments, we validate the effectiveness of both our dataset and method on generating in-the-wild scenes.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/897975f0-05e1-4f67-86cf-b19edf7b0f8c)


</details>

[📃 arXiv:24xx](https://arxiv.org/pdf/2406.11819v1) | [⌨️ Code](https://github.com/MegaScenes/nvs) | [🌐 Project Page](https://megascenes.github.io/)

#### <summary>FAWN: Floor-And-Walls Normal Regularization for Direct Neural TSDF Reconstruction
Authors: Anna Sokolova, Anna Vorontsova, Bulat Gabdullin, Alexander Limonov
<details span>
<summary><b>Abstract</b></summary>
Leveraging 3D semantics for direct 3D reconstruction has a great potential yet unleashed. For instance, by assuming that walls are vertical, and a floor is planar and horizontal, we can correct distorted room shapes and eliminate local artifacts such as holes, pits, and hills. In this paper, we propose FAWN, a modification of truncated signed distance function (TSDF) reconstruction methods, which considers scene structure by detecting walls and floor in a scene, and penalizing the corresponding surface normals for deviating from the horizontal and vertical directions. Implemented as a 3D sparse convolutional module, FAWN can be incorporated into any trainable pipeline that predicts TSDF. Since FAWN requires 3D semantics only for training, no additional limitations on further use are imposed. We demonstrate, that FAWN-modified methods use semantics more effectively, than existing semantic-based approaches. Besides, we apply our modification to state-of-the-art TSDF reconstruction methods, and demonstrate a quality gain in SCANNET, ICL-NUIM, TUM RGB-D, and 7SCENES benchmarks.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ab351cb8-000d-44da-8d0e-8b64c2cceab5)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.12054) | [⌨️ Code] | [🌐 Project Page]

#### <summary>CityNav: Language-Goal Aerial Navigation Dataset with Geographic Information
Authors: Jungdae Lee, Taiki Miyanishi, Shuhei Kurita, Koya Sakamoto, Daichi Azuma, Yutaka Matsuo, Nakamasa Inoue
<details span>
<summary><b>Abstract</b></summary>
Vision-and-language navigation (VLN) aims to guide autonomous agents through real-world environments by integrating visual and linguistic cues. While substantial progress has been made in understanding these interactive modalities in ground-level navigation, aerial navigation remains largely underexplored. This is primarily due to the scarcity of resources suitable for real-world, city-scale aerial navigation studies. To bridge this gap, we introduce CityNav, a new dataset for language-goal aerial navigation using a 3D point cloud representation from real-world cities. CityNav includes 32,637 natural language descriptions paired with human demonstration trajectories, collected from participants via a new web-based 3D simulator developed for this research. Each description specifies a navigation goal, leveraging the names and locations of landmarks within real-world cities. We also provide baseline models of navigation agents that incorporate an internal 2D spatial map representing landmarks referenced in the descriptions. We benchmark the latest aerial navigation baselines and our proposed model on the CityNav dataset. The results using this dataset reveal the following key findings: (i) Our aerial agent models trained on human demonstration trajectories outperform those trained on shortest path trajectories, highlighting the importance of human-driven navigation strategies; (ii) The integration of a 2D spatial map significantly enhances navigation efficiency at city scale.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ec8e80a3-3478-454b-827a-366a3a5991b4)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.14240) | [⌨️ Code] | [🌐 Project Page](https://water-cookie.github.io/city-nav-proj/)


#### <summary>Freq-Mip-AA : Frequency Mip Representation for Anti-Aliasing Neural Radiance Fields
Authors: Youngin Park, Seungtae Nam, Cheul-hee Hahm, Eunbyung Park
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRF) have shown remarkable success in representing 3D scenes and generating novel views. However, they often struggle with aliasing artifacts, especially when rendering images from different camera distances from the training views. To address the issue, Mip-NeRF proposed using volumetric frustums to render a pixel and suggested integrated positional encoding (IPE). While effective, this approach requires long training times due to its reliance on MLP architecture. In this work, we propose a novel anti-aliasing technique that utilizes grid-based representations, usually showing significantly faster training time. In addition, we exploit frequency-domain representation to handle the aliasing problem inspired by the sampling theorem. The proposed method, FreqMipAA, utilizes scale-specific low-pass filtering (LPF) and learnable frequency masks. Scale-specific low-pass filters (LPF) prevent aliasing and prioritize important image details, and learnable masks effectively remove problematic high-frequency elements while retaining essential information. By employing a scale-specific LPF and trainable masks, FreqMipAA can effectively eliminate the aliasing factor while retaining important details. We validated the proposed technique by incorporating it into a widely used grid-based method. The experimental results have shown that the FreqMipAA effectively resolved the aliasing issues and achieved state-of-the-art results in the multi-scale Blender dataset.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/912b8b95-4c54-4bee-9612-8e8fd5b34b38)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.13251) | [⌨️ Code](https://github.com/yi0109/FreqMipAA) | [🌐 Project Page]


#### <summary>Straight Through Gumbel Softmax Estimator based Bimodal Neural Architecture Search for Audio-Visual Deepfake Detection
Authors: Aravinda Reddy PN, Raghavendra Ramachandra, Krothapalli Sreenivasa Rao, Pabitra Mitra, Vinod Rathod
<details span>
<summary><b>Abstract</b></summary>
Deepfakes are a major security risk for biometric authentication. This technology creates realistic fake videos that can impersonate real people, fooling systems that rely on facial features and voice patterns for identification. Existing multimodal deepfake detectors rely on conventional fusion methods, such as majority rule and ensemble voting, which often struggle to adapt to changing data characteristics and complex patterns. In this paper, we introduce the Straight-through Gumbel-Softmax (STGS) framework, offering a comprehensive approach to search multimodal fusion model architectures. Using a two-level search approach, the framework optimizes the network architecture, parameters, and performance. Initially, crucial features were efficiently identified from backbone networks, whereas within the cell structure, a weighted fusion operation integrated information from various sources. An architecture that maximizes the classification performance is derived by varying parameters such as temperature and sampling time. The experimental results on the FakeAVCeleb and SWAN-DF datasets demonstrated an impressive AUC value 94.4\% achieved with minimal model parameters.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/3f8b7036-9812-4b87-bd77-2ec3efb75be0)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.13384) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Relighting Scenes with Object Insertions in Neural Radiance Fields
Authors: Xuening Zhu, Renjiao Yi, Xin Wen, Chenyang Zhu, Kai Xu
<details span>
<summary><b>Abstract</b></summary>
The insertion of objects into a scene and relighting are commonly utilized applications in augmented reality (AR). Previous methods focused on inserting virtual objects using CAD models or real objects from single-view images, resulting in highly limited AR application scenarios. We propose a novel NeRF-based pipeline for inserting object NeRFs into scene NeRFs, enabling novel view synthesis and realistic relighting, supporting physical interactions like casting shadows onto each other, from two sets of images depicting the object and scene. The lighting environment is in a hybrid representation of Spherical Harmonics and Spherical Gaussians, representing both high- and low-frequency lighting components very well, and supporting non-Lambertian surfaces. Specifically, we leverage the benefits of volume rendering and introduce an innovative approach for efficient shadow rendering by comparing the depth maps between the camera view and the light source view and generating vivid soft shadows. The proposed method achieves realistic relighting effects in extensive experimental evaluations.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/1b5e7a1f-5a07-44c7-84c7-240fed207fad)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.14806) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Crowd-Sourced NeRF: Collecting Data from Production Vehicles for 3D Street View Reconstruction
Authors: Tong Qin, Changze Li, Haoyang Ye, Shaowei Wan, Minzhen Li, Hongwei Liu, Ming Yang
<details span>
<summary><b>Abstract</b></summary>
Recently, Neural Radiance Fields (NeRF) achieved impressive results in novel view synthesis. Block-NeRF showed the capability of leveraging NeRF to build large city-scale models. For large-scale modeling, a mass of image data is necessary. Collecting images from specially designed data-collection vehicles can not support large-scale applications. How to acquire massive high-quality data remains an opening problem. Noting that the automotive industry has a huge amount of image data, crowd-sourcing is a convenient way for large-scale data collection. In this paper, we present a crowd-sourced framework, which utilizes substantial data captured by production vehicles to reconstruct the scene with the NeRF model. This approach solves the key problem of large-scale reconstruction, that is where the data comes from and how to use them. Firstly, the crowd-sourced massive data is filtered to remove redundancy and keep a balanced distribution in terms of time and space. Then a structure-from-motion module is performed to refine camera poses. Finally, images, as well as poses, are used to train the NeRF model in a certain block. We highlight that we present a comprehensive framework that integrates multiple modules, including data selection, sparse 3D reconstruction, sequence appearance embedding, depth supervision of ground surface, and occlusion completion. The complete system is capable of effectively processing and reconstructing high-quality 3D scenes from crowd-sourced data. Extensive quantitative and qualitative experiments were conducted to validate the performance of our system. Moreover, we proposed an application, named first-view navigation, which leveraged the NeRF model to generate 3D street view and guide the driver with a synthesized video.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/488523b6-4f73-4a5a-89e3-dd0b01de271b)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.16289) | [⌨️ Code] | [🌐 Project Page]


#### <summary>NerfBaselines: Consistent and Reproducible Evaluation of Novel View Synthesis Methods
Authors: Jonas Kulhanek, Torsten Sattler
<details span>
<summary><b>Abstract</b></summary>
Novel view synthesis is an important problem with many applications, including AR/VR, gaming, and simulations for robotics. With the recent rapid development of Neural Radiance Fields (NeRFs) and 3D Gaussian Splatting (3DGS) methods, it is becoming difficult to keep track of the current state of the art (SoTA) due to methods using different evaluation protocols, codebases being difficult to install and use, and methods not generalizing well to novel 3D scenes. Our experiments support this claim by showing that tiny differences in evaluation protocols of various methods can lead to inconsistent reported metrics. To address these issues, we propose a framework called NerfBaselines, which simplifies the installation of various methods, provides consistent benchmarking tools, and ensures reproducibility. We validate our implementation experimentally by reproducing numbers reported in the original papers. To further improve the accessibility, we release a web platform where commonly used methods are compared on standard benchmarks.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/0c1b7424-4c79-4838-b267-c6d3aec9b895)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.17345) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Segment Anything without Supervision
Authors: XuDong Wang, Jingfeng Yang, Trevor Darrell
<details span>
<summary><b>Abstract</b></summary>
The Segmentation Anything Model (SAM) requires labor-intensive data labeling. We present Unsupervised SAM (UnSAM) for promptable and automatic whole-image segmentation that does not require human annotations. UnSAM utilizes a divide-and-conquer strategy to "discover" the hierarchical structure of visual scenes. We first leverage top-down clustering methods to partition an unlabeled image into instance/semantic level segments. For all pixels within a segment, a bottom-up clustering method is employed to iteratively merge them into larger groups, thereby forming a hierarchical structure. These unsupervised multi-granular masks are then utilized to supervise model training. Evaluated across seven popular datasets, UnSAM achieves competitive results with the supervised counterpart SAM, and surpasses the previous state-of-the-art in unsupervised segmentation by 11% in terms of AR. Moreover, we show that supervised SAM can also benefit from our self-supervised labels. By integrating our unsupervised pseudo masks into SA-1B's ground-truth masks and training UnSAM with only 1% of SA-1B, a lightly semi-supervised UnSAM can often segment entities overlooked by supervised SAM, exceeding SAM's AR by over 6.7% and AP by 3.9% on SA-1B.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/95b95842-16a1-4d1f-b65c-e69375553e7c)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.20081) | [⌨️ Code] | [🌐 Project Page]


#### <summary>A Survey on Deep Clustering: From the Prior Perspective
Authors: Yiding Lu, Haobin Li, Yunfan Li, Yijie Lin, Xi Peng
<details span>
<summary><b>Abstract</b></summary>
Facilitated by the powerful feature extraction ability of neural networks, deep clustering has achieved great success in analyzing high-dimensional and complex real-world data. The performance of deep clustering methods is affected by various factors such as network structures and learning objectives. However, as pointed out in this survey, the essence of deep clustering lies in the incorporation and utilization of prior knowledge, which is largely ignored by existing works. From pioneering deep clustering methods based on data structure assumptions to recent contrastive clustering methods based on data augmentation invariances, the development of deep clustering intrinsically corresponds to the evolution of prior knowledge. In this survey, we provide a comprehensive review of deep clustering methods by categorizing them into six types of prior knowledge. We find that in general the prior innovation follows two trends, namely, i) from mining to constructing, and ii) from internal to external. Besides, we provide a benchmark on five widely-used datasets and analyze the performance of methods with diverse priors. By providing a novel prior knowledge perspective, we hope this survey could provide some novel insights and inspire future research in the deep clustering community.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9b2b2fec-3153-49a9-8925-fad6cace67b7)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.19602) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Grounding Image Matching in 3D with MASt3R
Authors: Vincent Leroy, Yohann Cabon, Jérôme Revaud
<details span>
<summary><b>Abstract</b></summary>
Image Matching is a core component of all best-performing algorithms and pipelines in 3D vision. Yet despite matching being fundamentally a 3D problem, intrinsically linked to camera pose and scene geometry, it is typically treated as a 2D problem. This makes sense as the goal of matching is to establish correspondences between 2D pixel fields, but also seems like a potentially hazardous choice. In this work, we take a different stance and propose to cast matching as a 3D task with DUSt3R, a recent and powerful 3D reconstruction framework based on Transformers. Based on pointmaps regression, this method displayed impressive robustness in matching views with extreme viewpoint changes, yet with limited accuracy. We aim here to improve the matching capabilities of such an approach while preserving its robustness. We thus propose to augment the DUSt3R network with a new head that outputs dense local features, trained with an additional matching loss. We further address the issue of quadratic complexity of dense matching, which becomes prohibitively slow for downstream applications if not carefully treated. We introduce a fast reciprocal matching scheme that not only accelerates matching by orders of magnitude, but also comes with theoretical guarantees and, lastly, yields improved results. Extensive experiments show that our approach, coined MASt3R, significantly outperforms the state of the art on multiple matching tasks. In particular, it beats the best published methods by 30% (absolute improvement) in VCRE AUC on the extremely challenging Map-free localization dataset.

![image](https://github.com/user-attachments/assets/586a7a51-221e-44dc-bb1b-bce19f6003fa)

</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.09756) | [⌨️ Code](https://github.com/naver/mast3r?tab=readme-ov-file) | [🌐 Project Page](https://europe.naverlabs.com/blog/mast3r-matching-and-stereo-3d-reconstruction/)



#### <summary>SfM on-the-fly: Get better 3D from What You Capture
Authors: Zhan Zongqian, Yu Yifei, Xia Rui, Gan Wentian, Xie Hong, Perda Giulio, Morelli Luca, Remondino Fabio, Wang Xin
<details span>
<summary><b>Abstract</b></summary>
In the last twenty years, Structure from Motion (SfM) has been a constant research hotspot in the fields of photogrammetry, computer vision, robotics etc., whereas real-time performance is just a recent topic of growing interest. This work builds upon the original on-the-fly SfM (Zhan et al., 2024) and presents an updated version with three new advancements to get better 3D from what you capture: (i) real-time image matching is further boosted by employing the Hierarchical Navigable Small World (HNSW) graphs, thus more true positive overlapping image candidates are faster identified; (ii) a self-adaptive weighting strategy is proposed for robust hierarchical local bundle adjustment to improve the SfM results; (iii) multiple agents are included for supporting collaborative SfM and seamlessly merge multiple 3D reconstructions into a complete 3D scene when commonly registered images appear. Various comprehensive experiments demonstrate that the proposed SfM method (named on-the-fly SfMv2) can generate more complete and robust 3D reconstructions in a high time-efficient way.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/f511b04f-305a-470c-9b0d-1f88622fdf51)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.03939) | [⌨️ Code](https://github.com/RayShark0605/On_the_fly_SfM) | [🌐 Project Page](https://yifeiyu225.github.io/on-the-flySfMv2.github.io/)

#### <summary>Enhancing Neural Radiance Fields with Depth and Normal Completion Priors from Sparse Views
Authors: Jiawei Guo, HungChyun Chou, Ning Ding
<details span>
<summary><b>Abstract</b></summary>
Neural Radiance Fields (NeRF) are an advanced technology that creates highly realistic images by learning about scenes through a neural network model. However, NeRF often encounters issues when there are not enough images to work with, leading to problems in accurately rendering views. The main issue is that NeRF lacks sufficient structural details to guide the rendering process accurately. To address this, we proposed a Depth and Normal Dense Completion Priors for NeRF (CP\_NeRF) framework. This framework enhances view rendering by adding depth and normal dense completion priors to the NeRF optimization process. Before optimizing NeRF, we obtain sparse depth maps using the Structure from Motion (SfM) technique used to get camera poses. Based on the sparse depth maps and a normal estimator, we generate sparse normal maps for training a normal completion prior with precise standard deviations. During optimization, we apply depth and normal completion priors to transform sparse data into dense depth and normal maps with their standard deviations. We use these dense maps to guide ray sampling, assist distance sampling and construct a normal loss function for better training accuracy. To improve the rendering of NeRF's normal outputs, we incorporate an optical centre position embedder that helps synthesize more accurate normals through volume rendering. Additionally, we employ a normal patch matching technique to choose accurate rendered normal maps, ensuring more precise supervision for the model. Our method is superior to leading techniques in rendering detailed indoor scenes, even with limited input views.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/908b1caa-d340-4f63-b475-8ba93b94ddea)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.05666) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Category-level Object Detection, Pose Estimation and Reconstruction from Stereo Images
Authors: Chuanrui Zhang, Yonggen Ling, Minglei Lu, Minghan Qin, Haoqian Wang
<details span>
<summary><b>Abstract</b></summary>
We study the 3D object understanding task for manipulating everyday objects with different material properties (diffuse, specular, transparent and mixed). Existing monocular and RGB-D methods suffer from scale ambiguity due to missing or imprecise depth measurements. We present CODERS, a one-stage approach for Category-level Object Detection, pose Estimation and Reconstruction from Stereo images. The base of our pipeline is an implicit stereo matching module that combines stereo image features with 3D position information. Concatenating this presented module and the following transform-decoder architecture leads to end-to-end learning of multiple tasks required by robot manipulation. Our approach significantly outperforms all competing methods in the public TOD dataset. Furthermore, trained on simulated data, CODERS generalize well to unseen category-level object instances in real-world robot manipulation experiments. Our dataset, code, and demos will be available on our project page.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/2ffe2ccb-fbd1-4237-acc9-6b1d8a7c51ee)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.06984) | [⌨️ Code] | [🌐 Project Page]


#### <summary>BiEquiFormer: Bi-Equivariant Representations for Global Point Cloud Registration
Authors: Stefanos Pertigkiozoglou, Evangelos Chatzipantazis, Kostas Daniilidis
<details span>
<summary><b>Abstract</b></summary>
The goal of this paper is to address the problem of \textit{global} point cloud registration (PCR) i.e., finding the optimal alignment between point clouds irrespective of the initial poses of the scans. This problem is notoriously challenging for classical optimization methods due to computational constraints. First, we show that state-of-the-art deep learning methods suffer from huge performance degradation when the point clouds are arbitrarily placed in space. We propose that \textit{equivariant deep learning} should be utilized for solving this task and we characterize the specific type of bi-equivariance of PCR. Then, we design BiEquiformer a novel and scalable \textit{bi-equivariant} pipeline i.e. equivariant to the independent transformations of the input point clouds. While a naive approach would process the point clouds independently we design expressive bi-equivariant layers that fuse the information from both point clouds. This allows us to extract high-quality superpoint correspondences and in turn, robust point-cloud registration. Extensive comparisons against state-of-the-art methods show that our method achieves comparable performance in the canonical setting and superior performance in the robust setting in both the 3DMatch and the challenging low-overlap 3DLoMatch dataset.

![image](https://github.com/user-attachments/assets/d92c9c64-b53f-403a-ac57-49a9a547630d)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.08729) | [⌨️ Code] | [🌐 Project Page]


#### <summary>OmniNOCS: A unified NOCS dataset and model for 3D lifting of 2D objects
Authors: Akshay Krishnan, Abhijit Kundu, Kevis-Kokitsi Maninis, James Hays, Matthew Brown
<details span>
<summary><b>Abstract</b></summary>
We propose OmniNOCS, a large-scale monocular dataset with 3D Normalized Object Coordinate Space (NOCS) maps, object masks, and 3D bounding box annotations for indoor and outdoor scenes. OmniNOCS has 20 times more object classes and 200 times more instances than existing NOCS datasets (NOCS-Real275, Wild6D). We use OmniNOCS to train a novel, transformer-based monocular NOCS prediction model (NOCSformer) that can predict accurate NOCS, instance masks and poses from 2D object detections across diverse classes. It is the first NOCS model that can generalize to a broad range of classes when prompted with 2D boxes. We evaluate our model on the task of 3D oriented bounding box prediction, where it achieves comparable results to state-of-the-art 3D detection methods such as Cube R-CNN. Unlike other 3D detection methods, our model also provides detailed and accurate 3D object shape and segmentation. We propose a novel benchmark for the task of NOCS prediction based on OmniNOCS, which we hope will serve as a useful baseline for future work in this area.

![image](https://github.com/user-attachments/assets/47a7899d-7166-451c-9f62-9acaa5652feb)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.08711) | [⌨️ Code](https://github.com/google-deepmind/omninocs) | [🌐 Project Page](https://omninocs.github.io/)

#### <summary>SRPose: Two-view Relative Pose Estimation with Sparse Keypoints
Authors: Rui Yin, Yulun Zhang, Zherong Pan, Jianjun Zhu, Cheng Wang, Biao Jia
<details span>
<summary><b>Abstract</b></summary>
Two-view pose estimation is essential for map-free visual relocalization and object pose tracking tasks. However, traditional matching methods suffer from time-consuming robust estimators, while deep learning-based pose regressors only cater to camera-to-world pose estimation, lacking generalizability to different image sizes and camera intrinsics. In this paper, we propose SRPose, a sparse keypoint-based framework for two-view relative pose estimation in camera-to-world and object-to-camera scenarios. SRPose consists of a sparse keypoint detector, an intrinsic-calibration position encoder, and promptable prior knowledge-guided attention layers. Given two RGB images of a fixed scene or a moving object, SRPose estimates the relative camera or 6D object pose transformation. Extensive experiments demonstrate that SRPose achieves competitive or superior performance compared to state-of-the-art methods in terms of accuracy and speed, showing generalizability to both scenarios. It is robust to different image sizes and camera intrinsics, and can be deployed with low computing resources.

![image](https://github.com/user-attachments/assets/a8ce5d31-0fa4-4150-92ef-8bc832ae6d8f)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.08199) | [⌨️ Code] | [🌐 Project Page]

#### <summary>ScaleDepth: Decomposing Metric Depth Estimation into Scale Prediction and Relative Depth Estimation
Authors: Ruijie Zhu, Chuxin Wang, Ziyang Song, Li Liu, Tianzhu Zhang, Yongdong Zhang
<details span>
<summary><b>Abstract</b></summary>
Estimating depth from a single image is a challenging visual task. Compared to relative depth estimation, metric depth estimation attracts more attention due to its practical physical significance and critical applications in real-life scenarios. However, existing metric depth estimation methods are typically trained on specific datasets with similar scenes, facing challenges in generalizing across scenes with significant scale variations. To address this challenge, we propose a novel monocular depth estimation method called ScaleDepth. Our method decomposes metric depth into scene scale and relative depth, and predicts them through a semantic-aware scale prediction (SASP) module and an adaptive relative depth estimation (ARDE) module, respectively. The proposed ScaleDepth enjoys several merits. First, the SASP module can implicitly combine structural and semantic features of the images to predict precise scene scales. Second, the ARDE module can adaptively estimate the relative depth distribution of each image within a normalized depth space. Third, our method achieves metric depth estimation for both indoor and outdoor scenes in a unified framework, without the need for setting the depth range or fine-tuning model. Extensive experiments demonstrate that our method attains state-of-the-art performance across indoor, outdoor, unconstrained, and unseen scenes.

![image](https://github.com/user-attachments/assets/cc893f0a-af77-49c3-bb7e-e0aea78b1d14)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.08187) | [⌨️ Code] | [🌐 Project Page](https://ruijiezhu94.github.io/ScaleDepth/)


#### <summary>Efficient Training with Denoised Neural Weights
Authors: Yifan Gong, Zheng Zhan, Yanyu Li, Yerlan Idelbayev, Andrey Zharkov, Kfir Aberman, Sergey Tulyakov, Yanzhi Wang, Jian Ren
<details span>
<summary><b>Abstract</b></summary>
Good weight initialization serves as an effective measure to reduce the training cost of a deep neural network (DNN) model. The choice of how to initialize parameters is challenging and may require manual tuning, which can be time-consuming and prone to human error. To overcome such limitations, this work takes a novel step towards building a weight generator to synthesize the neural weights for initialization. We use the image-to-image translation task with generative adversarial networks (GANs) as an example due to the ease of collecting model weights spanning a wide range. Specifically, we first collect a dataset with various image editing concepts and their corresponding trained weights, which are later used for the training of the weight generator. To address the different characteristics among layers and the substantial number of weights to be predicted, we divide the weights into equal-sized blocks and assign each block an index. Subsequently, a diffusion model is trained with such a dataset using both text conditions of the concept and the block indexes. By initializing the image translation model with the denoised weights predicted by our diffusion model, the training requires only 43.3 seconds. Compared to training from scratch (i.e., Pix2pix), we achieve a 15x training time acceleration for a new concept while obtaining even better image generation quality.

![image](https://github.com/user-attachments/assets/e025a189-a9d2-4574-a8bc-d9d9df0a3a51)


</details>

[📃 arXiv:2407] | [⌨️ Code](https://github.com/Yifanfanfanfan/Yifanfanfanfan.github.io/tree/main/e2gan) | [🌐 Project Page](https://yifanfanfanfan.github.io/denoised-weights/)

#### <summary>Segment, Lift and Fit: Automatic 3D Shape Labeling from 2D Prompts
Authors: Jianhao Li, Tianyu Sun, Zhongdao Wang, Enze Xie, Bailan Feng, Hongbo Zhang, Ze Yuan, Ke Xu, Jiaheng Liu, Ping Luo
<details span>
<summary><b>Abstract</b></summary>
This paper proposes an algorithm for automatically labeling 3D objects from 2D point or box prompts, especially focusing on applications in autonomous driving. Unlike previous arts, our auto-labeler predicts 3D shapes instead of bounding boxes and does not require training on a specific dataset. We propose a Segment, Lift, and Fit (SLF) paradigm to achieve this goal. Firstly, we segment high-quality instance masks from the prompts using the Segment Anything Model (SAM) and transform the remaining problem into predicting 3D shapes from given 2D masks. Due to the ill-posed nature of this problem, it presents a significant challenge as multiple 3D shapes can project into an identical mask. To tackle this issue, we then lift 2D masks to 3D forms and employ gradient descent to adjust their poses and shapes until the projections fit the masks and the surfaces conform to surrounding LiDAR points. Notably, since we do not train on a specific dataset, the SLF auto-labeler does not overfit to biased annotation patterns in the training set as other methods do. Thus, the generalization ability across different datasets improves. Experimental results on the KITTI dataset demonstrate that the SLF auto-labeler produces high-quality bounding box annotations, achieving an AP@0.5 IoU of nearly 90\%. Detectors trained with the generated pseudo-labels perform nearly as well as those trained with actual ground-truth annotations. Furthermore, the SLF auto-labeler shows promising results in detailed shape predictions, providing a potential alternative for the occupancy annotation of dynamic objects.

![image](https://github.com/user-attachments/assets/36863121-cf96-4a39-854d-3db00538702c)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.11382) | [⌨️ Code] | [🌐 Project Page]

#### <summary>GroundUp: Rapid Sketch-Based 3D City Massing
Authors: Gizem Esra Unlu, Mohamed Sayed, Yulia Gryaditskaya, Gabriel Brostow
<details span>
<summary><b>Abstract</b></summary>
We propose GroundUp, the first sketch-based ideation tool for 3D city massing of urban areas. We focus on early-stage urban design, where sketching is a common tool and the design starts from balancing building volumes (masses) and open spaces. With Human-Centered AI in mind, we aim to help architects quickly revise their ideas by easily switching between 2D sketches and 3D models, allowing for smoother iteration and sharing of ideas. Inspired by feedback from architects and existing workflows, our system takes as a first input a user sketch of multiple buildings in a top-down view. The user then draws a perspective sketch of the envisioned site. Our method is designed to exploit the complementarity of information in the two sketches and allows users to quickly preview and adjust the inferred 3D shapes. Our model has two main components. First, we propose a novel sketch-to-depth prediction network for perspective sketches that exploits top-down sketch shapes. Second, we use depth cues derived from the perspective sketch as a condition to our diffusion model, which ultimately completes the geometry in a top-down view. Thus, our final 3D geometry is represented as a heightfield, allowing users to construct the city `from the ground up'.

![image](https://github.com/user-attachments/assets/09fc7dfd-0b75-44e1-83c8-051023c57173)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12739) | [⌨️ Code] | [🌐 Project Page](http://visual.cs.ucl.ac.uk/pubs/groundup/index.html)

#### <summary>SG-NeRF: Neural Surface Reconstruction with Scene Graph Optimization
Authors: Yiyang Chen, Siyan Dong, Xulong Wang, Lulu Cai, Youyi Zheng, Yanchao Yang
<details span>
<summary><b>Abstract</b></summary>
3D surface reconstruction from images is essential for numerous applications. Recently, Neural Radiance Fields (NeRFs) have emerged as a promising framework for 3D modeling. However, NeRFs require accurate camera poses as input, and existing methods struggle to handle significantly noisy pose estimates (i.e., outliers), which are commonly encountered in real-world scenarios. To tackle this challenge, we present a novel approach that optimizes radiance fields with scene graphs to mitigate the influence of outlier poses. Our method incorporates an adaptive inlier-outlier confidence estimation scheme based on scene graphs, emphasizing images of high compatibility with the neighborhood and consistency in the rendering quality. We also introduce an effective intersection-over-union (IoU) loss to optimize the camera pose and surface geometry, together with a coarse-to-fine strategy to facilitate the training. Furthermore, we propose a new dataset containing typical outlier poses for a detailed evaluation. Experimental results on various datasets consistently demonstrate the effectiveness and superiority of our method over existing approaches, showcasing its robustness in handling outliers and producing high-quality 3D reconstructions.

![image](https://github.com/user-attachments/assets/dd6a8f2d-2b93-4274-9443-7fcf1596e392)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12667) | [⌨️ Code](https://github.com/Iris-cyy/SG-NeRF) | [🌐 Project Page]


#### <summary>InfoNorm: Mutual Information Shaping of Normals for Sparse-View Reconstruction
Authors: Xulong Wang, Siyan Dong, Youyi Zheng, Yanchao Yang
<details span>
<summary><b>Abstract</b></summary>
3D surface reconstruction from multi-view images is essential for scene understanding and interaction. However, complex indoor scenes pose challenges such as ambiguity due to limited observations. Recent implicit surface representations, such as Neural Radiance Fields (NeRFs) and signed distance functions (SDFs), employ various geometric priors to resolve the lack of observed information. Nevertheless, their performance heavily depends on the quality of the pre-trained geometry estimation models. To ease such dependence, we propose regularizing the geometric modeling by explicitly encouraging the mutual information among surface normals of highly correlated scene points. In this way, the geometry learning process is modulated by the second-order correlations from noisy (first-order) geometric priors, thus eliminating the bias due to poor generalization. Additionally, we introduce a simple yet effective scheme that utilizes semantic and geometric features to identify correlated points, enhancing their mutual information accordingly. The proposed technique can serve as a plugin for SDF-based neural surface representations. Our experiments demonstrate the effectiveness of the proposed in improving the surface reconstruction quality of major states of the arts.

![image](https://github.com/user-attachments/assets/75855334-e4f7-4049-a3c9-30907fe1cc02)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12661) | [⌨️ Code](https://github.com/Muliphein/InfoNorm) | [🌐 Project Page]

#### <summary>SCAPE: A Simple and Strong Category-Agnostic Pose Estimator
Authors: Yujia Liang, Zixuan Ye, Wenze Liu, Hao Lu
<details span>
<summary><b>Abstract</b></summary>
Category-Agnostic Pose Estimation (CAPE) aims to localize keypoints on an object of any category given few exemplars in an in-context manner. Prior arts involve sophisticated designs, e.g., sundry modules for similarity calculation and a two-stage framework, or takes in extra heatmap generation and supervision. We notice that CAPE is essentially a task about feature matching, which can be solved within the attention process. Therefore we first streamline the architecture into a simple baseline consisting of several pure self-attention layers and an MLP regression head -- this simplification means that one only needs to consider the attention quality to boost the performance of CAPE. Towards an effective attention process for CAPE, we further introduce two key modules: i) a global keypoint feature perceptor to inject global semantic information into support keypoints, and ii) a keypoint attention refiner to enhance inter-node correlation between keypoints. They jointly form a Simple and strong Category-Agnostic Pose Estimator (SCAPE). Experimental results show that SCAPE outperforms prior arts by 2.2 and 1.3 PCK under 1-shot and 5-shot settings with faster inference speed and lighter model capacity, excelling in both accuracy and efficiency.

![image](https://github.com/user-attachments/assets/958a1ec9-9cd7-43c5-9df4-1a88ea4fffd7)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.13483) | [⌨️ Code](https://github.com/tiny-smart/SCAPE?tab=readme-ov-file) | [🌐 Project Page]

#### <summary>Implicit Filtering for Learning Neural Signed Distance Functions from 3D Point Clouds
Authors: Shengtao Li, Ge Gao, Yudong Liu, Ming Gu, Yu-Shen Liu
<details span>
<summary><b>Abstract</b></summary>
Neural signed distance functions (SDFs) have shown powerful ability in fitting the shape geometry. However, inferring continuous signed distance fields from discrete unoriented point clouds still remains a challenge. The neural network typically fits the shape with a rough surface and omits fine-grained geometric details such as shape edges and corners. In this paper, we propose a novel non-linear implicit filter to smooth the implicit field while preserving high-frequency geometry details. Our novelty lies in that we can filter the surface (zero level set) by the neighbor input points with gradients of the signed distance field. By moving the input raw point clouds along the gradient, our proposed implicit filtering can be extended to non-zero level sets to keep the promise consistency between different level sets, which consequently results in a better regularization of the zero level set. We conduct comprehensive experiments in surface reconstruction from objects and complex scene point clouds, the numerical and visual comparisons demonstrate our improvements over the state-of-the-art methods under the widely used benchmarks.

![image](https://github.com/user-attachments/assets/db3c8d86-438d-41f7-b3e7-c9f4f066cb7f)

</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.13342) | [⌨️ Code] | [🌐 Project Page](https://list17.github.io/ImplicitFilter)

#### <summary>GenRC: Generative 3D Room Completion from Sparse Image Collections
Authors: Ming-Feng Li, Yueh-Feng Ku, Hong-Xuan Yen, Chi Liu, Yu-Lun Liu, Albert Y. C. Chen, Cheng-Hao Kuo, Min Sun
<details span>
<summary><b>Abstract</b></summary>
Sparse RGBD scene completion is a challenging task especially when considering consistent textures and geometries throughout the entire scene. Different from existing solutions that rely on human-designed text prompts or predefined camera trajectories, we propose GenRC, an automated training-free pipeline to complete a room-scale 3D mesh with high-fidelity textures. To achieve this, we first project the sparse RGBD images to a highly incomplete 3D mesh. Instead of iteratively generating novel views to fill in the void, we utilized our proposed E-Diffusion to generate a view-consistent panoramic RGBD image which ensures global geometry and appearance consistency. Furthermore, we maintain the input-output scene stylistic consistency through textual inversion to replace human-designed text prompts. To bridge the domain gap among datasets, E-Diffusion leverages models trained on large-scale datasets to generate diverse appearances. GenRC outperforms state-of-the-art methods under most appearance and geometric metrics on ScanNet and ARKitScenes datasets, even though GenRC is not trained on these datasets nor using predefined camera trajectories.

![image](https://github.com/user-attachments/assets/b72c0d14-7adc-4c8a-ba1b-55b131a8fd9d)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.12939) | [⌨️ Code](https://github.com/minfenli/GenRC) | [🌐 Project Page](https://minfenli.github.io/GenRC/)

#### <summary>Learning Where to Look: Self-supervised Viewpoint Selection for Active Localization using Geometrical Information
Authors: Luca Di Giammarino, Boyang Sun, Giorgio Grisetti, Marc Pollefeys, Hermann Blum, Daniel Barath
<details span>
<summary><b>Abstract</b></summary>
Accurate localization in diverse environments is a fundamental challenge in computer vision and robotics. The task involves determining a sensor's precise position and orientation, typically a camera, within a given space. Traditional localization methods often rely on passive sensing, which may struggle in scenarios with limited features or dynamic environments. In response, this paper explores the domain of active localization, emphasizing the importance of viewpoint selection to enhance localization accuracy. Our contributions involve using a data-driven approach with a simple architecture designed for real-time operation, a self-supervised data training method, and the capability to consistently integrate our map into a planning framework tailored for real-world robotics applications. Our results demonstrate that our method performs better than the existing one, targeting similar problems and generalizing on synthetic and real data. We also release an open-source implementation to benefit the community.

![image](https://github.com/user-attachments/assets/57c8de49-2304-4c02-8373-d989c8b629d6)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.15593) | [⌨️ Code](https://github.com/rvp-group/learning-where-to-look) | [🌐 Project Page]

#### <summary>MonoWAD: Weather-Adaptive Diffusion Model for Robust Monocular 3D Object Detection
Authors: Youngmin Oh, Hyung-Il Kim, Seong Tae Kim, Jung Uk Kim
<details span>
<summary><b>Abstract</b></summary>
Monocular 3D object detection is an important challenging task in autonomous driving. Existing methods mainly focus on performing 3D detection in ideal weather conditions, characterized by scenarios with clear and optimal visibility. However, the challenge of autonomous driving requires the ability to handle changes in weather conditions, such as foggy weather, not just clear weather. We introduce MonoWAD, a novel weather-robust monocular 3D object detector with a weather-adaptive diffusion model. It contains two components: (1) the weather codebook to memorize the knowledge of the clear weather and generate a weather-reference feature for any input, and (2) the weather-adaptive diffusion model to enhance the feature representation of the input feature by incorporating a weather-reference feature. This serves an attention role in indicating how much improvement is needed for the input feature according to the weather conditions. To achieve this goal, we introduce a weather-adaptive enhancement loss to enhance the feature representation under both clear and foggy weather conditions. Extensive experiments under various weather conditions demonstrate that MonoWAD achieves weather-robust monocular 3D object detection.

![image](https://github.com/user-attachments/assets/0ae66e45-a5f0-44fd-bfbf-f48e1ec1a93b)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.16448) | [⌨️ Code](https://github.com/VisualAIKHU/MonoWAD) | [🌐 Project Page]

#### <summary>Global Structure-from-Motion Revisited
Authors: Linfei Pan, Dániel Baráth, Marc Pollefeys, Johannes L. Schönberger
<details span>
<summary><b>Abstract</b></summary>
Recovering 3D structure and camera motion from images has been a long-standing focus of computer vision research and is known as Structure-from-Motion (SfM). Solutions to this problem are categorized into incremental and global approaches. Until now, the most popular systems follow the incremental paradigm due to its superior accuracy and robustness, while global approaches are drastically more scalable and efficient. With this work, we revisit the problem of global SfM and propose GLOMAP as a new general-purpose system that outperforms the state of the art in global SfM. In terms of accuracy and robustness, we achieve results on-par or superior to COLMAP, the most widely used incremental SfM, while being orders of magnitude faster.

![image](https://github.com/user-attachments/assets/2e8cffe5-caa7-4713-bbc4-2d54011a462a)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.20219) | [⌨️ Code](https://github.com/colmap/glomap) | [🌐 Project Page](https://lpanaf.github.io/eccv24_glomap/)

#### <summary>Text2LiDAR: Text-guided LiDAR Point Cloud Generation via Equirectangular Transformer
Authors: Yang Wu, Kaihua Zhang, Jianjun Qian, Jin Xie, Jian Yang
<details span>
<summary><b>Abstract</b></summary>
The complex traffic environment and various weather conditions make the collection of LiDAR data expensive and challenging. Achieving high-quality and controllable LiDAR data generation is urgently needed, controlling with text is a common practice, but there is little research in this field. To this end, we propose Text2LiDAR, the first efficient, diverse, and text-controllable LiDAR data generation model. Specifically, we design an equirectangular transformer architecture, utilizing the designed equirectangular attention to capture LiDAR features in a manner with data characteristics. Then, we design a control-signal embedding injector to efficiently integrate control signals through the global-to-focused attention mechanism. Additionally, we devise a frequency modulator to assist the model in recovering high-frequency details, ensuring the clarity of the generated point cloud. To foster development in the field and optimize text-controlled generation performance, we construct nuLiDARtext which offers diverse text descriptors for 34,149 LiDAR point clouds from 850 scenes. Experiments on uncontrolled and text-controlled generation in various forms on KITTI-360 and nuScenes datasets demonstrate the superiority of our approach.

![image](https://github.com/user-attachments/assets/4824516e-bae6-4a79-9e8c-36bed3ab66b5)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.19628) | [⌨️ Code] | [🌐 Project Page]


#### <summary>MSP-MVS: Multi-granularity Segmentation Prior Guided Multi-View Stereo
Authors: Zhenlong Yuan, Cong Liu, Fei Shen, Zhaoxin Li, Tianlu Mao, Zhaoqi Wang
<details span>
<summary><b>Abstract</b></summary>
Reconstructing textureless areas in MVS poses challenges due to the absence of reliable pixel correspondences within fixed patch. Although certain methods employ patch deformation to expand the receptive field, their patches mistakenly skip depth edges to calculate areas with depth discontinuity, thereby causing ambiguity. Consequently, we introduce Multi-granularity Segmentation Prior Multi-View Stereo (MSP-MVS). Specifically, we first propose multi-granularity segmentation prior by integrating multi-granularity depth edges to restrict patch deformation within homogeneous areas. Moreover, we present anchor equidistribution that bring deformed patches with more uniformly distributed anchors to ensure an adequate coverage of their own homogeneous areas. Furthermore, we introduce iterative local search optimization to represent larger patch with sparse representative candidates, significantly boosting the expressive capacity for each patch. The state-of-the-art results on ETH3D and Tanks & Temples benchmarks demonstrate the effectiveness and robust generalization ability of our proposed method.

![image](https://github.com/user-attachments/assets/0f257b3d-01ed-4184-a7b8-02cee60c19da)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.19323) | [⌨️ Code] | [🌐 Project Page]

#### <summary>A Comparative Study of Neural Surface Reconstruction for Scientific Visualization
Authors: Siyuan Yao, Weixi Song, Chaoli Wang
<details span>
<summary><b>Abstract</b></summary>
This comparative study evaluates various neural surface reconstruction methods, particularly focusing on their implications for scientific visualization through reconstructing 3D surfaces via multi-view rendering images. We categorize ten methods into neural radiance fields and neural implicit surfaces, uncovering the benefits of leveraging distance functions (i.e., SDFs and UDFs) to enhance the accuracy and smoothness of the reconstructed surfaces. Our findings highlight the efficiency and quality of NeuS2 for reconstructing closed surfaces and identify NeUDF as a promising candidate for reconstructing open surfaces despite some limitations. By sharing our benchmark dataset, we invite researchers to test the performance of their methods, contributing to the advancement of surface reconstruction solutions for scientific visualization.

![image](https://github.com/user-attachments/assets/0468e8a1-95ad-43c1-8eeb-35ed2071f392)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.20868) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Forecasting Future Videos from Novel Views via Disentangled 3D Scene Representation
Authors: Sudhir Yarram, Junsong Yuan
<details span>
<summary><b>Abstract</b></summary>
Video extrapolation in space and time (VEST) enables viewers to forecast a 3D scene into the future and view it from novel viewpoints. Recent methods propose to learn an entangled representation, aiming to model layered scene geometry, motion forecasting and novel view synthesis together, while assuming simplified affine motion and homography-based warping at each scene layer, leading to inaccurate video extrapolation. Instead of entangled scene representation and rendering, our approach chooses to disentangle scene geometry from scene motion, via lifting the 2D scene to 3D point clouds, which enables high quality rendering of future videos from novel views. To model future 3D scene motion, we propose a disentangled two-stage approach that initially forecasts ego-motion and subsequently the residual motion of dynamic objects (e.g., cars, people). This approach ensures more precise motion predictions by reducing inaccuracies from entanglement of ego-motion with dynamic object motion, where better ego-motion forecasting could significantly enhance the visual outcomes. Extensive experimental analysis on two urban scene datasets demonstrate superior performance of our proposed method in comparison to strong baselines.

![image](https://github.com/user-attachments/assets/6b33a117-ed42-4481-9def-50a6a810de86)


</details>

[📃 arXiv:2407](https://arxiv.org/pdf/2407.21450) | [⌨️ Code] | [🌐 Project Page](https://skrya.github.io/projects/ffn-dsr/)

#### <summary>PanoFree: Tuning-Free Holistic Multi-view Image Generation with Cross-view Self-Guidance
Authors: Aoming Liu, Zhong Li, Zhang Chen, Nannan Li, Yi Xu, Bryan A. Plummer
<details span>
<summary><b>Abstract</b></summary>
Immersive scene generation, notably panorama creation, benefits significantly from the adaptation of large pre-trained text-to-image (T2I) models for multi-view image generation. Due to the high cost of acquiring multi-view images, tuning-free generation is preferred. However, existing methods are either limited to simple correspondences or require extensive fine-tuning to capture complex ones. We present PanoFree, a novel method for tuning-free multi-view image generation that supports an extensive array of correspondences. PanoFree sequentially generates multi-view images using iterative warping and inpainting, addressing the key issues of inconsistency and artifacts from error accumulation without the need for fine-tuning. It improves error accumulation by enhancing cross-view awareness and refines the warping and inpainting processes via cross-view guidance, risky area estimation and erasing, and symmetric bidirectional guided generation for loop closure, alongside guidance-based semantic and density control for scene structure preservation. In experiments on Planar, 360°, and Full Spherical Panoramas, PanoFree demonstrates significant error reduction, improves global consistency, and boosts image quality without extra fine-tuning. Compared to existing methods, PanoFree is up to 5x more efficient in time and 3x more efficient in GPU memory usage, and maintains superior diversity of results (2x better in our user study). PanoFree offers a viable alternative to costly fine-tuning or the use of additional pre-trained models.

![image](https://github.com/user-attachments/assets/de188b8e-739f-4da7-bda9-c57add82ba20)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.02157) | [⌨️ Code](https://github.com/zxcvfd13502/PanoFree) | [🌐 Project Page](https://panofree.github.io/)

#### <summary>LEGO: Self-Supervised Representation Learning for Scene Text Images
Authors: Yujin Ren, Jiaxin Zhang, Lianwen Jin
<details span>
<summary><b>Abstract</b></summary>
In recent years, significant progress has been made in scene text recognition by data-driven methods. However, due to the scarcity of annotated real-world data, the training of these methods predominantly relies on synthetic data. The distribution gap between synthetic and real data constrains the further performance improvement of these methods in real-world applications. To tackle this problem, a highly promising approach is to utilize massive amounts of unlabeled real data for self-supervised training, which has been widely proven effective in many NLP and CV tasks. Nevertheless, generic self-supervised methods are unsuitable for scene text images due to their sequential nature. To address this issue, we propose a Local Explicit and Global Order-aware self-supervised representation learning method (LEGO) that accounts for the characteristics of scene text images. Inspired by the human cognitive process of learning words, which involves spelling, reading, and writing, we propose three novel pre-text tasks for LEGO to model sequential, semantic, and structural features, respectively. The entire pre-training process is optimized by using a consistent Text Knowledge Codebook. Extensive experiments validate that LEGO outperforms previous scene text self-supervised methods. The recognizer incorporated with our pre-trained model achieves superior or comparable performance compared to state-of-the-art scene text recognition methods on six benchmarks. Furthermore, we demonstrate that LEGO can achieve superior performance in other text-related tasks.

![image](https://github.com/user-attachments/assets/760c3ceb-e727-42b9-89f6-2859f94861d5)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.02036) | [⌨️ Code] | [🌐 Project Page]


#### <summary>An Object is Worth 64x64 Pixels: Generating 3D Object via Image Diffusion
Authors: Xingguang Yan, Han-Hung Lee, Ziyu Wan, Angel X. Chang
<details span>
<summary><b>Abstract</b></summary>
We introduce a new approach for generating realistic 3D models with UV maps through a representation termed "Object Images." This approach encapsulates surface geometry, appearance, and patch structures within a 64x64 pixel image, effectively converting complex 3D shapes into a more manageable 2D format. By doing so, we address the challenges of both geometric and semantic irregularity inherent in polygonal meshes. This method allows us to use image generation models, such as Diffusion Transformers, directly for 3D shape generation. Evaluated on the ABO dataset, our generated shapes with patch structures achieve point cloud FID comparable to recent 3D generative models, while naturally supporting PBR material generation.

![image](https://github.com/user-attachments/assets/c4776857-8438-4191-922f-f2d59c9a6a8e)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.03178) | [⌨️ Code] | [🌐 Project Page](https://omages.github.io/)


#### <summary>Gaussian Mixture based Evidential Learning for Stereo Matching
Authors: Weide Liu, Xingxing Wang, Lu Wang, Jun Cheng, Fayao Liu, Xulei Yang
<details span>
<summary><b>Abstract</b></summary>
In this paper, we introduce a novel Gaussian mixture based evidential learning solution for robust stereo matching. Diverging from previous evidential deep learning approaches that rely on a single Gaussian distribution, our framework posits that individual image data adheres to a mixture-of-Gaussian distribution in stereo matching. This assumption yields more precise pixel-level predictions and more accurately mirrors the real-world image distribution. By further employing the inverse-Gamma distribution as an intermediary prior for each mixture component, our probabilistic model achieves improved depth estimation compared to its counterpart with the single Gaussian and effectively captures the model uncertainty, which enables a strong cross-domain generation ability. We evaluated our method for stereo matching by training the model using the Scene Flow dataset and testing it on KITTI 2015 and Middlebury 2014. The experiment results consistently show that our method brings improvements over the baseline methods in a trustworthy manner. Notably, our approach achieved new state-of-the-art results on both the in-domain validated data and the cross-domain datasets, demonstrating its effectiveness and robustness in stereo matching tasks.

![image](https://github.com/user-attachments/assets/e0dc220a-687c-4576-aed9-e6dbe2de8ab8)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.02796) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Cross-View Meets Diffusion: Aerial Image Synthesis with Geometry and Text Guidance
Authors: Ahmad Arrabi, Xiaohan Zhang, Waqas Sultan, Chen Chen, Safwan Wshah
<details span>
<summary><b>Abstract</b></summary>
Aerial imagery analysis is critical for many research fields. However, obtaining frequent high-quality aerial images is not always accessible due to its high effort and cost requirements. One solution is to use the Ground-to-Aerial (G2A) technique to synthesize aerial images from easily collectible ground images. However, G2A is rarely studied, because of its challenges, including but not limited to, the drastic view changes, occlusion, and range of visibility. In this paper, we present a novel Geometric Preserving Ground-to-Aerial (G2A) image synthesis (GPG2A) model that can generate realistic aerial images from ground images. GPG2A consists of two stages. The first stage predicts the Bird's Eye View (BEV) segmentation (referred to as the BEV layout map) from the ground image. The second stage synthesizes the aerial image from the predicted BEV layout map and text descriptions of the ground image. To train our model, we present a new multi-modal cross-view dataset, namely VIGORv2 which is built upon VIGOR with newly collected aerial images, maps, and text descriptions. Our extensive experiments illustrate that GPG2A synthesizes better geometry-preserved aerial images than existing models. We also present two applications, data augmentation for cross-view geo-localization and sketch-based region search, to further verify the effectiveness of our GPG2A. The code and data will be publicly available.

![image](https://github.com/user-attachments/assets/7f32ffeb-0b1f-4681-9296-019ca8d73da5)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.04224) | [⌨️ Code] | [🌐 Project Page]

#### <summary>RISurConv: Rotation Invariant Surface Attention-Augmented Convolutions for 3D Point Cloud Classification and Segmentation
>  *ECCV2024 oral*
> 
Authors: Zhiyuan Zhang, Licheng Yang, Zhiyu Xiang
<details span>
<summary><b>Abstract</b></summary>
Despite the progress on 3D point cloud deep learning, most prior works focus on learning features that are invariant to translation and point permutation, and very limited efforts have been devoted for rotation invariant property. Several recent studies achieve rotation invariance at the cost of lower accuracies. In this work, we close this gap by proposing a novel yet effective rotation invariant architecture for 3D point cloud classification and segmentation. Instead of traditional pointwise operations, we construct local triangle surfaces to capture more detailed surface structure, based on which we can extract highly expressive rotation invariant surface properties which are then integrated into an attention-augmented convolution operator named RISurConv to generate refined attention features via self-attention layers. Based on RISurConv we build an effective neural network for 3D point cloud analysis that is invariant to arbitrary rotations while maintaining high accuracy. We verify the performance on various benchmarks with supreme results obtained surpassing the previous state-of-the-art by a large margin. We achieve an overall accuracy of 96.0% (+4.7%) on ModelNet40, 93.1% (+12.8%) on ScanObjectNN, and class accuracies of 91.5% (+3.6%), 82.7% (+5.1%), and 78.5% (+9.2%) on the three categories of the FG3D dataset for the fine-grained classification task. Additionally, we achieve 81.5% (+1.0%) mIoU on ShapeNet for the segmentation task.

![image](https://github.com/user-attachments/assets/599aacb3-9edb-482a-976b-5d6ab13ae5f2)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.06110) | [⌨️ Code](https://github.com/cszyzhang/RISurConv) | [🌐 Project Page]

#### <summary>Sapiens: Foundation for Human Vision Models
>  *ECCV2024 oral*
> 
Authors: Rawal Khirodkar, Timur Bagautdinov, Julieta Martinez, Su Zhaoen, Austin James, Peter Selednik, Stuart Anderson, Shunsuke Saito
<details span>
<summary><b>Abstract</b></summary>
We present Sapiens, a family of models for four fundamental human-centric vision tasks - 2D pose estimation, body-part segmentation, depth estimation, and surface normal prediction. Our models natively support 1K high-resolution inference and are extremely easy to adapt for individual tasks by simply fine-tuning models pretrained on over 300 million in-the-wild human images. We observe that, given the same computational budget, self-supervised pretraining on a curated dataset of human images significantly boosts the performance for a diverse set of human-centric tasks. The resulting models exhibit remarkable generalization to in-the-wild data, even when labeled data is scarce or entirely synthetic. Our simple model design also brings scalability - model performance across tasks improves as we scale the number of parameters from 0.3 to 2 billion. Sapiens consistently surpasses existing baselines across various human-centric benchmarks. We achieve significant improvements over the prior state-of-the-art on Humans-5K (pose) by 7.6 mAP, Humans-2K (part-seg) by 17.1 mIoU, Hi4D (depth) by 22.4% relative RMSE, and THuman2 (normal) by 53.5% relative angular error.

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.12569)| [⌨️ Code](https://github.com/facebookresearch/sapiens) | [🌐 Project Page](https://about.meta.com/realitylabs/codecavatars/sapiens/)

#### <summary>Learning-based Multi-View Stereo: A Survey
>  *pic*

Authors: Fangjinhua Wang, Qingtian Zhu, Di Chang, Quankai Gao, Junlin Han, Tong Zhang, Richard Hartley, Marc Pollefeys
<details span>
<summary><b>Abstract</b></summary>
3D reconstruction aims to recover the dense 3D structure of a scene. It plays an essential role in various applications such as Augmented/Virtual Reality (AR/VR), autonomous driving and robotics. Leveraging multiple views of a scene captured from different viewpoints, Multi-View Stereo (MVS) algorithms synthesize a comprehensive 3D representation, enabling precise reconstruction in complex environments. Due to its efficiency and effectiveness, MVS has become a pivotal method for image-based 3D reconstruction. Recently, with the success of deep learning, many learning-based MVS methods have been proposed, achieving impressive performance against traditional methods. We categorize these learning-based methods as: depth map-based, voxel-based, NeRF-based, 3D Gaussian Splatting-based, and large feed-forward methods. Among these, we focus significantly on depth map-based methods, which are the main family of MVS due to their conciseness, flexibility and scalability. In this survey, we provide a comprehensive review of the literature at the time of this writing. We investigate these learning-based methods, summarize their performances on popular benchmarks, and discuss promising future research directions in this area.

![image](https://github.com/user-attachments/assets/a463ed35-cb4e-4c8f-9d15-ec46bf07275b)


</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.15235) | [⌨️ Code] | [🌐 Project Page]


#### <summary>3D Reconstruction with Spatial Memory
Authors: Hengyi Wang, Lourdes Agapito
<details span>
<summary><b>Abstract</b></summary>
We present Spann3R, a novel approach for dense 3D reconstruction from ordered or unordered image collections. Built on the DUSt3R paradigm, Spann3R uses a transformer-based architecture to directly regress pointmaps from images without any prior knowledge of the scene or camera parameters. Unlike DUSt3R, which predicts per image-pair pointmaps each expressed in its local coordinate frame, Spann3R can predict per-image pointmaps expressed in a global coordinate system, thus eliminating the need for optimization-based global alignment. The key idea of Spann3R is to manage an external spatial memory that learns to keep track of all previous relevant 3D information. Spann3R then queries this spatial memory to predict the 3D structure of the next frame in a global coordinate system. Taking advantage of DUSt3R's pre-trained weights, and further fine-tuning on a subset of datasets, Spann3R shows competitive performance and generalization ability on various unseen datasets and can process ordered image collections in real time.

![image](https://github.com/user-attachments/assets/d322c9c7-1b6f-4520-b82a-a4b6c2fa6c2b)

</details>

[📃 arXiv:2408](https://arxiv.org/pdf/2408.16061) | [⌨️ Code] | [🌐 Project Page](https://hengyiwang.github.io/projects/spanner)

#### <summary>Geometry-aware Feature Matching for Large-Scale Structure from Motion
>*combine the detector-free and detector-based method*

Authors: Gonglin Chen, Jinsen Wu, Haiwei Chen, Wenbin Teng, Zhiyuan Gao, Andrew Feng, Rongjun Qin, Yajie Zhao
<details span>
<summary><b>Abstract</b></summary>
Establishing consistent and dense correspondences across multiple images is crucial for Structure from Motion (SfM) systems. Significant view changes, such as air-to-ground with very sparse view overlap, pose an even greater challenge to the correspondence solvers. We present a novel optimization-based approach that significantly enhances existing feature matching methods by introducing geometry cues in addition to color cues. This helps fill gaps when there is less overlap in large-scale scenarios. Our method formulates geometric verification as an optimization problem, guiding feature matching within detector-free methods and using sparse correspondences from detector-based methods as anchor points. By enforcing geometric constraints via the Sampson Distance, our approach ensures that the denser correspondences from detector-free methods are geometrically consistent and more accurate. This hybrid strategy significantly improves correspondence density and accuracy, mitigates multi-view inconsistencies, and leads to notable advancements in camera pose accuracy and point cloud density. It outperforms state-of-the-art feature matching methods on benchmark datasets and enables feature matching in challenging extreme large-scale settings.

![image](https://github.com/user-attachments/assets/c306a8c5-5efe-4460-8253-658728d4bc43)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.02310) | [⌨️ Code] | [🌐 Project Page]




#### <summary>Towards Localizing Structural Elements: Merging Geometrical Detection with Semantic Verification in RGB-D Data
>*semantic SLAM*

Authors: Ali Tourani, Saad Ejaz, Hriday Bavle, Jose Luis Sanchez-Lopez, Holger Voos
<details span>
<summary><b>Abstract</b></summary>
RGB-D cameras supply rich and dense visual and spatial information for various robotics tasks such as scene understanding, map reconstruction, and localization. Integrating depth and visual information can aid robots in localization and element mapping, advancing applications like 3D scene graph generation and Visual Simultaneous Localization and Mapping (VSLAM). While point cloud data containing such information is primarily used for enhanced scene understanding, exploiting their potential to capture and represent rich semantic information has yet to be adequately targeted. This paper presents a real-time pipeline for localizing building components, including wall and ground surfaces, by integrating geometric calculations for pure 3D plane detection followed by validating their semantic category using point cloud data from RGB-D cameras. It has a parallel multi-thread architecture to precisely estimate poses and equations of all the planes detected in the environment, filters the ones forming the map structure using a panoptic segmentation validation, and keeps only the validated building components. Incorporating the proposed method into a VSLAM framework confirmed that constraining the map with the detected environment-driven semantic elements can improve scene understanding and map reconstruction accuracy. It can also ensure (re-)association of these detected components into a unified 3D scene graph, bridging the gap between geometric accuracy and semantic understanding. Additionally, the pipeline allows for the detection of potential higher-level structural entities, such as rooms, by identifying the relationships between building components based on their layout.

![image](https://github.com/user-attachments/assets/56e84a1f-0f62-4ed0-951a-0a768643c0b2)

</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.06625) | [⌨️ Code] | [🌐 Project Page]



#### <summary>Event-based Mosaicing Bundle Adjustment
>*event camera BA*

Authors: Shuang Guo, Guillermo Gallego
<details span>
<summary><b>Abstract</b></summary>
We tackle the problem of mosaicing bundle adjustment (i.e., simultaneous refinement of camera orientations and scene map) for a purely rotating event camera. We formulate the problem as a regularized non-linear least squares optimization. The objective function is defined using the linearized event generation model in the camera orientations and the panoramic gradient map of the scene. We show that this BA optimization has an exploitable block-diagonal sparsity structure, so that the problem can be solved efficiently. To the best of our knowledge, this is the first work to leverage such sparsity to speed up the optimization in the context of event-based cameras, without the need to convert events into image-like representations. We evaluate our method, called EMBA, on both synthetic and real-world datasets to show its effectiveness (50% photometric error decrease), yielding results of unprecedented quality. In addition, we demonstrate EMBA using high spatial resolution event cameras, yielding delicate panoramas in the wild, even without an initial map.

![image](https://github.com/user-attachments/assets/e8cc0a4b-df75-4c95-89ac-83d6b605973d)


</details>

[📃 arXiv:2409](https://arxiv.org/pdf/2409.07365) | [⌨️ Code](https://github.com/tub-rip/emba) | [🌐 Project Page]



#### <summary>Depth Pro: Sharp Monocular Metric Depth in Less Than a Second
>*predict focal length and mono-depth for metric mono-depth*

Authors: Aleksei Bochkovskii, Amaël Delaunoy, Hugo Germain, Marcel Santos, Yichao Zhou, Stephan R. Richter, Vladlen Koltun
<details span>
<summary><b>Abstract</b></summary>
We present a foundation model for zero-shot metric monocular depth estimation. Our model, Depth Pro, synthesizes high-resolution depth maps with unparalleled sharpness and high-frequency details. The predictions are metric, with absolute scale, without relying on the availability of metadata such as camera intrinsics. And the model is fast, producing a 2.25-megapixel depth map in 0.3 seconds on a standard GPU. These characteristics are enabled by a number of technical contributions, including an efficient multi-scale vision transformer for dense prediction, a training protocol that combines real and synthetic datasets to achieve high metric accuracy alongside fine boundary tracing, dedicated evaluation metrics for boundary accuracy in estimated depth maps, and state-of-the-art focal length estimation from a single image. Extensive experiments analyze specific design choices and demonstrate that Depth Pro outperforms prior work along multiple dimensions.

![image](https://github.com/user-attachments/assets/53081bed-b477-4046-bb2d-959e41f4e4cc)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.02073) | [⌨️ Code](https://github.com/apple/ml-depth-pro) | [🌐 Project Page]

#### <summary>LoGDesc: Local geometric features aggregation for robust point cloud registration
>*local geometric feature*

Authors: Karim Slimani, Brahim Tamadazte, Catherine Achard
<details span>
<summary><b>Abstract</b></summary>
This paper introduces a new hybrid descriptor for 3D point matching and point cloud registration, combining local geometrical properties and learning-based feature propagation for each point's neighborhood structure description. The proposed architecture first extracts prior geometrical information by computing each point's planarity, anisotropy, and omnivariance using a Principal Components Analysis (PCA). This prior information is completed by a descriptor based on the normal vectors estimated thanks to constructing a neighborhood based on triangles. The final geometrical descriptor is propagated between the points using local graph convolutions and attention mechanisms. The new feature extractor is evaluated on ModelNet40, Bunny Stanford dataset, KITTI and MVP (Multi-View Partial)-RG for point cloud registration and shows interesting results, particularly on noisy and low overlapping point clouds.

![image](https://github.com/user-attachments/assets/1844d483-e37d-4616-a145-b6af79e1bbf2)


</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.02420) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Generative Edge Detection with Stable Diffusion
> *Different ways of using the diffusion model*

Authors: Caixia Zhou, Yaping Huang, Mochu Xiang, Jiahui Ren, Haibin Ling, Jing Zhang
<details span>
<summary><b>Abstract</b></summary>
Edge detection is typically viewed as a pixel-level classification problem mainly addressed by discriminative methods. Recently, generative edge detection methods, especially diffusion model based solutions, are initialized in the edge detection task. Despite great potential, the retraining of task-specific designed modules and multi-step denoising inference limits their broader applications. Upon closer investigation, we speculate that part of the reason is the under-exploration of the rich discriminative information encoded in extensively pre-trained large models (\eg, stable diffusion models). Thus motivated, we propose a novel approach, named Generative Edge Detector (GED), by fully utilizing the potential of the pre-trained stable diffusion model. Our model can be trained and inferred efficiently without specific network design due to the rich high-level and low-level prior knowledge empowered by the pre-trained stable diffusion. Specifically, we propose to finetune the denoising U-Net and predict latent edge maps directly, by taking the latent image feature maps as input. Additionally, due to the subjectivity and ambiguity of the edges, we also incorporate the granularity of the edges into the denoising U-Net model as one of the conditions to achieve controllable and diverse predictions. Furthermore, we devise a granularity regularization to ensure the relative granularity relationship of the multiple predictions. We conduct extensive experiments on multiple datasets and achieve competitive performance (\eg, 0.870 and 0.880 in terms of ODS and OIS on the BSDS test dataset).

![image](https://github.com/user-attachments/assets/9e868c37-9447-4382-968a-347979f07203)
![image](https://github.com/user-attachments/assets/b6dd0156-c037-43a7-809a-61a57c788d27)


</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.03080) | [⌨️ Code] | [🌐 Project Page]

#### <summary>MonST3R: A Simple Approach for Estimating Geometry in the Presence of Motion
Authors: Junyi Zhang, Charles Herrmann, Junhwa Hur, Varun Jampani, Trevor Darrell, Forrester Cole, Deqing Sun, Ming-Hsuan Yang
<details span>
<summary><b>Abstract</b></summary>
Estimating geometry from dynamic scenes, where objects move and deform over time, remains a core challenge in computer vision. Current approaches often rely on multi-stage pipelines or global optimizations that decompose the problem into subtasks, like depth and flow, leading to complex systems prone to errors. In this paper, we present Motion DUSt3R (MonST3R), a novel geometry-first approach that directly estimates per-timestep geometry from dynamic scenes. Our key insight is that by simply estimating a pointmap for each timestep, we can effectively adapt DUST3R's representation, previously only used for static scenes, to dynamic scenes. However, this approach presents a significant challenge: the scarcity of suitable training data, namely dynamic, posed videos with depth labels. Despite this, we show that by posing the problem as a fine-tuning task, identifying several suitable datasets, and strategically training the model on this limited data, we can surprisingly enable the model to handle dynamics, even without an explicit motion representation. Based on this, we introduce new optimizations for several downstream video-specific tasks and demonstrate strong performance on video depth and camera pose estimation, outperforming prior work in terms of robustness and efficiency. Moreover, MonST3R shows promising results for primarily feed-forward 4D reconstruction.

![image](https://github.com/user-attachments/assets/ec97cc02-663f-4bf1-beed-8fc72414bfb3)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.03825) | [⌨️ Code](https://github.com/Junyi42/monst3r) | [🌐 Project Page](https://monst3r-project.github.io/)



#### <summary>ε-VAE: Denoising as Visual Decoding
>*offer a new perspective by proposing denoising as decoding*

Authors: Long Zhao, Sanghyun Woo, Ziyu Wan, Yandong Li, Han Zhang, Boqing Gong, Hartwig Adam, Xuhui Jia, Ting Liu
<details span>
<summary><b>Abstract</b></summary>
In generative modeling, tokenization simplifies complex data into compact, structured representations, creating a more efficient, learnable space. For high-dimensional visual data, it reduces redundancy and emphasizes key features for high-quality generation. Current visual tokenization methods rely on a traditional autoencoder framework, where the encoder compresses data into latent representations, and the decoder reconstructs the original input. In this work, we offer a new perspective by proposing denoising as decoding, shifting from single-step reconstruction to iterative refinement. Specifically, we replace the decoder with a diffusion process that iteratively refines noise to recover the original image, guided by the latents provided by the encoder. We evaluate our approach by assessing both reconstruction (rFID) and generation quality (FID), comparing it to state-of-the-art autoencoding approach. We hope this work offers new insights into integrating iterative generation and autoencoding for improved compression and generation.

![image](https://github.com/user-attachments/assets/1332afd3-c99d-4b22-82de-38ab43125298)

</details>

[📃 arXiv:2410](https://arxiv.org/pdf/2410.04081) | [⌨️ Code] | [🌐 Project Page]






#### <summary>
Authors: 
<details span>
<summary><b>Abstract</b></summary>


![image]()

</details>

[📃 arXiv:2410] | [⌨️ Code] | [🌐 Project Page]
