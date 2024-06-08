# AwesomeGaussian


<br>

[Surface](#Surface) | [Sparse View](#Sparse-View) | [Noisy Poses](#Noisy-Poses) | [Structured](#Structured) | [Large Scale](#Large-Scale) | [Generalizable](#Generalizable) | [High Frequency Details](#High-Frequency-Details) | [Others](#Others) 

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

[📃 arXiv:2405](https://arxiv.org/pdf/2405.17176) | [⌨️ Code] | [🌐 Project Page]



#### <summary>RaDe-GS: Rasterizing Depth in Gaussian Splatting
Authors: Baowen Zhang, Chuan Fang, Rakesh Shrestha, Yixun Liang, Xiaoxiao Long, Ping Tan
<details span>
<summary><b>Abstract</b></summary>
Gaussian Splatting (GS) has proven to be highly effective in novel view synthesis, achieving high-quality and real-time rendering. However, its potential for reconstructing detailed 3D shapes has not been fully explored. Existing methods often suffer from limited shape accuracy due to the discrete and unstructured nature of Gaussian splats, which complicates the shape extraction. While recent techniques like 2D GS have attempted to improve shape reconstruction, they often reformulate the Gaussian primitives in ways that reduce both rendering quality and computational efficiency. To address these problems, our work introduces a rasterized approach to render the depth maps and surface normal maps of general 3D Gaussian splats. Our method not only significantly enhances shape reconstruction accuracy but also maintains the computational efficiency intrinsic to Gaussian Splatting. Our approach achieves a Chamfer distance error comparable to NeuraLangelo on the DTU dataset and similar training and rendering time as traditional Gaussian Splatting on the Tanks & Temples dataset. Our method is a significant advancement in Gaussian Splatting and can be directly integrated into existing Gaussian Splatting-based methods.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/86c35cf2-d3b7-4e10-a4fd-26e7e0ed47c5)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.01467) | [⌨️ Code](https://github.com/BaowenZ/RaDe-GS) | [🌐 Project Page](https://baowenz.github.io/radegs/)



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


#### <summary>3D-HGS: 3D Half-Gaussian Splatting
Authors: Haolin Li, Jinyang Liu, Mario Sznaier, Octavia Camps
<details span>
<summary><b>Abstract</b></summary>
Photo-realistic 3D Reconstruction is a fundamental problem in 3D computer vision. This domain has seen considerable advancements owing to the advent of recent neural rendering techniques. These techniques predominantly aim to focus on learning volumetric representations of 3D scenes and refining these representations via loss functions derived from rendering. Among these, 3D Gaussian Splatting (3D-GS) has emerged as a significant method, surpassing Neural Radiance Fields (NeRFs). 3D-GS uses parameterized 3D Gaussians for modeling both spatial locations and color information, combined with a tile-based fast rendering technique. Despite its superior rendering performance and speed, the use of 3D Gaussian kernels has inherent limitations in accurately representing discontinuous functions, notably at edges and corners for shape discontinuities, and across varying textures for color discontinuities. To address this problem, we propose to employ 3D Half-Gaussian (3D-HGS) kernels, which can be used as a plug-and-play kernel. Our experiments demonstrate their capability to improve the performance of current 3D-GS related methods and achieve state-of-the-art rendering performance on various datasets without compromising rendering speed.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/e737cfb0-2afd-4f05-9b6e-73cdcfa86c42)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02720) | [⌨️ Code] | [🌐 Project Page]


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

