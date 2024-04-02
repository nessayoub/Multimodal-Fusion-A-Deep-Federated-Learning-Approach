# Federated Learning for Disaster Event Classification with Social Media Analysis

## Methodology

### Pipeline Overview
Figure 1 illustrates the pipeline of our proposed model for disaster event classification utilizing social media analysis. The approach comprises three main components: feature extraction, multimodal data fusion, and deep federated learning process. I will elaborate on each phase in the subsequent subsections.

### 3.1 Dataset Preparation
I utilize the MEDIC dataset, which comprises 5831 image-tweet pairs divided into training (5247 samples) and test (584 samples) sets. Notably, the dataset exhibits class imbalance, with the majority of samples falling under the non-damage category (2975 cases). We preprocess images, resize them to 228x228x3 dimensions, and normalize pixel values to a range of [0, 1]. Various augmentation techniques are employed to enrich the dataset.

### 3.2 Multimodal Feature Extraction
For visual features, I will be employing a ResNet50 pre-trained model, known for its deep CNN architecture and utilization of residual connections to mitigate vanishing gradient problems. Textual features are extracted using BERT, a state-of-the-art NLP model, renowned for its bidirectional approach in contextual understanding of language. We utilize BERT-base-uncased variant for its effectiveness in handling diverse textual data.

### 3.3 Data Fusion and Classification
The outputs from dense layers of both visual and textual components are merged to create a unified representation through late fusion. This approach involves independent analysis of inputs from multiple modalities followed by integration of outputs to arrive at a conclusive prediction. Equal-sized hidden nodes are used in the classification layer for both modalities.

### 3.4 Federated Learning Setup
The federated learning process commences with initialization of a global model and individual client models. Key hyperparameters such as number of training rounds, selected clients per round, and training epochs are set. In each iteration, a subset of clients is chosen for model update, simulating the decentralized nature of federated learning. The client updates are aggregated at the server using mean aggregation method. The global model's performance is evaluated on a separate test subset to gauge its generalization capabilities.

Continuous monitoring of training and testing metrics allows for observation of convergence patterns and overall progress of the federated learning model. Insights into learning dynamics and collaborative efficiency are gleaned from these metrics over multiple rounds.

---
