# Classification-of-Bird-Call
Classification of Birdcall Audio by converting into a spectrogram and Using Neural Networks 

---

## Models Used

### 🔹 Binary Classification
- Task: Red-winged Blackbird vs. Dark-eyed Junco
- Model: 3 Conv layers → 3 Pooling → Dense + Dropout → Sigmoid output
- Accuracy: **88%**

### 🔹 Multi-class Classification
- Task: Classify 12 bird species in Greater Seattle
- Model: 4 Conv layers → 3 Pooling → GAP → Dense + Dropout → Softmax
- Accuracy: **57%**

---

##  Dataset

- Source: [Xeno-Canto](https://www.xeno-canto.org) via the BirdCLEF Challenge ([Kaggle link](https://www.kaggle.com/c/birdclef))
- Format: Each audio clip is trimmed into **3-second segments** and converted into **Mel spectrograms**.
- Species Covered:
  - American Crow (`amecro`)
  - Red-winged Blackbird (`rewbla`)
  - Dark-eyed Junco (`daejun`)
  - Black-capped Chickadee (`bkcchi`)
  - and 8 more (see full list in `Appendix A` of the report)

---

##  Methodology

1. **Preprocessing**
   - 3-sec audio ➜ Mel Spectrograms
   - Rescaled and reshaped for CNN input

2. **Training & Validation**
   - Train/Val/Test split: 60/20/20
   - Early stopping + dropout regularization
   - Evaluation Metrics: Accuracy, Precision, Recall, F1, Confusion Matrix

3. **Testing**
   - External clips classified using trained multi-class CNN
   - Probabilities plotted to show model confidence

---

##  Results

### Binary Classifier
- **Accuracy**: 88%
- Balanced performance with minimal misclassifications

### Multi-class Classifier
- **Accuracy**: 57%
- Strongest predictions: American Crow, House Sparrow
- Most errors between acoustically similar species (e.g., Song Sparrow vs. Spotted Towhee)

---

##  Limitations

- Fixed 3-second window might miss long/complex calls
- Some species have overlapping acoustic patterns
- CNN assumes stationarity across input clips

---

##  Future Work

- Use **RNNs or LSTM-CNN hybrids** to capture temporal dependencies
- Test deeper CNN architectures with batch normalization
- Explore **manual feature extraction + SVM/Random Forest** for comparison

---

##  References

- [Xeno-Canto Bird Sounds Archive](https://www.xeno-canto.org)
- [BirdCLEF Competition](https://www.kaggle.com/c/birdclef)
- [Librosa: Music & Audio Signal Processing](https://librosa.org)
- [GeeksforGeeks CNN Architecture](https://www.geeksforgeeks.org/cnn-introduction/)

---

## 🧑‍💻 Author

**Sanjay Ramesh Kannan**  
Graduate Student, Seattle University  
Instructor: Dr. Ariana Mendible

---

## 📝 License

This project is for academic use only. Please cite sources appropriately.