[📃 arXiv:2405](https://repo-sam.inria.fr/fungraph/hierarchical-3d-gaussians/hierarchical-3d-gaussians_low.pdf) | [⌨️ Code] | [🌐 Project Page](https://repo-sam.inria.fr/fungraph/hierarchical-3d-gaussians/)




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

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16923) | [⌨️ Code] | [🌐 Project Page](https://saliteta.github.io/SA-GS/)



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



<br>
<br>



## Generalizable

#### <summary>pixelSplat: 3D Gaussian Splats from Image Pairs for Scalable Generalizable 3D Reconstruction

Authors: David Charatan, Sizhe Li, Andrea Tagliasacchi, Vincent Sitzmann
<details span>
<summary><b>Abstract</b></summary>
We introduce pixelSplat, a feed-forward model that learns to reconstruct 3D radiance fields parameterized by 3D Gaussian primitives from pairs of images. Our model features real-time and memory-efficient rendering for scalable training as well as fast 3D reconstruction at inference time. To overcome local minima inherent to sparse and locally supported representations, we predict a dense probability distribution over 3D and sample Gaussian means from that probability distribution. We make this sampling operation differentiable via a reparameterization trick, allowing us to back-propagate gradients through the Gaussian splatting representation. We benchmark our method on wide-baseline novel view synthesis on the real-world RealEstate10k and ACID datasets, where we outperform state-of-the-art light field transformers and accelerate rendering by 2.5 orders of magnitude while reconstructing an interpretable and editable 3D radiance field.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d46225eb-97c6-44ab-a96b-10ca2754fa56)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.12337) | [⌨️ Code](https://github.com/dcharatan/pixelsplat) | [🌐 Project Page](https://davidcharatan.com/pixelsplat/)


#### <summary>MVSplat: Efficient 3D Gaussian Splatting from Sparse Multi-View Images
Authors: Yuedong Chen, Haofei Xu, Chuanxia Zheng, Bohan Zhuang, Marc Pollefeys, Andreas Geiger, Tat-Jen Cham, Jianfei Cai
<details span>
<summary><b>Abstract</b></summary>
We propose MVSplat, an efficient feed-forward 3D Gaussian Splatting model learned from sparse multi-view images. To accurately localize the Gaussian centers, we propose to build a cost volume representation via plane sweeping in the 3D space, where the cross-view feature similarities stored in the cost volume can provide valuable geometry cues to the estimation of depth. We learn the Gaussian primitives' opacities, covariances, and spherical harmonics coefficients jointly with the Gaussian centers while only relying on photometric supervision. We demonstrate the importance of the cost volume representation in learning feed-forward Gaussian Splatting models via extensive experimental evaluations. On the large-scale RealEstate10K and ACID benchmarks, our model achieves state-of-the-art performance with the fastest feed-forward inference speed (22 fps). Compared to the latest state-of-the-art method pixelSplat, our model uses 10× fewer parameters and infers more than 2× faster while providing higher appearance and geometry quality as well as better cross-dataset generalization.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/5f4ec424-1dcd-4747-a2a2-bc0395f412d4)

</details>

[📃 arXiv:2403](https://arxiv.org/pdf/2403.14627) | [⌨️ Code](https://github.com/donydchen/mvsplat?tab=readme-ov-file) | [🌐 Project Page](https://donydchen.github.io/mvsplat/)

#### <summary>Fast Generalizable Gaussian Splatting Reconstruction from Multi-View Stereo
Authors: Tianqi Liu, Guangcong Wang, Shoukang Hu, Liao Shen, Xinyi Ye, Yuhang Zang, Zhiguo Cao, Wei Li, Ziwei Liu
<details span>
<summary><b>Abstract</b></summary>
We present MVSGaussian, a new generalizable 3D Gaussian representation approach derived from Multi-View Stereo (MVS) that can efficiently reconstruct unseen scenes. Specifically, 1) we leverage MVS to encode geometry-aware Gaussian representations and decode them into Gaussian parameters. 2) To further enhance performance, we propose a hybrid Gaussian rendering that integrates an efficient volume rendering design for novel view synthesis. 3) To support fast fine-tuning for specific scenes, we introduce a multi-view geometric consistent aggregation strategy to effectively aggregate the point clouds generated by the generalizable model, serving as the initialization for per-scene optimization. Compared with previous generalizable NeRF-based methods, which typically require minutes of fine-tuning and seconds of rendering per image, MVSGaussian achieves real-time rendering with better synthesis quality for each scene. Compared with the vanilla 3D-GS, MVSGaussian achieves better view synthesis with less training computational cost. Extensive experiments on DTU, Real Forward-facing, NeRF Synthetic, and Tanks and Temples datasets validate that MVSGaussian attains state-of-the-art performance with convincing generalizability, real-time rendering speed, and fast per-scene optimization.



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




