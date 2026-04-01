<h1 align="center">CompassAD: Intent-Driven 3D Affordance Grounding<br />in Functionally Competing Objects</h1>

<p align="center">
  <a href="#"><img src="https://img.shields.io/badge/arXiv-coming_soon-b31b1b?logo=arxiv&logoColor=white" alt="arXiv" /></a>
  <a href="#"><img src="https://img.shields.io/badge/Project_Page-TBD-2ea44f?logo=googlechrome&logoColor=white" alt="Project Page" /></a>
  <a href="https://github.com/Lorenzo-0-0/CompassAD-Intent-Driven-3D-Affordance-Grounding-in-Functionally-Competing-Objects"><img src="https://img.shields.io/badge/Code-GitHub-181717?logo=github&logoColor=white" alt="Code" /></a>
  <img src="https://komarev.com/ghpvc/?username=Lorenzo-0-0&repo=CompassAD-Intent-Driven-3D-Affordance-Grounding-in-Functionally-Competing-Objects&color=blueviolet" alt="Visitors" />
</p>

<p align="center">
  <strong>Jingliang Li</strong><sup>1</sup>,
  <a href="https://jiajindou.github.io/"><strong>Jindou Jia</strong></a><sup>1</sup>,
  <a href="https://morpheus-an.github.io/"><strong>Tuo An</strong></a><sup>1</sup>,
  <a href="https://marslab.tech/members/chuhao-zhou.html"><strong>Chuhao Zhou</strong></a><sup>1</sup>,
  <a href="https://xyc0212.github.io/"><strong>Xiangyu Chen</strong></a><sup>1</sup>,
  <a href="https://shanshilin.github.io/"><strong>Shilin Shan</strong></a><sup>1</sup>,
  <a href="https://ma-boyu.github.io/"><strong>Boyu Ma</strong></a><sup>1</sup>,
  <strong>Bofan Lyu</strong><sup>1</sup>,
  <a href="https://reagan1311.github.io/"><strong>Gen Li</strong></a><sup>1,†</sup>,
  <a href="https://marsyang.site/"><strong>Jianfei Yang</strong></a><sup>1,†</sup>
</p>

<p align="center">
  <sup>1</sup>MARS Lab, Nanyang Technological University, Singapore
</p>

<p align="center">
  <sup>†</sup>Corresponding Authors
</p>

<p align="center">
  <img src="./images/teaser.png" alt="CompassAD teaser figure" width="88%" />
</p>

<table align="center" width="88%">
  <tr>
    <td valign="top">
      <b>Abstract.</b> When told to "cut the apple," a robot must choose the knife over nearby scissors, despite both objects affording the same cutting function. In real-world scenes, multiple objects may share identical affordances, yet only one is appropriate under the given task context. We call such cases confusing pairs. However, existing 3D affordance methods largely sidestep this challenge by evaluating isolated single objects, often with explicit category names provided in the query. We formalize Multi-Object Affordance Grounding under Intent-Driven Instructions, a new 3D affordance setting that requires predicting a per-point affordance mask on the correct object within a cluttered multi-object point cloud, conditioned on implicit natural language intent. To study this problem, we construct CompassAD, the first benchmark centered on implicit intent in confusable multi-object scenes. It comprises 30 confusing object pairs spanning 16 affordance types, 6,422 scenes, and 88K+ query-answer pairs. Furthermore, we propose CompassNet, a framework that incorporates two dedicated modules tailored to this task. Instance-bounded Cross Injection (ICI) constrains language-geometry alignment within object boundaries to prevent cross-object semantic leakage. Bi-level Contrastive Refinement (BCR) enforces discrimination at both geometric-group and point levels, sharpening distinctions between target and confusable surfaces. Extensive experiments demonstrate state-of-the-art results on both seen and unseen queries, and deployment on a robotic manipulator confirms effective transfer to real-world grasping in confusing multi-object scenes.
      <br /><br />
      <img src="./images/marslab.png" alt="MARS Lab Logo" width="76" align="right" />
      <b>Correspondence:</b> Gen Li at <a href="mailto:gen.li@ntu.edu.sg">gen.li@ntu.edu.sg</a> &amp; Jianfei Yang at <a href="mailto:jianfei.yang@ntu.edu.sg">jianfei.yang@ntu.edu.sg</a>
    </td>
  </tr>
</table>

---

## Method

<p align="center">
  <img src="./images/method.png" alt="CompassNet architecture" width="88%" />
</p>

**Overall architecture of CompassNet.** Given 3D point clouds of a scene and a human query, Uni3D and RoBERTa are applied to produce per-point features and text features. We then propose Instance-bounded Cross Injection (ICI), which enhances both region- and point-level representations through coarse-to-fine query interactions while preventing cross-object leakage of query semantics. Bi-level Contrastive Refinement (BCR) is further introduced to explicitly identify the functional regions that best match the query and provide additional supervision for highly ambiguous point-level affordances.

