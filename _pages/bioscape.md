---
layout: archive
permalink: /bioscape/
author_profile: true
title: "BioSCape"
excerpt: "BioSCape"
---
AGU 2024
======

<iframe src="/images/AGU-2024-Poster.pdf" width="100%" height="600px">
    This browser does not support PDFs. Please <a href="/images/AGU-2024-Poster.pdf">download the PDF</a>.
</iframe>

**Please read below for more details on our motivation and methods.**

Background
======
* Global change drivers, such as invasion, are impacting biodiversity and ecosystem functioning.
* These threats require large scale conservation and management efforts. However, understanding impacts at large scales is hampered by the challenge of external validity of small-scale experiments and internal validity of large-scale observational data.
* Remote sensing expands scales of possibility for ecological understanding, but still carries the challenges associated with observational data for inferring causality. However, statistical approaches for causal inference allow us to better account for confounders and test the robustness of our results to varying assumptions.
* Here, we attempt to scale up causal ecological relationships by integrating remote sensing and causal inference to address a pressing global change problem: invasion.
* **We do so using the Greater Cape Floristic Region of South Africa as a case study, due to the significant threat the region faces from invasive alien trees and because we have access to data from the unprecedented biodiversity campaign conducted through NASA BioSCape.**

Additional Methods
======
**Unit of analysis:** We will test our hypotheses using 500x500-m2 regions as our samples. At this region size, we have >3000 samples across three study sites spanning the GCFR.
**Data layers:**
* **Invasive alien tree (IAT) presence and cover:** We are using reflectance data from AVIRIS-NG (380-2510 nm; 5-m spatial resolution) to predict invasion status based on *in situ* training data collected across our three study sites, which is possible due differences in reflectance between invasive trees and native species (e.g., due to differences in water use, productivity and functional traits). We are summarizing outcomes of this mapping effort at the region level as percent cover of each of our IAT taxa of interest (Pine, Wattle, Gum and Hakea).
* **Spectral diversity:** We are using reflectance data from AVIRIS-NG to calculate a metric of vegetation diversity, using the algorithm developed by LaLiberte et al., 2020, which partitions variance in reflectance into alpha, beta and gamma components. We use a community size of 25 x 25-m2 to partition our regions.
* **Canopy height:** We are using lidar data from LVIS (5-m spatial resolution) to summarize canopy height (RH98) across each of our regions. This value will inform a potential alternate pathway to diversity through which invasion might impact functioning (e.g., because of the different functional form, root depth, etc. of invasive and native species).
* **Ecosystem function:** We chose to measure evapotranspiration (ET) as our ecosystem function of interest due to relevance to local management which considers water use by IATs to be a major concern. We estimate ET from MOD16, which has been shown to predict ET well for the CFR (manuscript in prep, Rebelo et al.).
* **Environmental covariates:** We estimate a variety of environmental covariates at the region level to account for potential confounders. We created a Directed Acyclic Graph (DAG) to lay out our assumptions about the system and to select these variables, which include time since fire, elevation, topographic roughness, and climate, among others. These covariates are derived from a variety of satellite sources, including MODIS. 

**Statistical Approach for Causal Inference:** We build off Van Cleemput et al. 2024, which identifies challenges and opportunities for causal inference from remotely sensed data, by integrating the following steps into our analyses:
* We will account for potential bias arising from measurement error in our predictions of invasion status using multiple imputation.
* We will propagate uncertainty from our invasion mapping effort by creating a series of maps using the probability distribution of pixel predictions. We will run our analysis for each map in order to bound our estimates.
* We will account for observed confounders by weighting regions of varying invasion status by covariates to ensure balance across our “treatments”. We plan to use either Inverse Probability Weighting or a Group Centered Means approach.
* We will conduct a mediation analysis under the potential outcomes framework to identify direct and indirect effects of invasion, accounting for confounders across each of these pathways.
* We will conduct sensitivity tests to detect robustness of our results to unaccounted-for or unobserved confounding variables. 


  

