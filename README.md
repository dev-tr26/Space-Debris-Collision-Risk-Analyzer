# -Space-Debris-Collision-Risk-Analyzer

## Project Overview
This experiment uses a custom dataset of over 300 satellite objects, manually curated and transformed into TLE format, to calculate 3D distances and train a Random Forest Classifier. The goal is to identify satellite pairs with a collision risk (defined as a distance < 10 km) and evaluate the model's performance through metrics like accuracy, precision, recall, and F1-score. The project integrates the Skyfield API for precise orbital computations and explores data preprocessing, model training, and web interface development using Django.

### Key Features
- **Data Preparation**: Manually collected and converted orbital elements (e.g., MEAN_MOTION, INCLINATION, ECCENTRICITY) from a CSV dataset into standardized TLEs, saved as a JSON file for reuse.
- **Orbital Calculations**: Utilized the Skyfield API to compute geocentric 3D positions of over 44,850 satellite pairs, handling complex distance calculations at a specified epoch (March 10, 2025).
- **Machine Learning**: Trained a Random Forest Classifier on paired orbital features, achieving initial metrics of Accuracy: 1.00, Precision: 0.97, Recall: 0.75, and F1-Score: 0.84, with ongoing efforts to address potential imbalance.



## Results
- **TLE Construction**: Explored mapping dataset columns to TLE fields, addressing challenges like epoch formatting and checksum validation.
- **Distance Calculation**: Processed 44,850 pairs, debugging issues like empty feature arrays (`ValueError`) and ensuring 2D data shapes for ML.
- **Model Evaluation**: Initial metrics suggest high precision but moderate recall, indicating potential overfitting to a majority "no risk" class. Current efforts include class weighting and threshold tuning.
- Due to biased data the model is overfitted.

