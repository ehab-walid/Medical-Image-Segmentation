# 🏥 Medical Image Segmentation

Deep learning segmentation of medical images across three clinical tasks — **Brain Tumour**, **Polyp**, and **Heart** — using a family of UNet-based architectures implemented in TensorFlow/Keras and trained on publicly available datasets.

---

## 🧠 Overview

This project implements and compares four encoder-decoder segmentation architectures across three distinct medical imaging tasks. Each task is contained in its own Jupyter notebook with full pipelines covering data loading, preprocessing, model definition, training, and evaluation.

---

## 📓 Notebooks

| Notebook | Task | Dataset | Type |
|---|---|---|---|
| `Brain Tumor Segmentation.ipynb` | Brain tumour segmentation | LGG MRI Segmentation (Kaggle) | Binary |
| `Polyp_segmentation-2.ipynb` | Polyp segmentation | CVC-ClinicDB | Binary |
| `Multi-label Heart Segmentation.ipynb` | Cardiac structure segmentation | ACDC | Multi-label (4 classes) |

---

## 🏗️ Model Architectures

All three notebooks implement and compare the following four architectures:

**UNet** — the standard encoder-decoder with skip connections.

**Res-UNet** — UNet with residual connections in the encoder blocks for improved gradient flow.

**Attention UNet** — UNet augmented with attention gates to focus on relevant regions.

**Attention Res-UNet** — combines residual connections and attention gates for the strongest feature representation.

---

## 📊 Training Details

- **Optimizer:** Adam (lr = 1e-2) with `ReduceLROnPlateau`
- **Loss:** Binary Focal Loss (brain & polyp) / Categorical Focal Cross-Entropy (heart)
- **Callbacks:** Early stopping, model checkpointing (best val loss), learning rate scheduler
- **Epochs:** Up to 100 per model
- **Metrics tracked:** Accuracy, Dice coefficient, Jaccard coefficient (IoU)
- **Evaluation:** Precision, recall, and Dice score computed on held-out test set

---

## 📁 Datasets

| Task | Dataset | Source |
|---|---|---|
| Brain Tumour | LGG MRI Segmentation (`kaggle_3m`) | [Kaggle](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation) |
| Polyp | CVC-ClinicDB | [Link](https://polyp.grand-challenge.org/CVCClinicDB/) |
| Heart | ACDC (Automated Cardiac Diagnosis Challenge) | [Link](https://acdc.creatis.insa-lyon.fr/) |

Datasets are not included in this repository. Download them separately and update `BASE_PATH` in each notebook to point to your local directory.

---

## ⚙️ Tech Stack

| Tool | Role |
|---|---|
| TensorFlow / Keras | Model building & training |
| NumPy, OpenCV, scikit-image | Image processing |
| pandas, scikit-learn | Data handling & train/val/test splits |
| focal_loss | Binary Focal Loss |
| matplotlib, seaborn | Visualisation |
| Google Colab + Drive | Training environment |

---

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/ehab-walid/Medical-Image-Segmentation.git
   cd Medical-Image-Segmentation
   ```

2. Install dependencies:
   ```bash
   pip install tensorflow numpy pandas opencv-python scikit-learn scikit-image matplotlib seaborn focal_loss
   ```

3. Download the relevant dataset and update `BASE_PATH` at the top of the chosen notebook.

4. Open and run the notebook end-to-end in Jupyter or Google Colab.

---

## 👤 Author

**Ehab Walid** — [GitHub](https://github.com/ehab-walid)