---

## CompassAD Benchmark

<p align="center">
  <img src="./images/dataset.png" alt="CompassAD benchmark overview" width="88%" />
</p>

**Overview of the CompassAD benchmark.** (a) Affordance concept distribution. (b) Object category distribution. (c) Hierarchy of confusing pairs grouped by target confusing affordance types. (d) Source breakdown of the collected 3D object instances. (e) Confusion matrix between affordance and object categories, highlighting the many-to-many nature of real-world affordances.

---

## Main Results

**Table 1: Main results on CompassAD.** All methods are trained and evaluated with the same setup. **Best** in bold, <ins>second-best</ins> underlined. aIoU is the primary metric.

### Test-Seen

| Method | Venue | aIoU ↑ | AUC ↑ | SIM ↑ | MAE ↓ |
|:-------|:-----:|:------:|:-----:|:-----:|:-----:|
| 3D-SPS | CVPR 2022 | 5.23 | 64.7 | 0.158 | 0.096 |
| ReferTrans | NeurIPS 2021 | 5.81 | 66.3 | 0.171 | 0.093 |
| ReLA | CVPR 2023 | 6.47 | 68.9 | 0.193 | 0.091 |
| IAGNet | ICCV 2023 | 7.64 | 72.4 | 0.214 | 0.086 |
| GREAT | CVPR 2025 | 9.23 | 75.7 | 0.237 | 0.082 |
| PointRefer | CVPR 2024 | 10.52 | 79.3 | 0.260 | 0.079 |
| GLANCE | ICCV 2025 | <ins>14.18</ins> | <ins>87.5</ins> | <ins>0.296</ins> | <ins>0.077</ins> |
| **CompassNet (Ours)** | **—** | **18.20** | **89.2** | **0.368** | **0.061** |

### Test-Unseen

| Method | Venue | aIoU ↑ | AUC ↑ | SIM ↑ | MAE ↓ |
|:-------|:-----:|:------:|:-----:|:-----:|:-----:|
| 3D-SPS | CVPR 2022 | 4.12 | 61.8 | 0.136 | 0.099 |
| ReferTrans | NeurIPS 2021 | 4.58 | 63.5 | 0.148 | 0.096 |
| ReLA | CVPR 2023 | 5.06 | 65.7 | 0.167 | 0.094 |
| IAGNet | ICCV 2023 | 6.07 | 68.4 | 0.186 | 0.089 |
| GREAT | CVPR 2025 | 7.31 | 72.0 | 0.209 | 0.085 |
| PointRefer | CVPR 2024 | 8.47 | 75.8 | 0.232 | 0.082 |
| GLANCE | ICCV 2025 | <ins>11.82</ins> | <ins>85.2</ins> | <ins>0.268</ins> | <ins>0.075</ins> |
| **CompassNet (Ours)** | **—** | **15.36** | **87.4** | **0.339** | **0.059** |

---

## Qualitative Comparison

<p align="center">
  <img src="./images/qualitative.png" alt="Qualitative comparison on CompassAD" width="88%" />
</p>

**Qualitative comparison on CompassAD.** Each triplet shows ground truth (GT), CompassNet (Ours), and GLANCE (SOTA). **Left:** the same scene queried with different intents activates different objects/regions (chair seat *vs.* bed surface), illustrating query-dependent disambiguation. **Right:** diverse confusing pairs (knife *vs.* scissors, skateboard *vs.* surfboard, kettle *vs.* cup). Red denotes higher affordance probability.

---

## Real-World Robot Deployment

<p align="center">
  <img src="./images/robot.png" alt="Real-world robotic grasping" width="88%" />
</p>

**Real-world robotic grasping in confusing multi-object scenes.** Each row shows a different scenario. Real-world scene containing confusing objects and distractors. Affordance prediction from CompassNet on the reconstructed point cloud (red = high probability). Robotic grasp execution based on the predicted affordance. **Top:** given a cutting-related query, the model correctly identifies the knife over scissors. **Bottom:** given a hammering-related query, the model correctly identifies the hammer over distractors.

---

## More Qualitative Results

<p align="center">
  <img src="./images/more_results_1.png" alt="Additional qualitative results 1" width="70%" />
</p>

<p align="center">
  <img src="./images/more_results_2.png" alt="Additional qualitative results 2" width="70%" />
</p>

<p align="center">
  <img src="./images/more_results_3.png" alt="Additional qualitative results 3" width="70%" />
</p>

---

<p align="center">
  <b>Code and dataset will be released soon. Stay tuned!</b>
</p>
