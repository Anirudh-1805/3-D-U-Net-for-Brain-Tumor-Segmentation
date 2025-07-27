# 3D-U-Net-for-Brain-Tumor-Segmentation

For this project, I tackled a 3D image‑segmentation challenge:

1. **MRI Data Loading**  
   I loaded multi‑modal MRI scans (FLAIR, T1, T1‑Gd, T2) in NIfTI format using NiBabel and wrote utilities to visualize slices and verify data integrity.

2. **Patch Sampling**  
   Instead of feeding entire volumes, I implemented a patch extractor that randomly samples sub‑volumes enriched with tumor voxels—ensuring the network sees enough examples of abnormalities during training.

3. **Normalization**  
   I standardized each MRI channel per slice to zero mean and unit variance, which stabilized training and improved convergence.

4. **Built a 3D U‑Net**  
   From scratch in Keras, I assembled an encoder‑decoder architecture with skip connections. I used 3×3×3 convolutions, instance normalization, and dropout to prevent overfitting.

5. **Segmentation Loss & Metrics**  
   I implemented soft‑Dice loss to directly optimize for overlap, and wrote functions to compute Dice coefficient, sensitivity, and specificity on both patch‑level and whole‑volume predictions.

6. **Inference & Visualization**  
   After training on patches, I stitched predictions back into full 3D volumes to generate segmentation masks. I created overlay visualizations to compare my masks against ground‑truth.

---

**P.S.**
The code files in this repository were developed as part of the AI for Medical Diagnosis course on Coursera. All work was implemented and tested using the course’s provided backend environment.
