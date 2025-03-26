# Sentiment Analysis and Text Mining on Amazon Fine Food Reviews

## Project Overview
Customer reviews are a valuable source of feedback in e-commerce, but their volume makes manual analysis challenging. This project focused on automating sentiment analysis and thematic clustering of Amazon Fine Food Reviews using text mining. The dataset, included 568,454 reviews from October 1999 to October 2012, covering 256,059 users and 74,258 products. We used SAS Enterprise Miner to build unsupervised and supervised models, extracting insights to help businesses understand customer preferences and address pain points.

## What We Did
1. **Data Description**:
   - Key variables:
     - `Product ID`, `User ID`: Unique identifiers.
     - `Score`: Rating (1-5).
     - `Text`: Review text.
     - `Summary`: Brief review summary.
     - `Time`: Timestamp of the review.

2. **Data Preprocessing**:
   - Confirmed the dataset had no missing values.
   - Partitioned the data into 50% training, 30% validation, and 20% testing sets for model development and evaluation.
   - Applied text parsing to filter out irrelevant words (e.g., auxiliary verbs, conjunctions) using a stop list, focusing on meaningful terms for sentiment analysis.

3. **Unsupervised Model (Clustering)**:
   - Categorized reviews into positive (scores 4-5) and negative (scores 1-3) groups.
   - Used text filtering with Log frequency weight and IDF/Entropy term weights to refine the data.
   - Performed cluster analysis to identify themes:
     - Positive clusters: Themes like "cheap" (affordable products) and "organic" (natural, sustainable choices).
     - Negative clusters: Themes like "smell" (unpleasant odors) and "expiration" (short shelf life concerns).

4. **Supervised Model (Sentiment Classification)**:
   - Built a rule-based classifier to label reviews as "Positive" (score > 4) or "Negative" (score < 3).
   - Applied text parsing and filtering, using Log frequency weight and Entropy term weight for better performance.
   - Used Singular Value Decomposition (SVD) with 100 dimensions to reduce data complexity while retaining key features.
   - Tested multiple models (Decision Tree, Regression, Neural Network) with different settings (Log-IDF, Log-Entropy, low/high SVD resolution).
   - Selected the Neural Network model with Log-Entropy, high SVD resolution as the best, achieving a test ROC index of 0.849 and a misclassification rate of 16.5%.

5. **Final Model**:
   - Combined the best settings (Log frequency weight, Entropy term weight, SVD 100 dimensions, high resolution) into a final model.
   - Achieved a test ROC index of 0.857 and a misclassification rate of 16%.

6. **Business Insights and Recommendations**:
   - **Insights**:
     - Positive sentiments often included terms like "good" and "love," indicating customer satisfaction.
     - Negative sentiments highlighted issues like unpleasant smells and short expiration dates.
     - Businesses can use positive terms in marketing to enhance brand perception.
     - Addressing negative feedback (e.g., improving product freshness) can improve customer satisfaction.
   - **Recommendations**:
     - Invest in quality improvements to address concerns about smells and expiration.
     - Communicate clearly about expiration dates to build trust.
     - Engage with customers to address negative feedback and improve experiences.
     - Use positive terms like "good" and "love" in marketing to reinforce brand image.
## Results and Metrics
- **Best Model**: Neural Network with Log-Entropy, high SVD resolution.
- **Performance**:
  - Test ROC Index: 0.849 (initial model), improved to 0.857 in the final model.
  - Test Misclassification Rate: 16.5% (initial model), 16% (final model).
- **Key Findings**:
  - Positive reviews often praised affordability ("cheap") and natural qualities ("organic").
  - Negative reviews highlighted issues with smells and expiration dates.
  - The model effectively classified sentiments, providing insights into customer preferences.

## Why We Chose This Approach
- **Neural Network Selection**: Chosen for its high ROC index (0.849, improved to 0.857) and low misclassification rate (16%), balancing accuracy and performance.
- **Log-Entropy Settings**: Selected for better model performance compared to Log-IDF, as shown by a lower misclassification rate.
- **SVD with 100 Dimensions**: Used to reduce data complexity while retaining key features for clustering and classification.


## Note on Posting Delay
This project was completed in Spring 2023 as part of the OPIM 5671 course at the University of Connecticut. However, due to the loss of the original project files, sharing it on LinkedIn and GitHub in 2025 after recovering and finalizing the work. The analysis, modeling, and results reflect our efforts from 2023, showcasing our approach to text mining and sentiment analysis at that time.
