
# Text Summarizer Project

## Overview
The **Text Summarizer Project** is an advanced Natural Language Processing (NLP) application designed to automatically generate concise summaries of extensive text content. With the ever-increasing volume of information available in articles, research papers, and other documents, efficiently extracting key information is crucial. This project leverages cutting-edge NLP techniques to address the need for effective and accurate text summarization.

### Key Features and Functionality:
- **Text Preprocessing:** The system preprocesses input text by removing noise, punctuation, and stopwords to enhance the quality of the generated summaries.
- **Sentence Extraction:** Advanced NLP techniques are employed to identify key sentences from the input text that best represent the main ideas and concepts.
- **Semantic Understanding:** The system uses semantic analysis to understand the meaning of the text and identify relevant information to include in the summary.
- **Summarization Techniques:** The project explores both extractive and abstractive summarization approaches. Extractive summarization selects and combines important sentences, while abstractive summarization generates summaries by paraphrasing and restructuring the text.
- **Length Control:** Users can adjust the length of the generated summaries, obtaining either short or comprehensive summaries based on their preferences.
- **User Interface:** A user-friendly interface is provided to facilitate easy text input and display of the generated summaries. The interface may include features such as text highlighting and source citation.

### Benefits and Impact:
- **Time-saving:** Quickly obtain condensed summaries of lengthy texts, enabling efficient information digestion.
- **Research and Knowledge Management:** Extract key insights from large volumes of academic papers, reports, and other research materials.
- **Content Curation:** Generate succinct summaries of news articles, blog posts, and online content, aiding in content curation and enhancing reader engagement.
- **Language Learning:** Practice comprehension skills and extract key information from foreign language texts.
- **Information Retrieval:** Enhance search engines and information retrieval systems with concise summaries alongside search results.

## Dataset
The **SAMSum** dataset contains around 16,000 messenger-like conversations with summaries. Created by linguists fluent in English, the dataset reflects a diverse range of topics and conversational styles. Summaries are concise briefs of what people talked about in the conversation, written in the third person.

- **Source:** [SAMSum Dataset](https://huggingface.co/datasets/samsum)
- **Data Fields:** `dialogue` (text of the conversation), `summary` (human-written summary), `id` (unique identifier).
- **Data Splits:** Train: 14,732, Validation: 818, Test: 819

## Model Information
**PEGASUS** is a state-of-the-art transformer-based model developed by Google AI for abstractive text summarization. It is trained on a large dataset of text and code, enabling it to generate informative and fluent summaries. PEGASUS is used in this project for generating summaries of various types of documents.

## Results
After conducting one epoch of training, the model's accuracy was relatively low due to limited computing power. The low accuracy suggests that further training, model adjustments, or dataset enhancements are needed to improve performance. Future iterations will focus on refining the model to achieve better results.

## How to Run the Project
Follow these steps to set up and run the project locally:

1. **Clone the Repository:**
   
   git clone https://github.com/praj2408/Text-Summarizer-Project
 
2. **Create a Conda Environment:**

   conda create -n summary python==3.8 -y
   conda activate summary

3. **Install the Required Packages:**
   
   pip install -r requirements.txt

4. **Run the Application:**
  
   python app.py
 
5. **Access the Application:**
   - Open your browser and navigate to `localhost:<port_number>` to use the text summarizer.

## Deployment Guide: AWS-CICD-Deployment-with-Github-Actions

### Steps:
1. **Login to AWS Console:**
   - Create an IAM user for deployment with the necessary access (EC2 and ECR).

2. **Create ECR Repository:**
   - Save the repository URI (e.g., `635735097495.dkr.ecr.us-east-1.amazonaws.com/text-s`).

3. **Launch EC2 Instance:**
   - Set up an Ubuntu EC2 machine.

4. **Install Docker on EC2:**
   
   sudo apt-get update -y
   sudo apt-get upgrade
   curl -fsSL https://get.docker.com -o get-docker.sh
   sudo sh get-docker.sh
   sudo usermod -aG docker ubuntu
   newgrp docker
  

5. **Configure EC2 as Self-Hosted Runner:**
   - Navigate to `Settings > Actions > Runners` in GitHub and set up the runner by following the provided commands.

6. **Set Up GitHub Secrets:**
   - Add the following secrets to your repository:
     - `AWS_ACCESS_KEY_ID`
     - `AWS_SECRET_ACCESS_KEY`
     - `AWS_REGION` (e.g., `us-east-1`)
     - `AWS_ECR_LOGIN_URI` (e.g., `635735097495.dkr.ecr.us-east-1.amazonaws.com/text-s`)
     - `ECR_REPOSITORY_NAME` (e.g., `simple-app`)

## Contributions
Contributions are welcome! To contribute, please follow the standard GitHub workflow for pull requests.

