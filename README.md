# Split-Aware Transformer Benchmarking and Vision-Language Interpretation for Breast Histopathology Classification 

## Completed study

- Conducted a comparative study of pretrained Vision Transformer (ViT), Swin Transformer, DeiT, and BEiT architectures for benign–malignant classification using the BreakHis breast histopathology dataset.
  
- Compared the model performance on patient-level 70:15:15 and 80:10:10 train-validation-test splits using accuracy,
precision, recall, f1-score, specificity, ROC-AUC and confusion-matrix analysis. Swin Transformer 97.16% accuracy shown under 70:15:15 split, DeiT 94.19% accuracy in 80:10:10 split.

- Generated Transformer attention and feature-activation maps to investigate model focus patterns and class-wise prediction errors across benign and malignant histopathology breast images.
  
- Integrated VLM model Gemma 4:12B via Ollama for qualitative vision-language interpretation of histopathology images and corresponding explainability maps.

## 💻 Framework / Technologies / Tools

- **Programming:** Python
- **Deep Learning:** PyTorch, Torchvision
- **Transformer Architectures:** Vision Transformer (ViT), Swin Transformer, DeiT, BEiT
- **Vision-Language Models (VLMs):** Gemma 4:12B, Ollama
- **Model Libraries:** Hugging Face Transformers, TIMM
- **Development Platforms:** Jupyter Notebook, Google Colab, Kaggle
- **Data Processing and Evaluation:** NumPy, Pandas, Scikit-learn, Matplotlib, OpenCV

## 📁 Dataset

- **BreaKHis (Breast Cancer Histopathological Image Dataset)**
- Binary classification:
  - Benign
  - Malignant
- Patient-level data partitioning:
  - 80:10:10 (Training: Validation: Testing)
  - 70:15:15 (Training: Validation: Testing)

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/<YOUR_GITHUB_USERNAME>/Split-Aware-Transformer-Benchmarking-Breast-Histopathology.git

cd Split-Aware-Transformer-Benchmarking-Breast-Histopathology
```

Replace `<YOUR_GITHUB_USERNAME>` with your GitHub username after creating the repository.

### 2. Create a Virtual Environment

**Windows (PowerShell):**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**Linux / macOS:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

Upgrade pip:

```bash
python -m pip install --upgrade pip
```

Install PyTorch and Torchvision:

```bash
pip install torch torchvision
```

For GPU-enabled PyTorch, select the appropriate installation command for your system from the [official PyTorch installation guide](https://pytorch.org/get-started/locally/).

Install the remaining dependencies:

```bash
pip install timm transformers scikit-learn numpy pandas matplotlib pillow opencv-python-headless tqdm jupyter notebook ollama
```

### 4. Set Up Gemma 4:12B Using Ollama

Install [Ollama](https://ollama.com/download), then download and run the vision-language model:

```bash
ollama run gemma4:12b
```

Ensure that the Ollama service is running before executing the vision-language interpretation stage.

**Note:** The VLM interpretation stage is separate from Transformer training and evaluation. It can be executed after generating the required attention or feature-activation maps.

### 5. Download and Configure the Dataset

Download the BreakHis breast histopathology image dataset and organize it in the required directory structure.

Configure the dataset path in the relevant notebook or Python script:

```python
DATA_DIR = "/path/to/breakhis_dataset"
```

For Google Colab, the dataset can be placed in the Colab runtime or accessed through Google Drive.

### 6. Run the Research Notebooks

The experiments investigate four independently trained Transformer architectures under two patient-level data partitioning configurations:

- **80:10:10:** 80% Training, 10% Validation, 10% Testing.
- **70:15:15:** 70% Training, 15% Validation, 15% Testing.

The trained model checkpoints are saved separately for each experimental configuration.

The four model checkpoint filenames are:

```text
vit_best.pth
swin_best.pth
deit_best.pth
beit_best.pth
```

Keep the checkpoints in their respective split-specific directories to avoid mixing models trained under different partition configurations.

### 7. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the relevant project notebook and execute its cells in sequence.

For Google Colab GPU execution:

1. Upload or open the notebook in Google Colab.
2. Select **Runtime → Change runtime type → T4 GPU** (or another available GPU).
3. Mount Google Drive if using Drive for checkpoint storage.
4. Configure the BreaKHis dataset path.
5. Execute the notebook cells in sequence.

### 8. Generate Explainability Maps and VLM Interpretations

After training and evaluating the models, generate architecture-specific visual explanations using the selected checkpoints:

- **DeiT:** Class-token attention maps under the 80:10:10 configuration.
- **Swin Transformer:** Feature-activation maps under the 70:15:15 configuration.

The generated maps can subsequently be supplied to Gemma 4:12B through Ollama for qualitative, group-level interpretation of benign and malignant histopathology images.