#### <summary>Multi-Scale 3D Gaussian Splatting for Anti-Aliased Rendering
Authors: Zhiwen Yan, Weng Fei Low, Yu Chen, Gim Hee Lee
<details span>
<summary><b>Abstract</b></summary>
3D Gaussians have recently emerged as a highly efficient representation for 3D reconstruction and rendering. Despite its high rendering quality and speed at high resolutions, they both deteriorate drastically when rendered at lower resolutions or from far away camera position. During low resolution or far away rendering, the pixel size of the image can fall below the Nyquist frequency compared to the screen size of each splatted 3D Gaussian and leads to aliasing effect. The rendering is also drastically slowed down by the sequential alpha blending of more splatted Gaussians per pixel. To address these issues, we propose a multi-scale 3D Gaussian splatting algorithm, which maintains Gaussians at different scales to represent the same scene. Higher-resolution images are rendered with more small Gaussians, and lower-resolution images are rendered with fewer larger Gaussians. With similar training time, our algorithm can achieve 13\%-66\% PSNR and 160\%-2400\% rendering speed improvement at 4×-128× scale rendering on Mip-NeRF360 dataset compared to the single scale 3D Gaussian splatting.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9c38b2b3-d229-4c27-9f85-22a0390b2a7b)


</details>

[📃 arXiv:2311](https://arxiv.org/pdf/2311.17089) | [⌨️ Code](https://github.com/JokerYan/MS-GS/tree/main) | [🌐 Project Page](https://jokeryan.github.io/projects/ms-gs/)


#### <summary>COLMAP-Free 3D Gaussian Splatting
Authors: Yang Fu, Sifei Liu, Amey Kulkarni, Jan Kautz, Alexei A. Efros, Xiaolong Wang
<details span>
<summary><b>Abstract</b></summary>
While neural rendering has led to impressive advances in scene reconstruction and novel view synthesis, it relies heavily on accurately pre-computed camera poses. To relax this constraint, multiple efforts have been made to train Neural Radiance Fields (NeRFs) without pre-processed camera poses. However, the implicit representations of NeRFs provide extra challenges to optimize the 3D structure and camera poses at the same time. On the other hand, the recently proposed 3D Gaussian Splatting provides new opportunities given its explicit point cloud representations. This paper leverages both the explicit geometric representation and the continuity of the input video stream to perform novel view synthesis without any SfM preprocessing. We process the input frames in a sequential manner and progressively grow the 3D Gaussians set by taking one input frame at a time, without the need to pre-compute the camera poses. Our method significantly improves over previous approaches in view synthesis and camera pose estimation under large motion changes.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9c38b2b3-d229-4c27-9f85-22a0390b2a7b)


</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.07504) | [⌨️ Code] | [🌐 Project Page]



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



#### <summary>GeoGaussian: Geometry-aware Gaussian Splatting for Scene Rendering
Authors: Yanyan Li, Chenyu Lyu, Yan Di, Guangyao Zhai, Gim Hee Lee, Federico Tombari
<details span>
<summary><b>Abstract</b></summary>
During the Gaussian Splatting optimization process, the scene’s geometry can gradually deteriorate if its structure is not deliberately preserved, especially in non-textured regions such as walls, ceilings, and furniture surfaces. This degradation significantly affects the rendering quality of novel views that deviate significantly from the viewpoints in the training data. To mitigate this issue, we propose a novel approach called GeoGaussian. Based on the smoothly connected areas observed from point clouds, this method introduces a novel pipeline to initialize thin Gaussians aligned with the surfaces, where the characteristic can be transferred to new generations through a carefully designed densification strategy. Finally, the pipeline ensures that the scene’s geometry and texture are maintained through constrained optimization processes with explicit geometry constraints. Benefiting from the proposed architecture, the generative ability of 3D Gaussians is enhanced, especially in structured regions. Our proposed pipeline achieves state-of-the-art performance in novel view synthesis and geometric reconstruction, as evaluated qualitatively and quantitatively on public datasets.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/9cd2a10a-5286-4b78-9b68-f107136cae73)


</details>


