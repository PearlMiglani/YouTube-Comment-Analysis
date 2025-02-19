# YouTube Video Engagement Analysis using Machine Learning

## Introduction
With millions of videos uploaded daily on YouTube, understanding the factors that drive engagement can provide critical insights for content creators and marketers. This project explores how machine learning techniques can predict YouTube video engagement levels based on metadata and user-generated content.

## Problem Statement
The primary objective of this project is to determine which attributes of YouTube videos impact engagement levels. The dataset used consists of 28 days (13/9 to 22/10) of video information sourced from Kaggle. Engagement levels (high, medium, low) were predicted using a Random Forest classifier.

## Research Questions
1. Which attributes of YouTube videos impact engagement levels?
2. How confident is the Random Forest model in predicting engagement levels (low, medium, high)?
3. Do sentiments of tags and comments affect views?

## Data Preprocessing
- **Merging Datasets**: Combined `GBvideos.csv` and `GBcomments.csv` on `video_id` for feature enrichment.
- **Sentiment Analysis**: Used VADER to analyze sentiments of tags and comments, assigning them positive (1), neutral (0), or negative (-1) scores.
- **Feature Encoding**: Applied Label Encoding to categorical features (channel title, video title).
- **Engagement Categorization**: Defined engagement levels based on views:
  - **High**: > 1,000,000 views
  - **Medium**: > 100,000 views
  - **Low**: ≤ 100,000 views
- **Feature Scaling**: Normalized numerical attributes (likes, dislikes, replies) using Min-MaxScaler.

## Model Training and Evaluation
- **Train-Test Split**: 80% training, 20% testing.
- **Model Used**: Random Forest Classifier with 20 estimators.
- **Evaluation Metrics**:
  - Accuracy
  - Classification Report (Precision, Recall, F1-score)
- **Feature Importance Analysis**:
  - SHAP Values for explainability
  - Ensemble Variance to quantify uncertainty

## Key Findings
- **Primary Predictors of Views**: Likes and dislikes were the most influential factors.
- **Limited Impact of Sentiment Analysis**:
  - Tag sentiment had minimal impact.
  - Comment sentiment and replies had no significant effect.
- **Confidence in Predictions**: The model showed near-zero variance in a large portion of predictions, indicating high confidence.
<img width="695" alt="Screenshot 2025-02-18 at 8 24 55 PM" src="https://github.com/user-attachments/assets/1bfc5f86-680b-4d65-bb65-ad34cf812cab" />

## Challenges and Lessons Learned
- **Challenges**:
  - Handling missing values after merging datasets.
  - Encoding text features (tags, comments, titles).
  - Quantifying uncertainty in predictions.
- **Lessons Learned**:
  - Channel and video titles significantly affect engagement and should be carefully chosen by content creators.
  - Likes play a crucial role in determining views, suggesting the importance of early engagement strategies.
  - A more granular sentiment analysis approach (analyzing individual tags separately) could improve model accuracy.
  - The dataset was limited to 28 days, restricting the ability to capture long-term video performance trends.
<img width="592" alt="Screenshot 2025-02-18 at 8 25 11 PM" src="https://github.com/user-attachments/assets/76f57240-f16e-45d6-824e-38338114f447" />

## How to Run
1. **Download Dataset**: Upload files from Kaggle: [https://www.kaggle.com/datasets/datasnaek/youtube/data](https://www.kaggle.com/datasets/datasnaek/youtube/data) to your Google Drive.
2. **Open Project**: Launch `.ipynb` file in Google Colab.
3. **Adjust File Path**: Modify `base_path` to match the dataset location in your Google Drive.

## Dataset Source
- `GBvideos.csv`
- `GBcomments.csv`
- **Kaggle Dataset**: [https://www.kaggle.com/datasets/datasnaek/youtube/data](https://www.kaggle.com/datasets/datasnaek/youtube/data)
