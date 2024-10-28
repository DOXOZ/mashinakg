

# Car Price Prediction Project

### Overview

This project is designed to scrape car advertisements from [Mashina.kg](https://www.mashina.kg/) for a specified car brand. After collecting the data, it prepares the dataset and trains a linear regression model to predict car prices based on various features. This project demonstrates data scraping, cleaning, and simple machine learning modeling.

### Features Scraped

The following attributes are extracted for each car listing:
- **Model** - Car model
- **Year of Production** - Manufacture year
- **Engine Volume** - Engine capacity in liters
- **Mileage** - Total distance driven
- **Fuel** - Fuel type (e.g., gasoline, diesel)
- **Gearbox** - Transmission type (automatic/manual)
- **Steering Wheel** - Location of the steering wheel (left/right)
- **Color** - Car color
- **Body Type** - Car body type (e.g., sedan, SUV)
- **Location** - City where the car is located
- **Price in USD** - Car price in US dollars

---

### Project Workflow

1. **Data Scraping**
   - Fetches listings from the `Mashina.kg` website.
   - Extracts relevant information from the HTML structure using BeautifulSoup and stores it in a DataFrame.

2. **Data Preparation**
   - Converts numerical data columns to the appropriate data types.
   - Handles missing values by imputing mean/mode or dropping, depending on the column.
   - Encodes categorical variables (e.g., steering wheel location as 0 for left, 1 for right).
   - Creates dummy variables for columns with more than two categories (e.g., fuel type, color).

3. **Model Building**
   - Trains a linear regression model to predict car prices with features excluding price as `X` and price as `y`.
   - Evaluates model performance using coefficient interpretation.

4. **Questions Answered**
   - Analyzes how various factors (year, mileage, steering wheel location, engine volume) impact car price based on model coefficients.

---

### Installation and Setup

#### Prerequisites
- Python 3.x
- Libraries:
  - `pandas`
  - `beautifulsoup4`
  - `requests`
  - `scikit-learn`

#### Installation
Install the required libraries with:
```bash
pip install pandas beautifulsoup4 requests scikit-learn
```

### Usage

1. **Run the Scraper**
   - The scraper iterates through pages on `Mashina.kg` and collects data for the specified brand.
   - Set up the car brand and other parameters within the code.

2. **Prepare Data**
   - Ensure the scraped data is clean and suitable for modeling by running the data preparation cells.

3. **Train Model**
   - Run the cells to fit the model and analyze the coefficients to interpret feature influence on price.

### Example Notebook Structure

- **Cells 1-5**: Scraper initialization and setup.
- **Cells 6-12**: Data collection and storage in DataFrame.
- **Cells 13-18**: Data cleaning, transformation, and preparation.
- **Cells 19-25**: Model training, evaluation, and coefficient interpretation.

### Results and Interpretation
The model coefficients provide insights into how each feature affects car prices. For instance:
- The year of manufacture typically has a negative coefficient, indicating older cars are valued less.
- Mileage shows a negative impact as well, with higher mileage leading to lower prices.

