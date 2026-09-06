# Fashion-MNIST Dataset Analysis
```markdown
Exploratory Data Analysis and visualization of the **Fashion-MNIST** dataset.

This project includes:
- Loading and inspecting the Fashion-MNIST dataset
- Understanding image representation
- Analyzing pixel value ranges
- Mapping numerical labels to class names
- Visualizing random samples from each class

```

## Project Structure

```
fashion-mnist/
├── main.ipynb          # Main analysis notebook
└── README.md
```

---

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Mobin-Khademi/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
```

2. Install dependencies:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn Jupyter
```

3. Run the notebook:
```bash
jupyter notebook
```

---

## Dataset Overview

- **Source**: OpenML (data_id = 40996)
- **Samples**: 70,000 images
- **Features**: 784 (28×28 grayscale images)
- **Classes**: 10
- **Pixel value range**: 0 – 255

### Class Labels

| Label | Class Name     |
|-------|----------------|
| 0     | T-shirt/top    |
| 1     | Trouser        |
| 2     | Pullover       |
| 3     | Dress          |
| 4     | Coat           |
| 5     | Sandal         |
| 6     | Shirt          |
| 7     | Sneaker        |
| 8     | Bag            |
| 9     | Ankle boot     |

---

## Notebook Contents

### 1. Single Image Representation
Each image is represented as a 1D array of 784 pixel values (flattened 28×28 image).

### 2. Pixel Value Range
- Minimum pixel value: **0**
- Maximum pixel value: **255**

### 3. Label Mapping
Numerical labels (0–9) correspond to the clothing categories listed above.

### 4. Visualization
A grid plot showing 5 random sample images from each of the 10 classes.

---

## Requirements

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

---

## Author

**Mobin Khademi**  
GitHub: [Mobin-Khademi](https://github.com/Mobin-Khademi)
```
