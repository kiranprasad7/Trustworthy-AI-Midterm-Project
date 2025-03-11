# Trustworthy-AI-Midterm-Project
## Overview
This project focuses on building an AI-powered application for voice conversion and data augmentation using the Mozilla Common Voice Dataset. The application performs the following tasks:

Converts .mp3 audio files to .wav format for compatibility with machine learning pipelines.

Augments audio data by applying pitch shifting to increase dataset diversity.

Evaluates transcription accuracy across different accent groups to assess the performance of a hypothetical speech recognition system.

The project demonstrates the use of AI for data preprocessing, augmentation, and evaluation, which are critical steps in building robust speech recognition systems.

## Dataset
The project uses the Mozilla Common Voice Dataset, a publicly available dataset containing voice recordings in multiple languages and accents. The dataset includes:

## Audio Clips: Recordings in .mp3 format.

Metadata: A validated.tsv file containing information such as file names, transcriptions, accents, and speaker demographics.

## Dataset Links
Mozilla Common Voice Dataset: Download Here

## Project Files (Code and Data): Google Drive Link

## Dataset Structure
#### clips/: Directory containing .mp3 audio files.

#### validated.tsv: Metadata file with columns like file, ground_truth (transcription), accent, and more.

## Project Functionality
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
#### Input: Metadata from validated.tsv and hypothetical transcriptions (for demonstration purposes).

#### Output: Accuracy scores for different accent groups.

#### Purpose: Evaluates how well a speech recognition system performs across different accents, highlighting potential biases or performance disparities.

## Project Structure

#### VoiceConversionProject/
#### ├── clips/                  # Directory containing input .mp3 files
#### ├── clips_wav/              # Directory for converted .wav files
#### ├── clips_augmented/        # Directory for augmented .wav files
#### ├── validated.tsv           # Metadata file
#### ├── voice_conversion.py     # Main script for conversion, augmentation, and evaluation
#### ├── README.md               # Project documentation

## Requirements
To run this project, you need the following Python libraries:

#### pandas

#### pydub

#### numpy

#### scikit-learn

You can install the required libraries using the following command:
#### pip install pandas pydub numpy scikit-learn

## How to Run the Project
#### Download the Dataset:
### Download the Mozilla Common Voice dataset from here.

### Place the clips/ directory and validated.tsv file in the project folder.

#### Download the Mozilla Common Voice dataset from here.

#### Download Project Files:


#### Access the project code and additional files from the Google Drive link.

#### Install Dependencies:
### pip install pandas pydub numpy scikit-learn

#### Run the Script:
### python voice_conversion.py

### Check Output:

#### Converted .wav files will be saved in the clips_wav/ directory.

#### Augmented .wav files will be saved in the clips_augmented/ directory.

#### Transcription accuracy results will be printed in the console.

## Future Enhancements
#### Integration with Speech Recognition Models: Use the preprocessed and augmented data to train a speech recognition model.

#### Additional Augmentation Techniques: Implement other augmentation techniques like noise addition, time stretching, or speed modification.

#### User Interface: Build a user-friendly interface for uploading audio files and viewing results.

#### Deployment: Deploy the application as a web service using frameworks like Flask or FastAPI.

## Advanced Evaluation and Bias Mitigation
#### 1. Word Error Rate (WER) Calculation per Accent Group
We calculate the Word Error Rate (WER) for each accent group to evaluate the performance of the speech recognition model. WER is a metric used to measure the accuracy of transcriptions by comparing the model's output to the ground truth labels.

#### Steps:
#### Input: Ground truth transcriptions from the validated.tsv file and model-generated transcriptions.

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

## Conclusion
This project successfully demonstrates the use of AI for voice conversion, data augmentation, and fairness evaluation in speech recognition systems. By converting .mp3 files to .wav, applying pitch shifting for data augmentation, and evaluating transcription accuracy across different accent groups, we have built a robust pipeline for preprocessing and analyzing voice data.

#### Key Achievements:
##### Audio Conversion: Successfully converted .mp3 files to .wav format, making the dataset compatible with machine learning pipelines.

##### Data Augmentation: Applied pitch shifting and speed variation techniques to increase dataset diversity and mitigate bias.

##### Fairness Evaluation: Evaluated transcription accuracy and fairness across different accent groups using WER and Fairlearn, identifying potential biases in the model's performance.
