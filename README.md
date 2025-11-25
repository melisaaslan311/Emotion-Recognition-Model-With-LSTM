## 🤖 Emotion Detection Chatbot (Bi-LSTM)

This project implements an **Emotion Detection Chatbot** using a **Bidirectional Long Short-Term Memory (Bi-LSTM)** neural network built with **PyTorch**. The model is trained to classify the emotion expressed in a given text into one of six categories: **joy, anger, love, sadness, fear, or surprise**.

---

### ✨ Key Features

* **Text Preprocessing:** Tokenization using `torchtext`'s basic English tokenizer and vocabulary creation.
* **Sequence Padding:** Handles variable-length input sequences using padding.
* **Bi-LSTM Model:** Uses a Bidirectional LSTM architecture to effectively capture context from both past and future words in a sentence. 
* **Emotion Classification:** Predicts one of 6 distinct emotion classes.
* **Interactive Chatbot:** Simple command-line interface for real-time emotion prediction.
* **GPU Acceleration:** Supports training and inference on a CUDA-enabled GPU (if available) (device: `cuda` or `cpu`).

---

### 📂 Dataset

The model is trained, validated, and tested using three separate files (`train.txt`, `test.txt`, and `va.txt` for validation). These files contain sentences labeled with one of the following six emotions:

| Emotion ID | Label (English) | Label (Turkish) |
| :---: | :---: | :---: |
| 0 | **joy** | Sevinç |
| 1 | **anger** | Öfke |
| 2 | **love** | Sevgi |
| 3 | **sadness** | Hüzün |
| 4 | **fear** | Korku |
| 5 | **surprise** | Şaşkınlık |

---

### ⚙️ Model Architecture

The `EmotionModel` is a deep learning model designed for Sequence Classification:

* **Embedding Layer:** Converts word indices into dense vector representations (**64 dimensions**).
* **Bi-LSTM Layer:** A **2-layer**, **bidirectional** LSTM with a **hidden dimension of 80**. The bidirectional structure means the final hidden state is obtained by concatenating the last forward and last backward hidden states.
* **Dropout:** Applied to the embedding and the final hidden state to prevent overfitting (rate: **0.6**).
* **Linear Layer (`fc`):** Maps the concatenated hidden state (80\*2 = 160 dimensions) to the output layer (**6 classes**).

---

### 🚀 Training and Performance

The model was trained for **20 epochs** using the **Adam optimizer** (learning rate: 0.001) and **Cross-Entropy Loss** (`nn.CrossEntropyLoss`).

Example loss values during the training process:

| Epoch | Train Loss | Validation Loss |
| :---: | :---: | :---: |
| 1 | 1.588 | 1.564 |
| ... | ... | ... |
| 20 | **0.353** | **0.181** |

The final performance on the test set was:

* **Test Loss: 0.170**

---

### 💬 How to Run the Chatbot

The provided code includes an interactive `chatbot()` function:

1.  **Run the complete script** (assuming your data files are present).
2.  The model will train and print epoch losses.
3.  The `chatbot()` function will start automatically.

**Interaction Example:**
You: hello how are you Chatbot: Hello! How are you feeling today? You: no i am bad today Chatbot: I think you're feeling sadness. You: q Chatbot: Goodbye!

To stop the chatbot, simply type **`q`** and press Enter.

---

### 🔧 Dependencies

The required libraries are:

* `torch`
* `torchvision`
* `torchaudio`
* `torchtext`
* `pandas`
* `numpy`
* `scikit-learn`

You can install them using the following commands:

```bash
!pip3 install torch torchvision torchaudio
!pip install torchtext pandas numpy scikit-learn
4.  The `chatbot()` function will start automatically.

**Interaction Example:**
