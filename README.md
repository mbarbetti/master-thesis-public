[![made-with-latex](https://img.shields.io/badge/Made%20with-LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white)](https://www.latex-project.org/)
[![made-with-latex](https://img.shields.io/badge/Developed%20in-Overleaf-47a141?style=for-the-badge&logo=overleaf&logoColor=white)](https://it.overleaf.com/)

# Master Thesis

_Report number_ : [CERN-THESIS-2020-416](https://cds.cern.ch/record/2826210)

## Title

- [ENG] _Techniques for parametric simulation with deep neural networks and implementation for the LHCb experiment at CERN and its future upgrades_
- [ITA] _Tecniche di simulazione parametrica con reti neurali profonde e loro implementazione per l'esperimento LHCb al CERN e le sue future evoluzioni_

## Info

- **Supervisor:** Lucio Anderlini – <a href="mailto:lucio.anderlini@fi.infn.it">Lucio.Anderlini@fi.infn.it</a>
- **Co-supervisor:** Piegiulio Lenzi – <a href="mailto:piergiulio.lenzi@unifi.it">Piergiulio.Lenzi@unifi.it</a>
- **Graduation day:** June 12, 2020
- **Graduation score:** 110/110 _cum laude_

## Abstract

The LHCb experiment [[1](https://iopscience.iop.org/article/10.1088/1748-0221/3/08/S08005)] is one of the four detectors along the accelerator ring of the LargeHadron Collider (LHC) at CERN, and is designed for the study of heavy flavour physics in $pp$ collisions. Its primary goal is to look for indirect evidences of phenomena beyond the Standard Model in $CP$-violation and in rare decays of $b$- and $c$-hadrons.
The upgraded LHCb detector will get back to data taking in 2021 with the LHC Run 3, relying on an increase of its statistical power by at least an order of magnitude thanks to a fully software trigger system [[2](https://cds.cern.ch/record/1701361)]. This will allow to reach unprecedented accuracy as long as the Collaboration will be able to provide simulated samples as large. As a direct consequence, the production of such simulated samples will dominate the computing effort of the experiment [[3](https://cds.cern.ch/record/2310827)].
Reproducing accurately all the physics processes from the $pp$ collisions to the radiation-matter interactions within the detectors (the full simulation approach) is already now incapable to sustain the analysis demands of the various LHCb physics groups, and it is therefore necessary to adopt faster solutions to take full advantage of the upgraded detector [[3](https://cds.cern.ch/record/2310827)].
Ultra-fast simulation needs lower computing resources, renouncing to reproduce radiation-matter interactions and parameterizing directly the high-level response of the detector. The LHCb subsystems are based on various physics processes, also very different, that make building high-level parameterizations non-trivial: for example, the Particle Identification (PID) system combines information from RICH, calorimeter and muon detectors. This task can be carried out effectively by _Generative Adversarial Networks_ (GAN), a powerful class of deep learning algorithms able to reproduce highly faithful and diverse probability distributions thanks to a _generative model_ learned directly from data [[4](https://arxiv.org/abs/1406.2661)].

A large part of this thesis has concerned the development and implementation of state-of-the-art GAN algorithms [[5](https://arxiv.org/abs/1705.10743)] to provide the high-level response of the PID subsystems of LHCb. Following what done in Ref. [[6](https://arxiv.org/abs/1905.11825)] where GANs are successfully used to reproduce the outputs of the RICH system to traversing particles, I have generalized and formalized such results building generative models based on neural networks able to parameterize faithfully the high-level response of the Global PID system of LHCb.
These neural networks were trained over the calibration samples collected in 2016, in order to provide datasets composed by an unbiased selection of long-lived particles. I have modified the learning procedure to subtract statistically the residual background within the training data, and I have developed an independent algorithm capable to measure the quality of the generated samples. This strategy has allowed to build models capable not only to parameterize the high-level response of specific detectors (such as RICH detectors and muon system) to different particles traversing them, but also to reproduce the distributions of variables resulting from the combination of various detector responses (the Global PID system).
Therefore, given a few basic information such as the particle type, its kinematics and the total number of tracks within the detector, the trained models are able to synthesize accurately a wide range of probability distributions representing the response obtained from a single detector or from their combination.

The second important personal contribution is related to the design and development of the `mambah` framework, a Python package aimed to provide and manage user friendly data structures for High Energy Physics applications. All `mambah` objects were designed to take full advantage of a batch-grained framework, using the most modern softwares for parallel computing and exploiting efficiently hardware accelerators, such as GPUs or FPGAs.
Within the `mambah` project, I have dealt with the implementation of database management functions and to the design of a simulation framework based on `mambah` and named `mambah.sim`. The `mambah.sim` module allows to selectively generate particles with the kinematics set by the $pp$ collision and to propagate them within the detector defining custom parameterization functions for efficiencies and resolutions: I have developed the parameterization for thePID system of LHCb.
I have proved the correctness of the implemented models, showing the generalization capabilities of GANs in describing decay channels different from the one of training. Lastly, I have shown that the samples produced by `mambah.sim` are competitive with the full simulated ones, while ensuring a significant reduction of the computing cost.

### References

1. LHCb Collaboration, A. A. Alves Jr. _et al._, _The LHCb Detector at the LHC_, [JINST 3 (2008) S08005](https://iopscience.iop.org/article/10.1088/1748-0221/3/08/S08005)
2. LHCb Collaboration, _LHCb Trigger and Online Upgrade Technical Design Report_, [LHCB-TDR-016](https://cds.cern.ch/record/1701361), CERN, 2014
3. LHCb Collaboration, _Upgrade Software and Computing_, [LHCB-TDR-017](https://cds.cern.ch/record/2310827), CERN, 2018
4. I. J. Goodfellow _et al._, _Generative Adversarial Networks_,
[arXiv:1406.2661](https://arxiv.org/abs/1406.2661)
5. M. G. Bellemare _et al._, _The Cramer Distance as a Solution to Biased Wasserstein Gradients_,
[arXiv:1705.10743](https://arxiv.org/abs/1705.10743)
6. A. Maevskiy _et al._, _Fast Data-Driven Simulation of Cherenkov Detectors Using Generative Adversarial Networks_,
[arXiv:1905.11825](https://arxiv.org/abs/1905.11825)

## Cite me

Are you referring to my research project? Please cite me!

> M. Barbetti, **Techniques for parametric simulation with deep neural networks and implementation for the LHCb experiment at CERN and its future upgrades**, Master's thesis, University of Florence, 2020

```bibtex
@mastersthesis{Barbetti:2826210,
      author = "Barbetti, Matteo",
      title  = "{Techniques for parametric simulation with deep neural
                networks and implementation for the LHCb experiment at CERN
                and its future upgrades}",
      school = "University of Florence",
      year   = "2020",
      url    = "https://cds.cern.ch/record/2826210",
}
```