[📃 arXiv:2403](https://arxiv.org/pdf/2403.11324) | [⌨️ Code](https://github.com/yanyan-li/GeoGaussian) | [🌐 Project Page](https://yanyan-li.github.io/project/gs/geogaussian)


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


#### <summary>RTG-SLAM: Real-time 3D Reconstruction at Scale using Gaussian Splatting
Authors: Zhexi Peng, Tianjia Shao, Yong Liu, Jingke Zhou, Yin Yang, Jingdong Wang, Kun Zhou
<details span>
<summary><b>Abstract</b></summary>
We present Real-time Gaussian SLAM (RTG-SLAM), a real-time 3D reconstruction system with an RGBD camera for large-scale environments using Gaussian splatting. The system features a compact Gaussian representation and a highly efficient on-the-fly Gaussian optimization scheme. We force each Gaussian to be either opaque or nearly transparent, with the opaque ones fitting the surface and dominant colors, and transparent ones fitting residual colors. By rendering depth in a different way from color rendering, we let a single opaque Gaussian well fit a local surface region without the need of multiple overlapping Gaussians, hence largely reducing the memory and computation cost. For on-the-fly Gaussian optimization, we explicitly add Gaussians for three types of pixels per frame: newly observed, with large color errors, and with large depth errors. We also categorize all Gaussians into stable and unstable ones, where the stable Gaussians are expected to well fit previously observed RGBD images and otherwise unstable. We only optimize the unstable Gaussians and only render the pixels occupied by unstable Gaussians. In this way, both the number of Gaussians to be optimized and pixels to be rendered are largely reduced, and the optimization can be done in real time. We show real-time reconstructions of a variety of large scenes. Compared with the state-of-the-art NeRF-based RGBD SLAM, our system achieves comparable high-quality reconstruction but with around twice the speed and half the memory cost, and shows superior performance in the realism of novel view synthesis and camera tracking accuracy.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ae306778-dc5a-40e2-99e6-fe8d8b827d42)


</details>

[📃 arXiv:2404](https://arxiv.org/pdf/2404.19706) | [⌨️ Code] | [🌐 Project Page]


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


#### <summary>MotionGS : Compact Gaussian Splatting SLAM by Motion Filter
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

#### <summary>Monocular Gaussian SLAM with Language Extended Loop Closure
Authors: Tian Lan, Qinwei Lin, Haoqian Wang
<details span>
<summary><b>Abstract</b></summary>
Recently,3DGaussianSplattinghasshowngreatpotentialin visual Simultaneous Localization And Mapping (SLAM). Existing methods have achieved encouraging results on RGB-D SLAM, but studies of the monocular case are still scarce. Moreover, they also fail to correct drift errors due to the lack of loop closure and global optimization. In this paper, we present MG-SLAM, a monocular Gaussian SLAM with a language-extended loop closure module capable of performing drift-corrected tracking and high-fidelity reconstruction while achieving a high-level understanding of the environment. Our key idea is to represent the global map as 3D Gaussian and use it to guide the estimation of the scene geometry, thus mitigating the efforts of missing depth information. Further, an additional language-extended loop closure module which is based on CLIP feature is designed to continually perform global optimization to correct drift errors accumulated as the system runs. Our system shows promising results on multiple challenging datasets in both tracking and mapping and even surpasses some existing RGB-D methods.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/ec122248-f518-461a-b38d-63b3ec8162a6)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.13748) | [⌨️ Code] | [🌐 Project Page]



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



