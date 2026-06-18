# Mitigating Demographic and Skin-Tone Bias in Melanoma Detection Models via Targeted Data Augmentation

## Project Overview
Melanoma is one of the most aggressive forms of skin cancer, yet it remains highly treatable with a 98.4% five-year survival rate when detected early in stages I-III. However, current prominent open-source dermatological datasets exhibit severe racial and demographic bias, with over 90% of images representing lighter skin tones. Consequently, machine learning models trained on this skewed data often learn unreliable shortcut features based on background skin types rather than isolating true biological malignant characteristics.

This research project introduces a structured data augmentation framework designed to artificially diversify training datasets to mitigate skin-tone and location bias, preventing convolutional neural networks (CNNs) from relying on shortcut learning features.

## Core Contributions
* **Bias Quantification:** Analyzing and quantifying systemic skin-tone, geographic, and clinic-origin imbalances across major skin cancer datasets.
* **Algorithmic Mitigation:** Proposing and testing targeted data augmentation and filtering methodologies to balance the feature maps.
* **Reproducible Pipeline:** Creating an accessible, data-level framework to help researchers develop racially inclusive diagnostic tools.

## Datasets Used
1. **ISIC 2024 Permissive Dataset (Training/Archive):** Consists of 217,000 clinical-resolution dermatological images across multiple global clinics. The permissive variant is strictly utilized to ensure non-commercial open-compliance.
2. **Stanford AIMI MIDAS Dataset (Evaluation/Validation):** Serving as a real-world mobile validation set, this clinical data features images captured via modern iPhones and iPads, with skin tones classified using the Fitzpatrick Scale (I-VI) and malignancy verified 100% via histopathology.

## Experimental Pipeline & Augmentations Tested
To disrupt the model's reliance on shortcut skin-tone patterns, the preprocessing pipeline applies distinct image-level filtering techniques:
* **Bilateral Filtering:** Utilized to smooth out irrelevant localized variations while preserving distinct structural boundaries of the lesion.
* **Color Removal / Grayscale Standardization:** Used to completely isolate morphological structures from underlying skin color properties.

## Repository Structure
* `/data_preprocessing`: Scripts for integrating metadata, parsing CSV fields, and cleaning transparency boundaries.
* `/models`: Base architecture setups for the ResNet50 neural network framework.
* `/notebooks`: Active Jupyter and Google Colab execution files.
