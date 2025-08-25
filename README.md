# Pulmo Disease Classification

A deep learning project for the non-contact diagnosis of respiratory diseases using Orthogonal Frequency Division Multiplexing (OFDM) signals.

## 🌟 Project Overview
This project introduces a novel, non-contact method for the classification of common respiratory diseases. Using a software-defined radio (SDR), a 5.23 GHz OFDM signal with 64 frequencies is transmitted through a patient's lungs. The unique breathing patterns associated with different diseases modulate this signal, which is then analyzed by a deep learning model to classify the patient's condition.  

![Methodology](Methodology.png)

This approach lays the foundation for non-invasive, AI-powered diagnostic tools in future 6G-enabled healthcare environments.

## 🗂️ The OFDM-Breathe Dataset
This work is based on the **OFDM-Breathe dataset**, the first of its kind. It comprises **26,760 seconds of raw RF data** collected from **220 subjects** in a hospital setting. The dataset is categorized into six distinct classes:

| Class Label | Value | Number of Subjects |
|-------------|-------|---------------------|
| Asthma      | 0     | 45                  |
| COPD        | 1     | 43                  |
| ILD         | 2     | 30                  |
| PN          | 3     | 31                  |
| TB          | 4     | 41                  |
| Normal      | 5     | 30                  |



## 🛠️ Technologies & Libraries
- **Python**
- **TensorFlow / Keras** – Deep learning model building & training
- **NumPy** – Numerical operations  
- **Pandas** – Data handling & preprocessing  
- **Matplotlib / Seaborn** – Visualization  
- **Scikit-learn** – Model evaluation  

---

## 🚀 Installation & Setup
Clone the repository:
```bash
git clone https://github.com/wasimnawaz1/Pulmo_Disease_Classification.git
cd Pulmo_Disease_Classification
````

Create a virtual environment:

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 📝 Usage

### Training the Model

To train the model from scratch, run:

```bash
python [training_script].py
```

### Running Inference

To use the trained model for predictions:

```bash
python [inference_script].py --signal_file_path "path/to/your/signal_file.dat"
```

---

## 📈 Model Performance & Key Findings

This project evaluated CNN, LSTM, and Transformer models.
The **CNN model** achieved the best results overall, while LSTM and Transformer also performed exceptionally well.

### CNN Results

| Class  | Accuracy | Precision | Recall | F1-score | TNR  | FPR  | FNR  | MCC  | Jaccard | Support |
| ------ | -------- | --------- | ------ | -------- | ---- | ---- | ---- | ---- | ------- | ------- |
| Asthma | 0.99     | 0.98      | 0.99   | 0.98     | 1.00 | 0.00 | 0.02 | 0.98 | 0.97    | 23520   |
| COPD   | 0.99     | 0.99      | 0.98   | 0.98     | 1.00 | 0.00 | 0.02 | 0.97 | 0.95    | 28224   |
| ILD    | 0.98     | 1.00      | 0.97   | 0.99     | 1.00 | 0.00 | 0.03 | 0.97 | 0.96    | 27048   |
| PN     | 0.99     | 1.00      | 0.98   | 0.99     | 1.00 | 0.00 | 0.03 | 0.97 | 0.95    | 19992   |
| TB     | 0.99     | 0.98      | 0.99   | 0.98     | 0.99 | 0.01 | 0.02 | 0.97 | 0.96    | 16464   |
| Normal | 1.00     | 1.00      | 1.00   | 1.00     | 1.00 | 0.00 | 0.01 | 0.98 | 0.97    | 27048   |

### LSTM Results

| Class  | Accuracy | Precision | Recall | F1-score | TNR  | FPR  | FNR  | MCC  | Jaccard | Support |
| ------ | -------- | --------- | ------ | -------- | ---- | ---- | ---- | ---- | ------- | ------- |
| Asthma | 0.99     | 0.99      | 0.98   | 0.99     | 1.00 | 0.00 | 0.01 | 0.98 | 0.97    | 23520   |
| COPD   | 0.99     | 0.95      | 0.98   | 0.97     | 1.00 | 0.00 | 0.01 | 0.98 | 0.97    | 28224   |
| ILD    | 0.98     | 1.00      | 0.96   | 0.98     | 1.00 | 0.00 | 0.02 | 0.99 | 0.98    | 27048   |
| PN     | 0.98     | 0.99      | 0.97   | 0.98     | 1.00 | 0.00 | 0.01 | 0.98 | 0.97    | 19992   |
| TB     | 0.99     | 0.99      | 0.99   | 0.99     | 1.00 | 0.00 | 0.01 | 0.98 | 0.97    | 16464   |
| Normal | 1.00     | 0.99      | 1.00   | 1.00     | 1.00 | 0.00 | 0.01 | 0.98 | 0.97    | 27048   |

### Transformer Results

| Class  | Accuracy | Precision | Recall | F1-score | TNR  | FPR  | FNR  | MCC  | Jaccard | Support |
| ------ | -------- | --------- | ------ | -------- | ---- | ---- | ---- | ---- | ------- | ------- |
| Asthma | 0.98     | 1.00      | 0.98   | 0.99     | 0.99 | 0.01 | 0.02 | 0.97 | 0.95    | 23520   |
| COPD   | 0.99     | 0.94      | 0.99   | 0.96     | 1.00 | 0.00 | 0.02 | 0.98 | 0.96    | 28224   |
| ILD    | 0.97     | 0.99      | 0.96   | 0.97     | 0.99 | 0.01 | 0.03 | 0.96 | 0.94    | 27048   |
| PN     | 0.99     | 0.99      | 0.98   | 0.98     | 1.00 | 0.00 | 0.02 | 0.98 | 0.97    | 19992   |
| TB     | 0.99     | 0.99      | 0.99   | 0.99     | 0.99 | 0.01 | 0.03 | 0.97 | 0.95    | 16464   |
| Normal | 1.00     | 1.00      | 1.00   | 1.00     | 1.00 | 0.00 | 0.03 | 0.97 | 0.95    | 27048   |

---

### 🔑 Key Findings

* An **ablation study** showed that reliable diagnosis (≈96% accuracy) is achievable using just **8 microwave frequencies**.
* This proves the feasibility of integrating AI-powered diagnosis with efficient data transmission in **6G ISAC systems**.

---

## 📄 License

This project is licensed under the **\[MIT License]**.

---

```