#### <summary>Splat-SLAM: Globally Optimized RGB-only SLAM with 3D Gaussians
Authors: Xiangyu Sun, Joo Chan Lee, Daniel Rho, Jong Hwan Ko, Usman Ali, Eunbyung Park
<details span>
<summary><b>Abstract</b></summary>
3D Gaussian Splatting has emerged as a powerful representation of geometry and appearance for RGB-only dense Simultaneous Localization and Mapping (SLAM), as it provides a compact dense map representation while enabling efficient and high-quality map rendering. However, existing methods show significantly worse reconstruction quality than competing methods using other 3D representations, e.g. neural points clouds, since they either do not employ global map and pose optimization or make use of monocular depth. In response, we propose the first RGB-only SLAM system with a dense 3D Gaussian map representation that utilizes all benefits of globally optimized tracking by adapting dynamically to keyframe pose and depth updates by actively deforming the 3D Gaussian map. Moreover, we find that refining the depth updates in inaccurate areas with a monocular depth estimator further improves the accuracy of the 3D reconstruction. Our experiments on the Replica, TUM-RGBD, and ScanNet datasets indicate the effectiveness of globally optimized 3D Gaussians, as the approach achieves superior or on par performance with existing RGB-only SLAM methods methods in tracking, mapping and rendering accuracy while yielding small map sizes and fast runtimes.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/223b9a44-1b78-48c1-a5a8-112e2695e2cb)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.16544) | [⌨️ Code](https://github.com/eriksandstroem/Splat-SLAM) | [🌐 Project Page]


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


#### <summary>3D Neural Edge Reconstruction
Authors: Lei Li, Songyou Peng, Zehao Yu, Shaohui Liu, Rémi Pautrat, Xiaochuan Yin, Marc Pollefeys
<details span>
<summary><b>Abstract</b></summary>
Real-world objects and environments are predominantly composed of edge features, including straight lines and curves. Such edges are crucial elements for various applications, such as CAD modeling, surface meshing, lane mapping, etc. However, existing traditional methods only prioritize lines over curves for simplicity in geometric modeling. To this end, we introduce EMAP, a new method for learning 3D edge representations with a focus on both lines and curves. Our method implicitly encodes 3D edge distance and direction in Unsigned Distance Functions (UDF) from multi-view edge maps. On top of this neural representation, we propose an edge extraction algorithm that robustly abstracts parametric 3D edges from the inferred edge points and their directions. Comprehensive evaluations demonstrate that our method achieves better 3D edge reconstruction on multiple challenging datasets. We further show that our learned UDF field enhances neural surface reconstruction by capturing more details.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/b6566200-16c5-4765-bc3b-1453681f5f54)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.19295) | [⌨️ Code](https://github.com/cvg/EMAP) | [🌐 Project Page](https://neural-edge-map.github.io/)


#### <summary>LP-3DGS: Learning to Prune 3D Gaussian Splatting
Authors: Zhaoliang Zhang, Tianchen Song, Yongjae Lee, Li Yang, Cheng Peng, Rama Chellappa, Deliang Fan
<details span>
<summary><b>Abstract</b></summary>
Recently, 3D Gaussian Splatting (3DGS) has become one of the mainstream methodologies for novel view synthesis (NVS) due to its high quality and fast rendering speed. However, as a point-based scene representation, 3DGS potentially generates a large number of Gaussians to fit the scene, leading to high memory usage. Improvements that have been proposed require either an empirical and preset pruning ratio or importance score threshold to prune the point cloud. Such hyperparamter requires multiple rounds of training to optimize and achieve the maximum pruning ratio, while maintaining the rendering quality for each scene. In this work, we propose learning-to-prune 3DGS (LP-3DGS), where a trainable binary mask is applied to the importance score that can find optimal pruning ratio automatically. Instead of using the traditional straight-through estimator (STE) method to approximate the binary mask gradient, we redesign the masking function to leverage the Gumbel-Sigmoid method, making it differentiable and compatible with the existing training process of 3DGS. Extensive experiments have shown that LP-3DGS consistently produces a good balance that is both efficient and high quality.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/bc7f074e-7dd4-4abb-95dc-53fafad5d6af)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.18784) | [⌨️ Code] | [🌐 Project Page]


