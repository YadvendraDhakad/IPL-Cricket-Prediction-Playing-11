# 📊 Project Report: IPL Cricket Prediction – Playing 11  

## **1. Introduction**  
The Indian Premier League (IPL) is one of the biggest cricket tournaments in the world, where team selection plays a crucial role in winning matches. Predicting the **Playing 11** for each team is a challenging task as it depends on multiple factors such as player form, venue, pitch conditions, and opposition.  

This project aims to use **machine learning and data analysis** to predict the **probability of a player being included in the Playing 11** and suggest the optimal team combination.  

---

## **2. Objectives**  
- Predict if a player will play in an upcoming match.  
- Suggest an **optimal Playing 11** based on probabilities.  
- Incorporate player performance, match conditions, and recent form.  
- Provide insights useful for teams, analysts, and even fantasy cricket.  

---

## **3. Data Collection**  
The dataset was collected from:  
- **Kaggle IPL Dataset** (ball-by-ball and match stats).  
- **ESPN Cricinfo & IPL Website** (player performance, injuries, squads).  

**Data Features:**  
- Player Information: name, role (batsman, bowler, all-rounder, wicketkeeper).  
- Batting Statistics: runs, balls faced, batting average, strike rate.  
- Bowling Statistics: wickets, overs, economy rate.  
- Match Information: venue, date, opponent, toss, pitch type.  
- Recent Form: last 5 match performance.  
- Label: **Played (1)** if player was in the Playing 11, **Not Played (0)** otherwise.  

---

## **4. Data Preprocessing**  
Steps taken to clean and prepare data:  
1. **Missing Values Handling** – Filled numerical values with 0, dropped invalid rows.  
2. **Feature Engineering:**  
   - **Batting Average** = Runs / Dismissals  
   - **Strike Rate** = (Runs / Balls) × 100  
   - **Bowling Form** = Avg wickets in last 5 matches  
   - **Batting Form** = Avg runs in last 5 matches  
   - **Home Advantage** = 1 if match at home, else 0  
   - **Opponent Encoding** = Label Encoding for opponent team names  
3. **Label Creation:**  
   - `Played = 1` if player was in match, `0` otherwise  

---

## **5. Methodology**  

### **Problem Type:**  
- **Classification** → Will player play? (Yes/No)  

### **Machine Learning Models Used:**  
- Logistic Regression  
- Random Forest Classifier  
- XGBoost (for boosting performance)  

### **Model Workflow:**  
1. Input Player + Match Features  
2. Train/Test Split (80/20)  
3. Train Random Forest Classifier  
4. Predict probability for each player  
5. Select top 11 based on probability & role constraints (5 batsmen, 1 keeper, 4 bowlers, 1 all-rounder)  



## 6. Implementation

The implementation of the **IPL Playing 11 Prediction Project** involves the following steps:

1. **Data Collection**  
   - Collected IPL player statistics from Kaggle/ESPN Cricinfo datasets.  
   - Datasets included batting averages, strike rates, wickets, economy rates, match dates, teams, and venues.  

2. **Data Preprocessing**  
   - Loaded data using **Pandas**.  
   - Cleaned missing values using `.fillna()` and row-dropping techniques.  
   - Renamed columns for consistency (`batting_avg`, `strike_rate`, `wickets`, `economy`).  
   - Created additional features:
     - **Recent Form (last 5 matches average)**
     - **Home/Away factor**
     - **Opponent Team**
     - **Pitch Type** (if available)  

3. **Feature Engineering**  
   - Numerical Features: Batting average, strike rate, wickets, economy rate.  
   - Derived Features: Rolling averages for last 5 matches.  
   - Categorical Features: Encoded opponent teams, venues, and pitch types.  
   - Target Variable: `played` (1 if player played, 0 otherwise).  

4. **Model Training**  
   - Split data into **Training (80%)** and **Testing (20%)** sets.  
   - Applied **Logistic Regression** and **Random Forest Classifier** for prediction.  
   - Evaluated models using **Accuracy, Precision, Recall, and F1-score**.  

5. **Prediction**  
   - Generated probability scores for each player.  
   - Selected top 11 players with highest probabilities as the **Predicted Playing 11**.  

---
## 7. Results

- **Model Accuracy:** ~75–80% (depending on dataset quality).  
- Provides a **probability score** for each player.  
- Suggests a **Playing 11** that often matches real selections.  

### Example Output:

| Player Name       | Probability | Role         |
|-------------------|-------------|--------------|
| Virat Kohli       | 0.95        | Batsman      |
| Faf du Plessis    | 0.93        | Batsman      |
| Glenn Maxwell     | 0.91        | All-Rounder  |
| Dinesh Karthik    | 0.88        | Wicketkeeper |
| Mohammed Siraj    | 0.86        | Bowler       |

---

## 8. Applications

- Helps **coaches and analysts** in decision-making.  
- Can be used for **fantasy cricket predictions**.  
- Provides **insights into player form** and **team balance**.  

---

## 9. Future Improvements

- Include **live injury updates & last-minute news** (via web scraping from ESPN Cricinfo).  
- Add **Deep Learning models (LSTM/RNN)** to track player form trends.  
- Build a **Streamlit Web App** for interactive Playing 11 prediction.  
- Extend to **fantasy point predictions** for Dream11/other fantasy leagues.  

---

## 10. Conclusion

This project successfully demonstrates how **Machine Learning** can be applied in **sports analytics** to predict the **Playing 11 in IPL matches**.  

By using **player stats, recent form, and match conditions**, the model achieves **reasonable prediction accuracy** and can be enhanced further with:  
- **Real-time data**  
- **Advanced modeling techniques**  
- **User-friendly applications (Web/App)**  

---

## 📌 Project Deliverables

1. **Python Code** (Jupyter Notebook / `.py` file)  
2. **Dataset** (Kaggle IPL Stats / manually curated)  
3. **Documentation** (Markdown Report in Jupyter Notebook)  

