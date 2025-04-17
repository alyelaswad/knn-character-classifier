<!-- SHIELDS -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


# knn-character-classifier
This project implements a K-Nearest Neighbors (KNN) classifier for recognizing lower-case characters from noisy image data. The classifier uses an 80%-20% cross-validation approach to determine the optimal value of K, validated over 10 randomized train-validation splits. The final model is evaluated using a separate test dataset. 

## 📂 Dataset

- **Train Path:** `../dataset/Noise Train`
- **Test Path:** `../dataset/Noise Test`
- **Format:** Grayscale `.jpg` images, size `12x12`
- **Images per Class:**
  - Train: 7 per character
  - Test: 2 per character

## 🚀 How It Works

1. **Preprocessing:**
   - Read all grayscale images from training and testing datasets.
   - Normalize image pixel values to `[0, 1]`.

2. **Training:**
   - Cross-validation over 10 randomized 80%-20% splits of training data.
   - For each fold, K values from 1 to 40 are evaluated.
   - Accuracy is computed, and the best K per fold is stored.

3. **Evaluation:**
   - Use the most frequent best K across folds.
   - Classify test data and compute character-wise correct classifications.

4. **Visualization:**
   - Plot: Mean error vs. K value.
   - Plot: Correct classifications per character.

## 📊 Output Visualizations

- `KNN.jpg` — Mean Error vs. K
- `Accuracy.jpg` — Per-character classification counts

## 🛠️ Tech Stack

| Tool / Library        | Purpose                              |
|-----------------------|--------------------------------------|
| `Python 3`            | Programming language                 |
| `NumPy`               | Numerical operations                 |
| `OpenCV (cv2)`        | Image reading & processing           |
| `Matplotlib`          | Plotting graphs                      |
| `Scikit-learn`        | Train-test split (cross-validation) |
| `heapq`               | Efficient nearest neighbor selection |
| `collections.Counter` | Label frequency analysis             |

## 📈 Results

- ✅ Best K (via CV): **3**
- 🎯 Avg CV Accuracy: ~**90.27%**

## 📁 File Structure



<!-- SHIELD LINKS -->
[contributors-shield]: https://img.shields.io/github/contributors/alyelaswad/knn-character-classifier.svg?style=for-the-badge
[contributors-url]: https://github.com/alyelaswad/knn-character-classifier/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/alyelaswad/knn-character-classifier.svg?style=for-the-badge
[forks-url]: https://github.com/alyelaswad/knn-character-classifier/network/members
[stars-shield]: https://img.shields.io/github/stars/alyelaswad/knn-character-classifier.svg?style=for-the-badge
[stars-url]: https://github.com/alyelaswad/knn-character-classifier/stargazers
[issues-shield]: https://img.shields.io/github/issues/alyelaswad/knn-character-classifier.svg?style=for-the-badge
[issues-url]: https://github.com/alyelaswad/knn-character-classifier/issues
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/aly-elaswad/