#### <summary>S3Gaussian: Self-Supervised Street Gaussians for Autonomous Driving
Authors: Nan Huang, Xiaobao Wei, Wenzhao Zheng, Pengju An, Ming Lu, Wei Zhan, Masayoshi Tomizuka, Kurt Keutzer, Shanghang Zhang
<details span>
<summary><b>Abstract</b></summary>
Photorealistic 3D reconstruction of street scenes is a critical technique for developing real-world simulators for autonomous driving. Despite the efficacy of Neural Radiance Fields (NeRF) for driving scenes, 3D Gaussian Splatting (3DGS) emerges as a promising direction due to its faster speed and more explicit representation. However, most existing street 3DGS methods require tracked 3D vehicle bounding boxes to decompose the static and dynamic elements for effective reconstruction, limiting their applications for in-the-wild scenarios. To facilitate efficient 3D scene reconstruction without costly annotations, we propose a self-supervised street Gaussian (S3Gaussian) method to decompose dynamic and static elements from 4D consistency. We represent each scene with 3D Gaussians to preserve the explicitness and further accompany them with a spatial-temporal field network to compactly model the 4D dynamics. We conduct extensive experiments on the challenging Waymo-Open dataset to evaluate the effectiveness of our method. Our S3Gaussian demonstrates the ability to decompose static and dynamic scenes and achieves the best performance without using 3D annotations.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/cd6040d0-1145-4b68-a204-5eb96a13fc71)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20323) | [⌨️ Code](https://github.com/nnanhuang/S3Gaussian/) | [🌐 Project Page](https://wzzheng.net/S3Gaussian/)


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


#### <summary>Structure Gaussian SLAM with Manhattan World Hypothesis
Authors: Shuhong Liu, Heng Zhou, Liuzhuozheng Li, Yun Liu, Tianchen Deng, Yiming Zhou, Mingrui Li
<details span>
<summary><b>Abstract</b></summary>
Gaussian SLAM systems have made significant advancements in improving the efficiency and fidelity of real-time reconstructions. However, these systems often encounter incomplete reconstructions in complex indoor environments, characterized by substantial holes due to unobserved geometry caused by obstacles or limited view angles. To address this challenge, we present Manhattan Gaussian SLAM (MG-SLAM), an RGB-D system that leverages the Manhattan World hypothesis to enhance geometric accuracy and completeness. By seamlessly integrating fused line segments derived from structured scenes, MG-SLAM ensures robust tracking in textureless indoor areas. Moreover, The extracted lines and planar surface assumption allow strategic interpolation of new Gaussians in regions of missing geometry, enabling efficient scene completion. Extensive experiments conducted on both synthetic and real-world scenes demonstrate that these advancements enable our method to achieve state-of-the-art performance, marking a substantial improvement in the capabilities of Gaussian SLAM systems.
 
![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/703df897-a955-4bac-b95e-dac8e2a3f317)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.20031) | [⌨️ Code] | [🌐 Project Page]



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

#### <summary>Event3DGS: Event-based 3D Gaussian Splatting for Fast Egomotion
Authors: Tianyi Xiong, Jiayi Wu, Botao He, Cornelia Fermuller, Yiannis Aloimonos, Heng Huang, Christopher A. Metzler
<details span>
<summary><b>Abstract</b></summary>
The recent emergence of 3D Gaussian splatting (3DGS) leverages the advantage of explicit point-based representations, which significantly improves the rendering speed and quality of novel-view synthesis. However, 3D radiance field rendering in environments with high-dynamic motion or challenging illumination condition remains problematic in real-world robotic tasks. The reason is that fast egomotion is prevalent real-world robotic tasks, which induces motion blur, leading to inaccuracies and artifacts in the reconstructed structure. To alleviate this problem, we propose Event3DGS, the first method that learns Gaussian Splatting solely from raw event streams. By exploiting the high temporal resolution of event cameras and explicit point-based representation, Event3DGS can reconstruct high-fidelity 3D structures solely from the event streams under fast egomotion. Our sparsity-aware sampling and progressive training approaches allow for better reconstruction quality and consistency. To further enhance the fidelity of appearance, we explicitly incorporate the motion blur formation process into a differentiable rasterizer, which is used with a limited set of blurred RGB images to refine the appearance. Extensive experiments on multiple datasets validate the superior rendering quality of Event3DGS compared with existing approaches, with over 95% lower training time and faster rendering speed in orders of magnitude.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/7a9eae92-d15b-4f6e-9682-4bdfbcb3c270)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.02972) | [⌨️ Code] | [🌐 Project Page]


#### <summary>Neural Surface Reconstruction from Sparse Views Using Epipolar Geometry
Authors: Kaichen Zhou
<details span>
<summary><b>Abstract</b></summary>
This paper addresses the challenge of reconstructing surfaces from sparse view inputs, where ambiguity and occlusions due to missing information pose significant hurdles. We present a novel approach, named EpiS, that incorporates Epipolar information into the reconstruction process. Existing methods in sparse-view neural surface learning have mainly focused on mean and variance considerations using cost volumes for feature extraction. In contrast, our method aggregates coarse information from the cost volume into Epipolar features extracted from multiple source views, enabling the generation of fine-grained Signal Distance Function (SDF)-aware features. Additionally, we employ an attention mechanism along the line dimension to facilitate feature fusion based on the SDF feature. Furthermore, to address the information gaps in sparse conditions, we integrate depth information from monocular depth estimation using global and local regularization techniques. The global regularization utilizes a triplet loss function, while the local regularization employs a derivative loss function. Extensive experiments demonstrate that our approach outperforms state-of-the-art methods, especially in cases with sparse and generalizable conditions.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/26ebd05c-de45-4012-82f3-8046009669f2)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.04301) | [⌨️ Code] | [🌐 Project Page]

