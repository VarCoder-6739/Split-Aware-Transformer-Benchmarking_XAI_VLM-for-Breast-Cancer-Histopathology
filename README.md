# Split-Aware Transformer Benchmarking and Vision-Language Interpretation for Breast Histopathology Classification 

## Completed study

- Conducted a comparative study of pretrained Vision Transformer (ViT), Swin Transformer, DeiT, and BEiT architectures for benign–malignant classification using the BreakHis breast histopathology dataset.
  
- Compared the model performance on patient-level 70:15:15 and 80:10:10 train-validation-test splits using accuracy,
precision, recall, f1-score, specificity, ROC-AUC and confusion-matrix analysis. Swin Transformer 97.16% accuracy shown under 70:15:15 split, DeiT 94.19% accuracy in 80:10:10 split.

- Generated Transformer attention and feature-activation maps to investigate model focus patterns and class-wise prediction errors across benign and malignant histopathology breast images.
  
- Integrated VLM model Gemma 4:12B via Ollama for qualitative vision-language interpretation of histopathology images and corresponding explainability maps.
