# Facial Emotion Recognition System

## Overview

The Facial Emotion Recognition System is designed to develop and deploy a deep neural network-based model for recognizing facial emotions on an ultra-low power embedded system. This project is divided into two phases: Model Development and Deployment.

## Project Contributors

- Maanasi Shastri (01FE21BCS210)
- Swarna Patil (01FE21BCS145)
- Ananya Kulkarni (01FE21BCS144)
- Amrutha Beedikar (01FE21BCS198)

Under the guidance of Dr. Sujatha C, KLE Technological University, Vidyanagar, Hubballi-580031, Karnataka, India.

## Phase 1: Model Development

### Problem Statement and Objectives

#### Problem Statement
Develop a synthesizable AI model to perform image classification on facial emotions using a Convolutional Neural Network.

![image](https://github.com/user-attachments/assets/f78dd619-4e62-4cef-8329-0f6edb6ccb7b)


#### Objectives
- Preprocess the images.
- Construct and train a convolutional neural network(CNN) model to categorize facial emotions in humans.
- Test and Compare the synthesizable model's accuracy and efficiency with state-of-the-art techniques for facial emotion recognition.

### Software Engineering Requirements
#### Functional Requirements
- The user shall be able to input the grayscale facial images for emotion recognition.
- The system shall classify a range of emotions such as happiness, sadness, anger, fear, etc., from the input images.
- The system shall predict the emotions and generate scores/accuracies for all the emotion classes.
- The user shall be able to view the performance analysis.

#### Non-Functional Requirements
- The system should achieve a response time of less than 2 seconds for emotion recognition processing, ensuring minimal delay in emotion recognition to enhance user experience.
- The emotion recognition system should achieve a minimum accuracy of 70% on standardized emotion recognition benchmarks.

#### Use Case Diagram
![image](https://github.com/user-attachments/assets/c3a8f9ce-cba5-4015-b90f-8acd187b190d)


### Dataset Description
- **Source:** Kaggle ("Facial emotion recognition" dataset)
- **Size:** 56.51MB
- **Images:** 35,914 grayscale face images
- **Classes:** 7 (happy, sad, disgust, angry, fear, neutral, surprise)
- **The number of images for each feature is as follows:**
  - angry – 4953 images
  - disgust - 547 images
  - fear - 5121 images
  - Happy - 8989 images
  - neutral - 6198 images
  - sad - 6077 images
  - surprise - 4002 images
- **Testing images** – 20.06% [7,205 images]
- **Training images** – 79.93% [28,709 images]


### Implementation
Data Preprocessing: Balancing of the train dataset using the oversampling method.
![image](https://github.com/user-attachments/assets/31a9799f-7cfe-4fa5-b4a3-155f7ce32e99)



### Literature Survey
1. **Benchmarking the MAX78000 AI microcontroller** for deep learning applications.
2. **TinyissimoYOLO:** A quantized object detection network for microcontrollers.
3. **Wildlife Species Classification on the Edge:** Deep learning for low-power devices.
4. **Ultra-low Power DNN Accelerators for IoT:** Performance of the MAX78000.
5. **AI and ML Accelerator Survey and Trends:** Developments in AI and ML accelerators.
6. **Ultra-Low Power Keyword Spotting at the Edge:** Optimized CNN model for the MAX78000.

### Approach
1. **Model Development:** Designed with PyTorch.
2. **Training:** Trained with floating-point weights, then quantized for deployment.
3. **Model Evaluation:** Assessed using an evaluation dataset.
4. **Synthesis Process:** Used the MAX78000 Synthesizer tool to generate optimized C code from ONNX files and YAML model description.

## Phase 2: Deployment

### Deployment Board
- **Board:** MAX78000FTHR

### Deployment Flow
1. Convert the trained model to ONNX format.
2. Use the MAX78000 Synthesizer tool to generate optimized C code.
3. Deploy the model on the MAX78000FTHR board.

### Circuit Diagram
- **Inference Energy Calculation:** 
  - \( \text{Inference Energy} = I \times V \times \text{inference time} \)
  - Where \( I \) is the current (mA), \( V \) is the voltage (V).

### Results and Observations
- **Epochs:** 100
- **Learning Rate:** 0.001
- **Accuracy:** 57.82%
- **Class-wise Accuracy:**
  - Happy: 77.00%
  - Surprise: 72.44%
  - Disgust: 53.15%
  - Angry: 50.73%
  - Neutral: 47.04%
  - Sad: 44.59%
  - Fear: 39.84%

### Resource Usage
- **Weight Memory:** 70,572 bytes out of 442,368 bytes total (16.0%)
- **Bias Memory:** 7 bytes out of 2,048 bytes total (0.3%)
- **Inference Energy:**
  - \( I = 3.16 \) mA
  - \( V = 5 \) V
  - Inference Time = 1.516 µs
  - **Inference Energy = 0.0237 mJ**
