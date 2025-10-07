# 🧠 Multiple Sclerosis (MS) Early Diagnosis with Deep Learning

This project explores how deep learning can help in the **early detection of Multiple Sclerosis (MS)** from brain MRI scans.
I’ve built and trained AI models to classify neurological disorders using the **Multi-Class Neurological Disorder (MCND)** dataset from Kaggle.

---

## 📘 About the Project

Multiple Sclerosis is a complex neurological condition that affects the brain and spinal cord. Detecting it early can make a huge difference in treatment outcomes.
In this project, I used **MRI brain images** and **deep learning models** to distinguish MS from other neurological disorders like Alzheimer’s and Parkinson’s disease — as well as from healthy brains.

I experimented with different CNN architectures (including EfficientNet and ResNet), fine-tuned the learning rate.

---

## 🧩 Dataset

* **Dataset name:** Multi-Class Neurological Disorder (MCND)
* **Source:** [Kaggle Dataset](https://www.kaggle.com/datasets/alifatahi/multi-class-neurological-disorder-mcnd-dataset?select=AD_MildDemented)
* **Classes included:**

AD_MildDemented
AD_ModerateDemented
AD_VeryMildDemented
BT_glioma
BT_meningioma
BT_pituitary
MS
Normal

The dataset contains brain MRI slices grouped into folders by diagnosis. Each image is labeled and preprocessed, making it ready for direct use in training.

---

## ⚙️ How to Run

1. **Clone this repository**

   ```bash
   git clone https://github.com/<your-username>/Multiple_Sclerosis_AI.git
   cd Multiple_Sclerosis_AI
   ```

2. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Download the dataset**
   You can get it from Kaggle here:
   [Multi-Class Neurological Disorder Dataset](https://www.kaggle.com/datasets/alifatahi/multi-class-neurological-disorder-mcnd-dataset?select=AD_MildDemented)

4. **Set the dataset path** in the notebook or config file:

   ```python
   DATASET_PATH = "/path/to/multi-class-neurological-disorder-mcnd-dataset"
   ```

5. **Run the notebook**
   Open the file `Multiple_Sclerosis_MS_Early_Diagnosis.ipynb` and start training or evaluation.

---

## 🧠 Model Details

* **Architecture:** EfficientNetB0 / Custom CNN
* **Optimizer:** Adam (learning rate decay from 1e-4 → 1e-6)
* **Loss:** Categorical Cross-Entropy
* **Metrics:** Accuracy, Validation Accuracy, Loss

Training was done with callbacks such as **EarlyStopping** and **ReduceLROnPlateau** to stabilize learning and avoid overfitting.

---

## 📈 Results

| Metric              | Score |
| ------------------- | ----- |
| Training Accuracy   | 99.7% |
| Validation Accuracy | 97.2% |
| Training Loss       | 0.010 |
| Validation Loss     | 0.118 |
| Final Learning Rate | 4e-6  |

The model generalizes very well — the small gap between training and validation accuracy means it’s not overfitting.
The learning rate scheduler also helped the model converge smoothly.

---

## 🔍 Evaluation & Explainability

I evaluated the model using:

* **Confusion Matrix**

These tools help verify that the model is focusing on medically meaningful areas, not random noise.

---

## 🧪 Reproducibility

You can reproduce the same results by setting a fixed random seed:

```python
import tensorflow as tf, numpy as np, random
tf.random.set_seed(42)
np.random.seed(42)
random.seed(42)
```

All models and logs are saved automatically inside:

```
/checkpoints/  → saved models (.h5)
/logs/         → training history
```

---

## 📊 Visualization

The notebook automatically generates:

* Accuracy and loss curves
* Learning rate schedule

You’ll find all output visuals in the `/results/` folder.

---

## 🧰 Tools Used

* Python 3.10
* TensorFlow / Keras
* NumPy, Pandas
* OpenCV
* Matplotlib, Seaborn
* scikit-learn

---

## 🧾 Citation

If you use this dataset or this project, please cite the dataset creator and this repo:

> Fatahi, A. (2023). *Multi-Class Neurological Disorder (MCND) Dataset.* Kaggle.
> [https://www.kaggle.com/datasets/alifatahi/multi-class-neurological-disorder-mcnd-dataset](https://www.kaggle.com/datasets/alifatahi/multi-class-neurological-disorder-mcnd-dataset)

---

## 🤝 Contributing

I welcome contributions — whether it’s improving preprocessing, testing new architectures (like Vision Transformers), or extending the model for clinical interpretability.
Feel free to open an issue or pull request anytime.

---

## 📧 Contact

**Author:** Enad Alrougi
**Role:** Data Scientist & AI Researcher

---

**Email:** [enadrouq@outlook.com](mailto:enadrouq@outlook.com)

---

**LinkedIn:** [enad-alrougi](https://www.linkedin.com/in/enad-alrougi-5b0a45253/)

---

**GitHub:** [IDE21](https://github.com/IDE21)
