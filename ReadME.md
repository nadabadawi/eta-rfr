### To predict ETA from the time the driver gets assigned to a driver to when it gets delivered, Careem's data goes through 4 steps:

(If data is already clean and split you can start from step 2)

#### 1. Data Cleaning and Splitting:
  Where incomplete trips are removed, data is reformatted for the models, and trips are split into 3 segments (Driver-to-Merchant, Wait-Time-at-Merchant, Merchant-to-Customer).
#### 2. Clustering and RFR
  Where STING clusetering is applied to geoencode data, and road segments are given to a Random Forest Regressor model to predict the times for segments 1 and 3.
#### 3. XGBoost
  Where the second segment from the trips (Wait-Time-at-Merchant) is given to an XGBoost model, to predict driver wait times and observe merchant behavior.
#### 4. Linear Regressor
  Where the predictions from the first 2 models are given as input to a Linear Regressor to predict the overall ETA for a trip, while observing which segments carry more importance towards the ETA.
  
![image](https://github.com/user-attachments/assets/10a90d89-c2c9-4cb4-bac9-519ce6a19a6d)

