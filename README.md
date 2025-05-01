# Trustworthy-AI-Midterm-Project
## Overview
This project focuses on building an AI-powered application for bias detection and mitigation in speech recognition models using the Mozilla Common Voice Dataset. The application performs the following tasks:

Converts .mp3 audio files to .wav format for compatibility with machine learning pipelines.

Augments audio data by applying pitch shifting to increase dataset diversity.

Evaluates transcription accuracy across different accent groups to assess the performance of a hypothetical speech recognition system.

The project demonstrates the use of AI for data preprocessing, augmentation, and evaluation, which are critical steps in building robust speech recognition systems.

## 🎯 Goals

- Measure **WER** for each accent group to evaluate performance disparities.
- Quantify **fairness gaps** using metrics like max disparity and WER ratio.
- Provide a baseline for **trustworthy AI evaluation** in speech systems.
  
## 📁 Dataset
The project uses the Mozilla Common Voice Dataset, a publicly available dataset containing around 28,000 voice recordings in multiple languages and accents. The dataset includes:

## Audio Clips: Recordings in .mp3 format.

Metadata: A other.tsv file containing information such as file names, transcriptions, accents, and speaker demographics.

## Dataset Links
#### Mozilla Common Voice Dataset: [Download Here](https://commonvoice.mozilla.org/en/datasets)

## Dataset Structure
#### clips.zip: Sample Directory containing 5 files of .mp3 audio files.

#### clips_wav.zip: Sample Directory containing 5 files of .wav audio files.

#### clips_resampled.zip: Sample Directory containing 5 resampled files of .wav audio files.

#### clipsaugmented.zip: Sample Directory containing 5 augmented files of .wav audio files.

#### (Note: The actual dataset contains 27.408 audio files, due to github limitations we just uploaded 5 sample auido files yoiu can find the entire dataset in provided links)

#### other.tsv: Metadata file with columns like file, ground_truth (transcription), accent, and more.

## 🧪 Project Functionality
#### The project is divided into three main components:

## 1. Audio Conversion (MP3 to WAV)
#### Input: .mp3 files from the clips/ directory.

#### Output: Converted .wav files saved in the clips_wav/ directory.

#### Purpose: Many machine learning models and libraries prefer .wav files due to their uncompressed nature and ease of processing.

## 2. Data Augmentation (Pitch Shifting)
#### Input: .wav files from the clips_wav/ directory.

#### Output: Augmented .wav files saved in the clips_augmented/ directory.

#### Purpose: Pitch shifting is a common technique for data augmentation in speech processing. It helps improve the robustness of machine learning models by introducing variability in the dataset.

## 3. Transcription Accuracy Evaluation
#### Input: Metadata from other.tsv and hypothetical transcriptions (for demonstration purposes).

#### Output: Accuracy scores for different accent groups.

#### Purpose: Evaluates how well a speech recognition system performs across different accents, highlighting potential biases or performance disparities.


## Project Structure

#### Trustworthy Project/
#### ├── clips/                  # Directory containing input .mp3 files
#### ├── clips_wav/              # Directory for converted .wav files
#### ├── clips_augmented/        # Directory for augmented .wav files
#### ├── other.tsv               # Metadata file
#### ├── MAIN_CODE.ipynb         # Main script for conversion, augmentation, and evaluation
#### ├── README.md               # Project documentation

## ⚙️ Requirements
To run this project, you need the following Python libraries:

#### pandas
#### pydub
#### numpy
#### scikit-learn
#### AudioSegment
#### librosa
#### soundfile
#### torch
#### Wav2Vec2ForCTC, Wav2Vec2Processor
#### torchaudio
#### jiwer
#### MetricFrame


## How to Run the Project
#### Download the Dataset:
### Download the Mozilla Common Voice dataset from above provided link.

### Place the clips/ directory and other.tsv file in the project folder.

#### Download the Mozilla Common Voice dataset from given link.

#### Download Project Files:


### You can install the required libraries using the following command::
#### pip install pandas pydub numpy scikit-learn pandas AudioSegment librosa soundfile torch transformers torchaudio jiwer

#### Run the Script:
### python MAIN_CODE.py

### Check Output:

#### Converted .wav files will be saved in the clips_wav/ directory.

#### Augmented .wav files will be saved in the clips_augmented/ directory.

#### Transcription accuracy results will be printed in the console.

## 🧮 Key Results

- ✅ **Overall WER**: `0.572`
- 🎯 **Mean Accent WER**: `0.439`
- ⚖️ **Max Disparity**: `1.684`
- 🔁 **Coefficient of Variation**: `0.629`
- 🚩 **Top 10 Accents with Highest WER** include:
  - Skopje (Macedonian)
  - Caribbean
  - South Asian
  - Scottish
  - Filipino

## 📊 Insights

- The **WER gap** between the best and worst performing accents is substantial.
- Accents not seen frequently during pretraining (e.g., regional or mixed accents) tend to perform poorly.
- Using a single global model introduces **systemic disparities** in transcription accuracy.

## ✅ Conclusion

This project clearly demonstrates that even high-performing speech recognition models like **Wav2Vec2** can show significant **bias** when evaluated across diverse accent groups. While the model performs well overall, certain accents—especially those underrepresented during pretraining—consistently receive much higher error rates.

These findings underscore a crucial challenge in building **trustworthy AI systems**: **performance fairness** is not guaranteed, even with large-scale pre-trained models. As speech-based technologies become more embedded in everyday life, ensuring **equal usability and reliability** across demographic groups is vital.

Our WER-based fairness analysis reveals that fairness metrics must be integral to model evaluation pipelines. This project also provides a reproducible framework that can be extended to **data augmentation**, **model fine-tuning**, or **accent-specific adaptation** as future work.

Ultimately, this study emphasizes the **importance of transparency, fairness, and robustness** in deploying speech recognition technologies at scale—especially for real-world use cases where user diversity is high.


## Advanced Evaluation and Bias Mitigation
#### 1. Word Error Rate (WER) Calculation per Accent Group
We calculate the Word Error Rate (WER) for each accent group to evaluate the performance of the speech recognition model. WER is a metric used to measure the accuracy of transcriptions by comparing the model's output to the ground truth labels.

#### Steps:
#### Input: Ground truth transcriptions from the other.tsv file and model-generated transcriptions.

#### Output: WER scores for each accent group.

#### Formula:
<img width="319" alt="image" src="https://github.com/user-attachments/assets/8fb08d8c-4d5e-4671-b3a7-46341d810c41" />

## 2. Fairness Evaluation using Fairlearn
We use the Fairlearn library to evaluate the fairness of the model across different accent groups. Fairness metrics help identify disparities in model performance for different demographic groups.

#### Steps:
#### Input: Ground truth labels, model predictions, and sensitive features (e.g., accents).

#### Output: Fairness metrics such as accuracy disparity or WER disparity across groups.

## 3. Bias Mitigation using Data Augmentation
To mitigate bias, we apply data augmentation techniques such as pitch shifting and speed variation. These techniques increase the diversity of the dataset, making the model more robust across different accents.

#### Steps:
#### Input: Original .wav files from the clips_wav/ directory.

#### Output: Augmented .wav files saved in the clips_augmented/ directory.

#### Techniques:

#### Pitch Shifting: Alter the pitch of the audio to simulate different voices.

#### Speed Variation: Adjust the speed of the audio to simulate different speaking rates.

## 🧠 Future Enhancements
#### Integration with Speech Recognition Models: Use the preprocessed and augmented data to train a speech recognition model.

#### Additional Augmentation Techniques: Implement other augmentation techniques like noise addition, time stretching, or speed modification.

## Conclusion
