<p align="center">
  <img src="./images/Compass-PNG-Pic.png" alt="" width="55" height="55" />
</p>
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
  <a href="https://chuhaozhou99.github.io/Chuhao-Zhou/"><strong>Chuhao Zhou</strong></a><sup>1</sup>,
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
      <img src="./images/marslab.png" alt="MARS Lab Logo" width="100" align="right" />
      <b>Correspondence:</b> Jianfei Yang at <a href="mailto:jianfei.yang@ntu.edu.sg">jianfei.yang@ntu.edu.sg</a> &amp; Gen Li at <a href="mailto:gen.li@ntu.edu.sg">gen.li@ntu.edu.sg</a>
    </td>
  </tr>
</table>

---

## :gear: Method

<p align="center">
  <img src="./images/method.png" alt="CompassNet architecture" width="88%" />
</p>

**Overall architecture of CompassNet.** Given 3D point clouds of a scene and a human query, Uni3D and RoBERTa are applied to produce per-point features and text features. We then propose Instance-bounded Cross Injection (ICI), which enhances both region- and point-level representations through coarse-to-fine query interactions while preventing cross-object leakage of query semantics. Bi-level Contrastive Refinement (BCR) is further introduced to explicitly identify the functional regions that best match the query and provide additional supervision for highly ambiguous point-level affordances.

---

## :bar_chart: CompassAD Benchmark

<p align="center">
  <img src="./images/dataset.png" alt="CompassAD benchmark overview" width="88%" />
</p>

---

## :art: Qualitative Comparison

<p align="center">
  <img src="./images/qualitative.png" alt="Qualitative comparison on CompassAD" width="88%" />
</p>

---

## :robot: Real-World Robot Deployment

<p align="center">
  <img src="./images/robot.png" alt="Real-world robotic grasping" width="88%" />
</p>

---

## :sparkles: More Qualitative Results

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
