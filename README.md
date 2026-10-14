# Fashion-MNIST: Exploratory Analysis & KNN From Scratch

Exploratory data analysis, dimensionality reduction (t-SNE, PCA) and a
from-scratch **K-Nearest Neighbors** classifier on the
[Fashion-MNIST](https://github.com/zalandoresearch/fashion-mnist) dataset.

## What's inside

**1. Exploratory data analysis**
- Image representation (each 28×28 image is a flat vector of 784 pixels)
- Pixel value range (0–255)
- Mapping numeric labels (0–9) to class names
- Grid of 5 random samples from each class
- Class distribution bar plot

**2. Class separability with t-SNE**
- Sample 100 images per class (1,000 total)
- Reduce to 3 dimensions with t-SNE and plot in 3D
- Discussion of which classes separate well and which overlap

**3. Preprocessing**
- Stratified 70 / 15 / 15 split (train / validation / test)
- Scaling (`MinMaxScaler` or `StandardScaler`), fitted on the training set only
- PCA keeping a target fraction of variance (85%, 90% or 95%)

**4. KNN implemented from scratch (NumPy)**
- Euclidean or Manhattan distance
- Neighbor search via sorting
- Uniform or inverse-distance weighted voting
- Per-class probability scores, used for ROC/AUC

**5. Model comparison and evaluation**
- 9 configurations compared on the validation set (scaler, PCA variance, `k`, metric, weighting)
- Per-class precision, recall, F1 and one-vs-rest AUC
- Confusion matrix and ROC curves

## Dataset

| Property | Value |
|---|---|
| Source | [OpenML](https://www.openml.org/d/40996) (`data_id=40996`) |
| Samples | 70,000 |
| Features | 784 (28×28 grayscale) |
| Classes | 10 |
| Pixel range | 0 – 255 |

| Label | Class | Label | Class |
|:-:|---|:-:|---|
| 0 | T-shirt/top | 5 | Sandal |
| 1 | Trouser | 6 | Shirt |
| 2 | Pullover | 7 | Sneaker |
| 3 | Dress | 8 | Bag |
| 4 | Coat | 9 | Ankle boot |

## Results

Hyperparameters were compared on the validation set, using a stratified
10,000-sample subset of the training data to keep the from-scratch KNN fast.

| Scaler | PCA variance | k | Metric | Weighted | Accuracy | Macro F1 | Macro AUC |
|---|:-:|:-:|---|:-:|:-:|:-:|:-:|
| standard | 0.90 | 7 | manhattan | yes | **0.8420** | **0.8423** | 0.9737 |
| standard | 0.90 | 7 | euclidean | yes | 0.8413 | 0.8414 | 0.9718 |
| minmax | 0.90 | 7 | manhattan | yes | 0.8412 | 0.8411 | 0.9736 |
| minmax | 0.90 | 5 | euclidean | yes | 0.8406 | 0.8401 | 0.9668 |
| minmax | 0.90 | 7 | euclidean | yes | 0.8392 | 0.8386 | 0.9724 |
| minmax | 0.95 | 7 | euclidean | yes | 0.8374 | 0.8373 | 0.9717 |
| minmax | 0.90 | 7 | euclidean | no | 0.8373 | 0.8360 | 0.9717 |
| minmax | 0.85 | 5 | euclidean | yes | 0.8371 | 0.8366 | 0.9656 |
| minmax | 0.90 | 9 | euclidean | yes | 0.8367 | 0.8359 | 0.9744 |

The differences between configurations are small (under 1 percentage point),
so the ranking should not be over-interpreted.

**Observations**
- Trousers, sandals, sneakers, bags and ankle boots are the easiest classes.
- Most errors come from visually similar upper-body garments:
  T-shirt/top vs. Shirt, and Pullover vs. Coat.

## Getting started

```bash
git clone https://github.com/Mobin-Khademi/Fashion-MNIST-dataset.git
cd Fashion-MNIST-dataset
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook main.ipynb
```

The dataset is downloaded automatically from OpenML on first run, so an
internet connection is needed. Running every KNN configuration takes several
minutes because the classifier is implemented in plain NumPy.

## Project structure

```
Fashion-MNIST-dataset/
├── main.ipynb    # full analysis and experiments
└── README.md
```

## Requirements

- Python 3.9+
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- jupyter

## Possible next steps

- Report final performance of the chosen configuration on the held-out test set
- Compare the from-scratch KNN with `sklearn.neighbors.KNeighborsClassifier`
- Try other classifiers (SVM, Random Forest, a small CNN)

## Author

**Mobin Khademi** · [GitHub](https://github.com/Mobin-Khademi)
