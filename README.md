# Semantic Segmentation of Drone-Captured Aerial Images: Swiss Drone and Okutama Datasets

## Bachground and Objectives
On this project work, we are going to develop and evaluate deep learning models for semantic segmentation of drone-captured aerial images. Using the Swiss Drone and Okutama Drone datasets, we aim to accurately identify and classify multiple object classes in outdoor environments. The goal is to enhance automated scene understanding for applications such as environmental monitoring, agriculture, and safe drone navigation.

The dataset used in this project are from https://www.kaggle.com/datasets/aletbm/swiss-drone-and-okutama-drone-datasets which consists of two drone image collections: the Swiss Drone Dataset and the Okutama Drone Dataset. Both datasets provide pixel-wise hand-labeled segmentation masks with 10 distinct classes: 
1. background, 
2. outdoor structures, 
3. buildings, 
4. paved ground, 
5. non-paved ground, 
6. train tracks, 
7. plants, 
8. wheeled vehicles, 
9. water, and 
10. people.

## Model Implementation 
For segmentation, four different U-Net based architectures are employed as for comparative approaches:

1. Standard U-Net: A classic encoder-decoder convolutional network with symmetric skip connections, designed to capture both spatial context and fine details.
2. U-Net with Xception Backbone (Guna et al., 2022): This variant replaces the encoder with the Xception model, which utilizes depthwise separable convolutions.
3. VGG U-Net (Nawaz et al., 2021): Incorporates a VGG network as the encoder backbone.
4. AER U-Net (Jonnala et al., 2025): An advanced U-Net variant integrating attention mechanisms or enhanced residual connections.

## Result
In this project, we conducted experiments on aerial image segmentation using drone imagery retrieved from the Kaggle Drone Dataset. For the segmentation models, we implemented and evaluated several deep learning architectures based on relevant literature. Specifically, we explored the standard U-Net, U-Net Xception, VGG U-Net, and AER U-Net models. To assess their performance, we used the Dice coefficient as considered to be a common metric for segmentation quality. The results are summarized below:

| Model            | Dice Score |
|------------------|------------|
| U-Net | 0.7012 | 
| U-Net Xception | 0.7098 | 
| VGG U-Net | 0.6263 | 
| AER U-Net | 0.6964 | 

From the results, we observe that the U-Net Xception model achieved the highest Dice score, followed closely by the standard U-Net and AER U-Net. The VGG U-Net model showed relatively lower performance in comparison.

The model weights can be accessed on the /model_weights folder.

## References
1. Nawaz, A., Akram, U., Salam, A. A., Ali, A. R., Ur Rehman, A., & Zeb, J. (2021). VGG-UNET for brain tumor segmentation and ensemble model for survival prediction. 2021 International Conference on Robotics and Automation in Industry (ICRAI), 1–6. https://doi.org/10.1109/ICRAI54018.2021.9651367
2. Jonnala, N. S., Siraaj, S., Prastuti, Y., et al. (2025). AER U-Net: Attention-enhanced multi-scale residual U-Net structure for water body segmentation using Sentinel-2 satellite images. Scientific Reports, 15, 16099. https://doi.org/10.1038/s41598-025-99322-z
3. Guna, R. T. A., Rahul, K., & Sikha, O. K. (2022). U-NET Xception: A two-stage segmentation-classification model for COVID detection from lung CT scan images. In International Conference on Innovative Computing and Communications (pp. 335–343). Springer. https://doi.org/10.1007/978-3-031-19130-8_29
4. Speth, S., Gonçalves, A., Rigault, B., Suzuki, S., Bouazizi, M., Matsuo, Y., & Prendinger, H. (2022). Deep learning with RGB and thermal images onboard a drone for monitoring operations. Journal of Field Robotics, 1–29. https://doi.org/10.1002/rob.22082
