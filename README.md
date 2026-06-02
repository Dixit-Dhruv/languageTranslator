# 🌍 Language Translator using Deep Learning (LSTM Encoder-Decoder)

A real-time Neural Machine Translation (NMT) application that translates English text into French using an LSTM-based Encoder-Decoder architecture built with TensorFlow/Keras. The project includes model training, inference, and a user-friendly GUI for translation.

---

## 📌 Project Overview

This project demonstrates how Neural Machine Translation (NMT) works using a Sequence-to-Sequence (Seq2Seq) model.

The model:

- Accepts English text as input
- Encodes the sentence into a context vector using an Encoder LSTM
- Decodes the context vector into French text using a Decoder LSTM
- Uses Teacher Forcing during training for improved learning
- Provides a GUI interface for real-time translations

---

## 🚀 Features

✅ English → French Translation

✅ LSTM Encoder-Decoder Architecture

✅ Teacher Forcing Training Technique

✅ Character-Level Tokenization

✅ TensorFlow/Keras Implementation

✅ Real-Time Translation GUI

✅ Model Saving & Loading

✅ Interactive User Interface using Tkinter

---

## 🏗️ Architecture

```text
English Sentence
        │
        ▼
 ┌──────────────┐
 │ Encoder LSTM │
 └──────────────┘
        │
 Hidden State + Cell State
        │
        ▼
 ┌──────────────┐
 │ Decoder LSTM │
 └──────────────┘
        │
        ▼
 French Sentence
```

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
| Python | Programming Language |
| TensorFlow | Deep Learning Framework |
| Keras | Model Building |
| NumPy | Numerical Operations |
| Scikit-Learn | One-Hot Encoding |
| Pickle | Data Serialization |
| Tkinter | GUI Development |

---

## 📂 Project Structure

```bash
Language-Translator/
│
├── eng-french.txt          # Dataset
├── langTraining.py         # Model Training Script
├── LangTransGui.py         # GUI Application
├── training_data.pkl       # Saved Vocabulary & Metadata
│
├── s2s/
│   ├── saved_model.pb
│   ├── variables/
│
├── Model_plot.png
├── README.md
└── requirements.txt
```

---

## 📊 Dataset

The project uses an English-French parallel corpus where:

```text
English Sentence     French Sentence
------------------------------------
Hello                Bonjour
How are you?         Comment allez-vous ?
Good Morning         Bonjour
```

Dataset format:

```text
English Sentence<TAB>French Sentence
```

---

## ⚙️ Installation

### 1. Clone Repository

```bash
git clone https://github.com/yourusername/language-translator.git

cd language-translator
```

### 2. Create Virtual Environment

```bash
python -m venv venv
```

Activate:

Windows:

```bash
venv\Scripts\activate
```

Linux/Mac:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install tensorflow numpy scikit-learn pickle-mixin
```

---

## 🧠 Model Training

Run:

```bash
python langTraining.py
```

Training process:

1. Load dataset
2. Character tokenization
3. One-hot encoding
4. Build Encoder-Decoder model
5. Train using Teacher Forcing
6. Save trained model

---

## 📈 Model Configuration

```python
LSTM Units = 256

Optimizer = Adam

Loss Function = Categorical Crossentropy

Batch Size = 64

Epochs = 200

Validation Split = 0.2
```

---

## 🎯 Teacher Forcing

Teacher Forcing is used during training.

Example:

Input:

```text
Hello
```

Target:

```text
\tBonjour\n
```

Decoder learns to predict:

```text
\t  → B
B   → o
Bo  → n
Bon → j
...
```

This significantly improves convergence and translation quality.

---

## ▶️ Run the Translator GUI

After training:

```bash
python LangTransGui.py
```

A graphical interface will open where users can:

- Enter English text
- Click Send
- Receive French translation instantly

---

## 🖥️ Example Output

```text
Input:
How are you?

Output:
Comment allez-vous ?
```

```text
Input:
Good Morning

Output:
Bonjour
```

---

## 🔍 Working Principle

### Encoder

- Reads English sentence character-by-character.
- Generates hidden and cell states.
- Captures semantic meaning.

### Decoder

- Uses encoder states as initial memory.
- Generates French sentence one character at a time.
- Stops when end token (`\n`) is produced.

---

## 📚 Concepts Used

- Natural Language Processing (NLP)
- Neural Machine Translation (NMT)
- Sequence-to-Sequence Learning
- Encoder-Decoder Architecture
- Recurrent Neural Networks (RNN)
- Long Short-Term Memory (LSTM)
- Teacher Forcing
- One-Hot Encoding

---

## 🔮 Future Improvements

- Support multiple languages
- Use Word Embeddings
- Integrate Attention Mechanism
- Replace LSTM with Transformer Architecture
- Deploy using Flask/Django
- Create Web-Based Translator
- Add Speech-to-Text Translation
- Real-Time Voice Translation

---

## 📊 Limitations

- Trained on only ~10,000 sentence pairs
- Character-level translation is slower
- Limited vocabulary
- Translation quality depends on dataset size
- Not suitable for production-scale translation

---

## 🤝 Contributing

Contributions are welcome.

Steps:

1. Fork the repository
2. Create a new branch
3. Commit your changes
4. Push to your branch
5. Create a Pull Request

---

## 📜 License

This project is licensed under the MIT License.

---

## 👨‍💻 Author

**Dhruv Dixit**

B.Tech Student | AI & Machine Learning Enthusiast

### Interests
- Deep Learning
- Computer Vision
- Natural Language Processing
- Generative AI
- Backend Development

---

⭐ If you found this project useful, please consider giving it a star!
