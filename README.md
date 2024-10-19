# Bengaluru Home Price Prediction

## Overview
This project utilizes machine learning to predict property prices in Bengaluru based on features such as location, property type, size, and amenities. It's designed for home buyers, sellers, and real estate professionals.

## Technologies Used
- **Language**: Python
- **Libraries**: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn

## Dataset
The dataset includes:
- **location**: Area of the property
- **size**: Property type (e.g., 2 BHK)
- **total_sqft**: Area in square feet
- **bath**: Number of bathrooms
- **price**: Price in lakhs
- **bhk**: Number of bedrooms

## Data Preprocessing
1. Cleaned data and standardized location names.
2. Added `price_per_sqft`: `data['price_per_sqft'] = data['price'] * 100000 / data['total_sqft']`.
3. Grouped infrequent locations as "other".

## Outlier Handling
- **Business Logic**: Removed properties with unrealistic sqft per bedroom ratios.
- **Statistical Techniques**: Eliminated outliers based on standard deviation from the mean price per sqft and validated pricing consistency across BHK categories.

## Modeling Approach
- Used Linear Regression after comparing various models (Lasso, Decision Tree).
- Achieved an R-squared score of approximately 0.86, indicating strong predictive capability.

## Usage
To predict property prices:
```python
def predict_price(location, sqft, bath, bhk):
    # Prediction logic here

predicted_price = predict_price('1st Phase JP Nagar', 1000, 2, 2)
print(f"Predicted Price: {predicted_price} lakhs")
