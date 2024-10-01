# Code supplement for the high risk autism phenotype paper
[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)
[![DOI](https://img.shields.io/badge/DOI-10.1101%2F2020.06.01.127688%20-informational)](https://doi.org/10.1101/2020.06.01.127688 )

This repository contains the main code used to process and analyse the data presented in the "Reproducible functional connectivity signature confers high risk of autism spectrum disorder in a subset of individuals" paper.

## Abstract
Discovery of predictive biomarkers is essential for understanding the neurobiological underpinnings of autism spectrum disorder (ASD), and improving diagnosis. Most progress has come from genetics, however, known genetic risk factors are either common, but associated with a low risk of diagnosis, or associated with a high risk but extremely uncommon. Resting-state functional connectivity analyses of individuals with ASD have established sensitivity of brain connectivity at the group level. Yet, the translation of these findings into robust markers of individual risk is hampered by extensive heterogeneity among ASD individuals. We analysed functional connectivity data from the Autism Brain Imaging Data Exchange (ABIDE) 1 and 2 datasets. We employed a transductive conformal prediction approach to identify a high risk autism signature based on functional connectivity patterns across multiple brain networks, and report a signature that confers a more than 7-fold increase in individual risk of ASD diagnosis, yet is still identified in an estimated 1 in 200 individuals in the general population. By limiting predictions to the most confidently identifiable subset of individuals we were able to increase the individual risk of our prediction by more than 3-fold over that of previously published imaging models. The identified high risk signature was characterised by underconnectivity of transmodal brain networks and generalised to independent data. Our results demonstrate the ability of a highly targeted prediction model to meaningfully decompose part of the heterogeneity of ASD, and could help better delineate the multitude of etiological pathways and behavioural symptoms that challenge our understanding of  ASD.

![Figure 4](fig4_model.png)

**Figure 4**. High risk signature is more common than genetic risk markers, confers higher risk than traditional imaging models, and meets the current machine learning state-of-the-art. Monogenic syndromes (green rhombs) and recurrent Copy Number Variants (pink triangles) confer high risk of ASD diagnosis (vertical axis), but are rare (horizontal axis). ASD related single nucleotide polymorphisms (yellow triangles) are very common, but confer negligible risk of ASD. Current imaging based predictive models (two pink circles) identify large portions of the general population with low risk of ASD. The high risk ASD signature (orange, black outline) identifies a small portion of the general population with elevated risk of ASD diagnosis, concordant with the estimated performance in the discovery data (orange plus signs), meeting the positive predictive value of 10 machine learning models combined (red circle), using a simple model.

## Scripts
- `Discovery_Conformal_Score.R` and `Validation_Conformal_Score.R` generate conformal scores for ASD and NTC individuals for each network, using bootstrapping, on the training (ABIDE 1) and validation (ABIDE 2) datasets respectively. Due to the large number of files generated by results on the training data, we share results for one of 100 bootstrap iterations as an example, in [Data](./Data). All results for the validation can be found in [20190524_Validation_Data](./20190524_Validation_Data).

- `Discovery_Read_Conformal_Scores.R` and `Validation_Read_Conformal_Scores.R` read the bootstrapped scores and compute combined scores (see paper for details). Results can be found in the respective directories.

Figures 2 supplementary, 4 and 7 can be fully reproduced using the code and data in the repo. We share a minimal version of the phenotypic data with only the necessary fileds required. We are grateful to the ABIDE consortium for making the data publicly available, more information on which can be found [here](https://fcon_1000.projects.nitrc.org/indi/abide/abide_I.html).