#### <summary>Superpoint Gaussian Splatting for Real-Time High-Fidelity Dynamic Scene Reconstruction
Authors: Diwen Wan, Ruijie Lu, Gang Zeng
<details span>
<summary><b>Abstract</b></summary>
Rendering novel view images in dynamic scenes is a crucial yet challenging task. Current methods mainly utilize NeRF-based methods to represent the static scene and an additional time-variant MLP to model scene deformations, resulting in relatively low rendering quality as well as slow inference speed. To tackle these challenges, we propose a novel framework named Superpoint Gaussian Splatting (SP-GS). Specifically, our framework first employs explicit 3D Gaussians to reconstruct the scene and then clusters Gaussians with similar properties (e.g., rotation, translation, and location) into superpoints. Empowered by these superpoints, our method manages to extend 3D Gaussian splatting to dynamic scenes with only a slight increase in computational expense. Apart from achieving state-of-the-art visual quality and real-time rendering under high resolutions, the superpoint representation provides a stronger manipulation capability. Extensive experiments demonstrate the practicality and effectiveness of our approach on both synthetic and real-world datasets.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/d164cbfc-74bb-4a08-bc3a-d91e52dd6a68)


</details>

[📃 arXiv:2406](https://arxiv.org/pdf/2406.03697) | [⌨️ Code] | [🌐 Project Page](https://dnvtmf.github.io/SP_GS.github.io)




<br>
<br>


## Others, not Gaussian







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

#### <summary>NeuSurf: On-Surface Priors for Neural Surface Reconstruction from Sparse Input Views
Authors: Han Huang, Yulun Wu, Junsheng Zhou, Ge Gao, Ming Gu, Yu-Shen Liu
<details span>
<summary><b>Abstract</b></summary>
Recently, neural implicit functions have demonstrated remarkable results in the field of multi-view reconstruction. However, most existing methods are tailored for dense views and exhibit unsatisfactory performance when dealing with sparse views. Several latest methods have been proposed for generalizing implicit reconstruction to address the sparse view reconstruction task, but they still suffer from high training costs and are merely valid under carefully selected perspectives. In this paper, we propose a novel sparse view reconstruction framework that leverages on-surface priors to achieve highly faithful surface reconstruction. Specifically, we design several constraints on global geometry alignment and local geometry refinement for jointly optimizing coarse shapes and fine details. To achieve this, we train a neural network to learn a global implicit field from the on-surface points obtained from SfM and then leverage it as a coarse geometric constraint. To exploit local geometric consistency, we project on-surface points onto seen and unseen views, treating the consistent loss of projected features as a fine geometric constraint. The experimental results with DTU and BlendedMVS datasets in two prevalent sparse settings demonstrate significant improvements over the state-of-the-art methods.
 
![image](https://github.com/PAU1G3ORGE/AwosomeGaussian/assets/167790336/0c8516ad-c054-4d61-adc2-afc59b43ceb9)

 
</details>

[📃 arXiv:2312](https://arxiv.org/pdf/2312.13977.pdf) | [⌨️ Code](https://github.com/leonwu0108/NeuSurf) | [🌐 Project Page](https://alvin528.github.io/NeuSurf/)



#### <summary>Binary Opacity Grids: Capturing Fine Geometric Detail for Mesh-Based View Synthesis
Authors: Christian Reiser, Stephan Garbin, Pratul P. Srinivasan, Dor Verbin, Richard Szeliski, Ben Mildenhall, Jonathan T. Barron, Peter Hedman, Andreas Geiger
<details span>
<summary><b>Abstract</b></summary>
While surface-based view synthesis algorithms are appealing due to their low computational requirements, they often struggle to reproduce thin structures. In contrast, more expensive methods that model the scene's geometry as a volumetric density field (e.g. NeRF) excel at reconstructing fine geometric detail. However, density fields often represent geometry in a "fuzzy" manner, which hinders exact localization of the surface. In this work, we modify density fields to encourage them to converge towards surfaces, without compromising their ability to reconstruct thin structures. First, we employ a discrete opacity grid representation instead of a continuous density field, which allows opacity values to discontinuously transition from zero to one at the surface. Second, we anti-alias by casting multiple rays per pixel, which allows occlusion boundaries and subpixel structures to be modelled without using semi-transparent voxels. Third, we minimize the binary entropy of the opacity values, which facilitates the extraction of surface geometry by encouraging opacity values to binarize towards the end of training. Lastly, we develop a fusion-based meshing strategy followed by mesh simplification and appearance model fitting. The compact meshes produced by our model can be rendered in real-time on mobile devices and achieve significantly higher view synthesis quality compared to existing mesh-based approaches.


</details>

[📃 arXiv:2402](https://arxiv.org/pdf/2402.12377) | [⌨️ Code] | [🌐 Project Page](https://binary-opacity-grid.github.io/)



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


#### <summary>Aerial-NeRF: Adaptive Spatial Partitioning and Sampling for Large-Scale Aerial Rendering
Authors: Xiaohan Zhang, Yukui Qiu, Zhenyu Sun, Qi Liu
<details span>
<summary><b>Abstract</b></summary>
Recent progress in large-scale scene rendering has yielded Neural Radiance Fields (NeRF)-based models with an impressive ability to synthesize scenes across small objects and indoor scenes. Nevertheless, extending this idea to large-scale aerial rendering poses two critical problems. Firstly, a single NeRF cannot render the entire scene with high-precision for complex large-scale aerial datasets since the sampling range along each view ray is insufficient to cover buildings adequately. Secondly, traditional NeRFs are infeasible to train on one GPU to enable interactive fly-throughs for modeling massive images. Instead, existing methods typically separate the whole scene into multiple regions and train a NeRF on each region, which are unaccustomed to different flight trajectories and difficult to achieve fast rendering. To that end, we propose Aerial-NeRF with three innovative modifications for jointly adapting NeRF in large-scale aerial rendering: (1) Designing an adaptive spatial partitioning and selection method based on drones' poses to adapt different flight trajectories; (2) Using similarity of poses instead of (expert) network for rendering speedup to determine which region a new viewpoint belongs to; (3) Developing an adaptive sampling approach for rendering performance improvement to cover the entire buildings at different heights. Extensive experiments have conducted to verify the effectiveness and efficiency of Aerial-NeRF, and new state-of-the-art results have been achieved on two public large-scale aerial datasets and presented SCUTic dataset. Note that our model allows us to perform rendering over 4 times as fast as compared to multiple competitors.

![image](https://github.com/PAU1G3ORGE/AwesomeGaussian/assets/167790336/6bf1d383-7d7d-4395-9ed8-01690ae7065b)


</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.06214) | [⌨️ Code] | [🌐 Project Page]

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

#### <summary>NVS-Solver: Video Diffusion Model as Zero-Shot Novel View Synthesizer
Authors: Meng You, Zhiyu Zhu, Hui Liu, Junhui Hou
<details span>
<summary><b>Abstract</b></summary>
By harnessing the potent generative capabilities of pre-trained large video diffusion models, we propose NVS-Solver, a new novel view synthesis (NVS) paradigm that operates \textit{without} the need for training. NVS-Solver adaptively modulates the diffusion sampling process with the given views to enable the creation of remarkable visual experiences from single or multiple views of static scenes or monocular videos of dynamic scenes. Specifically, built upon our theoretical modeling, we iteratively modulate the score function with the given scene priors represented with warped input views to control the video diffusion process. Moreover, by theoretically exploring the boundary of the estimation error, we achieve the modulation in an adaptive fashion according to the view pose and the number of diffusion steps. Extensive evaluations on both static and dynamic scenes substantiate the significant superiority of our NVS-Solver over state-of-the-art methods both quantitatively and qualitatively.

</details>

[📃 arXiv:2405](https://arxiv.org/pdf/2405.15364) | [⌨️ Code](https://github.com/ZHU-Zhiyu/NVS_Solver) | [🌐 Project Page]

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




#### <summary>
Authors: 
<details span>
<summary><b>Abstract</b></summary>


![image]()

</details>

[📃 arXiv:2406] | [⌨️ Code] | [🌐 Project Page]
