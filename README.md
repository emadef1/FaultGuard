<div id="top"></div>
<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/emadef1/FaultGuard/tree/main">
    <img src="figures/logo.png" alt="Logo" width="150" height="150">
  </a>

  <h1 align="center">FaultGuard</h1>

  <p align="center">
    A Robust Framework for Resilient Fault Prediction in Smart Electrical Grids
    <br />
    <a href="https://arxiv.org/abs/2403.17494"><strong>Preprint Available »</strong></a>
    <br />
    <br />
    <a href="https://www.dei.unipd.it/persona/1373bd29c9ef0140e39d53ec9add14d2">Emad Efatinasab</a>
    ·
    <a href="https://www.math.unipd.it/~fmarchio/">Francesco Marchiori</a>
    ·
    <a href="https://www.math.unipd.it/~abrighen/">Alessandro Brighente</a>
    ·
    <a href="https://www.dei.unipd.it/persona/95DDDDA0C518D43822ADC0338BD38073">Mirco Rampazzo</a>
    ·
    <a href="https://www.math.unipd.it/~conti/">Mauro Conti</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary><strong>Table of Contents</strong></summary>
  <ol>
    <li>
      <a href="#abstract">Abstract</a>
    </li>
    <li>
      <a href="#usage">Usage</a>
    </li>
    <li>
      <a href="#models">Models</a>
    </li>
    <li>
      <a href="#baseline">Baseline</a>
    </li>
    <li>
      <a href="#attacks">Attacks</a>
    </li>
  </ol>
</details>

<div id="abstract"></div>

## 🧩 Abstract

>Ensuring the reliability of energy distribution networks is paramount for uninterrupted provision, a challenge further compounded by the introduction of new sustainable energy sources to the grid. Promptly addressing faults becomes critical for optimal energy consumption, quick restoration, and overall customer satisfaction in this evolving landscape. While Machine Learning approaches have been applied in smart grids for fault detection, the robustness and security of these systems need thorough exploration. The vulnerability of these systems to adversarial attacks underscores the need for a rigorous examination of their resilience and the implementation of robust security measures. To address these concerns, we introduce **FaultGuard**, a resilient framework for fault type and zone classification tasks. To ensure the security of our system, we employ an Anomaly Detection System (ADS) leveraging a novel Generative Adversarial Network training layer to identify attacks. Furthermore, we propose a low-complexity fault prediction model and an online adversarial training technique to enhance robustness. We comprehensively evaluate the framework's performance against various adversarial attacks using the publicly available IEEE13-AdvAttack dataset, a simulated dataset based on the IEEE-13 test node feeder. Our model outclasses the state-of-the-art with an accuracy of up to 0.958, and our ADS shows attack detection capabilities with an accuracy of up to 1.000. Moreover, we demonstrate how our novel training layers drastically increase performances across the whole framework, with a mean increase of 154.18% in ADS accuracy and 118.14% in model accuracy. With our research, we contribute to advancing reliable and secure smart grid applications, ensuring uninterrupted and secure energy delivery to consumers, especially in the face of challenges posed by integrating new sustainable energy sources.

<p align="right"><a href="#top">(back to top)</a></p>
<div id="usage"></div>

## ⚙️ Usage

To execute the attacks or to deploy the FaultGuard framework, start by cloning the repository:

```bash
git clone https://github.com/emadef1/FaultGuard.git
cd FaultGuard
```

Then, install the required Python packages by running:

```bash
pip install -r requirements.txt
```

<p align="right"><a href="#top">(back to top)</a></p>
<div id="models"></div>

## 🤖 Models

The architecture and training details of our GRU model are extensively expounded in Section 6.2 of the paper. Also, we have chosen to integrate classical machine learning algorithms such as XGBoost, Random Forest, and Decision Tree into our analysis for two primary reasons. Firstly, they serve as a baseline for comparison against our proposed models, enabling us to gauge the performance and efficacy of our approaches. Secondly, their inclusion underscores the significance of considering causality between data points in this task, highlighting the importance of leveraging advanced techniques to capture temporal dependencies within the data.


<p align="right"><a href="#top">(back to top)</a></p>
<div id="baseline"></div>

## 📊 Baseline

The obtained results are the following.

<center>

| **Model** | **Accuracy Fault Type** | **Accuracy Fault Zone** |
| --------- | :-----------------: | :-----------: |
| Ardito et al.     |        0.460 | 0.710     |
| Decision Tree      |        0.522 | 0.818     |
| Random Forest     |        0.543 | 0.831     |
| XGBoost |        0.560 | 0.841     |
| GRU |        0.604 | 0.958     |

</center>

<p align="right"><a href="#top">(back to top)</a></p>
<div id="attacks"></div>

## ⚔️ Attacks

Attacks are divided in different scenarios depending on the level of knowledge that the attacker has of the system.

<center>

| **Scenario**         | **Model** | **Data** |
| -------------------- | :-------: | :------: |
| **White Box**   |     ✅     |    ✅     |
| **Gray Box** |     ❌     |    ✅     |

</center>

<p align="right"><a href="#top">(back to top)</a></p>