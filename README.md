### **Black-Scholes Model Correction and Market Analysis**
#### *A Data-Driven Approach to Enhancing Option Pricing with Entropy and Nonlinear Techniques*

---

## **Overview**
The **Black-Scholes model** is one of the most widely used frameworks for pricing options, yet it is known to exhibit **systematic biases** due to simplifying assumptions, such as constant volatility and frictionless markets. This project investigates these pricing discrepancies, identifies patterns in **pricing errors**, and introduces **entropy-based corrections** and **nonlinear modeling techniques** to improve pricing accuracy. 

We explore how **market uncertainty**, measured via entropy, influences pricing deviations and evaluate the impact of these corrections across different **volatility regimes**. Additionally, we backtest a **trading strategy** based on the corrected model to assess its potential profitability.

---

## **Data Source**
The dataset used in this project was sourced from **Kaggle**, containing historical options pricing data, including:
- **Bid-Ask Spreads** (Market prices traders are willing to buy/sell at)
- **Implied Volatility** (Market expectations of future volatility)
- **Market Conditions** (Price movements, trading volume, etc.)

This data provides a **realistic testbed** for evaluating the performance of theoretical models like Black-Scholes against actual market conditions.

---

## **Project Goals**
This project aims to:
1. **Analyze Pricing Errors** – Identify systematic biases in the Black-Scholes pricing model by comparing theoretical and observed market prices.
2. **Entropy as a Market Uncertainty Measure** – Investigate the role of entropy in quantifying unpredictable market behavior.
3. **Fourier and Wavelet Analysis** – Detect periodic structures and hidden market dynamics within pricing errors.
4. **Develop a Corrected Pricing Model** – Introduce entropy-based and nonlinear transformations of implied volatility to refine the Black-Scholes predictions.
5. **Evaluate Performance Across Volatility Regimes** – Study how pricing errors vary in low, medium, and high volatility markets.
6. **Backtest a Trading Strategy** – Assess whether the corrected model can systematically exploit market inefficiencies for profitable trading.

---

## **Key Findings and Analysis**

### **1. Understanding Pricing Errors in the Black-Scholes Model**
The first step in this study involved computing the **pricing errors** (deviations between market prices and Black-Scholes estimates). A histogram of these errors reveals a highly **skewed distribution**, indicating the presence of systematic biases.

![Pricing Errors Histogram](images/Screenshot2025-03-08184256.png)

- The Black-Scholes model performs reasonably well for most data points (concentrated around zero error).
- However, significant deviations exist, particularly in extreme cases, where volatility assumptions may be invalid.

---

### **2. Market Uncertainty Through Entropy**
To better understand these errors, we introduced **entropy** as a measure of market uncertainty. Higher entropy suggests **greater unpredictability**, leading to larger pricing deviations.

#### **Rolling Entropy vs. Implied Volatility**
We computed a **rolling entropy measure** and compared it against implied volatility. Interestingly, **entropy fluctuations align with shifts in implied volatility**, reinforcing the idea that pricing errors are linked to broader market uncertainty.

![Rolling Entropy vs. Implied Volatility](images/Screenshot2025-03-08191210.png)

- Higher entropy correlates with periods of **greater volatility and mispricing**.
- This suggests that entropy-based corrections may help **adjust for systematic pricing errors**.

---

### **3. Frequency Analysis: Detecting Hidden Patterns in Pricing Errors**
We performed **Fourier Transform and Wavelet Analysis** to uncover hidden structures in pricing errors.

#### **Fourier Transform Findings**
A **Fourier transform** of the pricing error data reveals **dominant low-frequency components**, indicating that pricing errors are not random but exhibit structured trends.

![Detrended Fourier Transform](images/Screenshot2025-03-08191754.png)

#### **Wavelet Power Spectrum**
Wavelet analysis further highlights **localized fluctuations** over time, suggesting **nonstationary behavior in pricing errors**.

![Wavelet Power Spectrum](images/Screenshot2025-03-08194807.png)

---

### **4. Developing a Corrected Pricing Model**
We introduced **entropy-based and nonlinear corrections** to refine the Black-Scholes predictions.

#### **OLS Regression with Entropy Correction**
A simple **Ordinary Least Squares (OLS) regression** incorporating entropy significantly **improved the explanatory power of the model**, capturing market uncertainty more effectively.

![OLS with Entropy](images/Screenshot2025-03-08200440.png)

#### **Nonlinear Model with Implied Volatility Interactions**
We further extended the model to include **squared and interaction terms** of implied volatility and entropy.

![Nonlinear Model](images/Screenshot2025-03-08200737.png)

- The **nonlinear model** captures price deviations **more effectively than a linear correction**.
- This suggests that **market inefficiencies have a nonlinear structure** that must be accounted for in pricing models.

---

### **5. Evaluating Model Performance Across Volatility Regimes**
We classified the dataset into **low, medium, and high volatility regimes** and examined pricing error distributions before and after applying the corrections.

#### **Before Correction:**
![Violin Plot - Uncorrected](images/Screenshot2025-03-08200948.png)

- **High-volatility regimes** show greater pricing errors.
- The Black-Scholes model underperforms in volatile markets.

#### **After Entropy-Based Correction:**
![Violin Plot - Corrected](images/Screenshot2025-03-08201359.png)

- The corrected model **reduces errors**, especially in high-volatility conditions.
- This suggests that **entropy-based corrections improve pricing consistency**.

---

### **6. Backtesting a Trading Strategy**
Finally, we implemented a **backtesting framework** to evaluate whether a trading strategy based on the corrected model could systematically profit from mispricings.

![Backtest Results](images/Screenshot2025-03-08201545.png)

- **Cumulative profit trends suggest that corrected pricing improves trade profitability**.
- The strategy successfully exploits **systematic inefficiencies** in option pricing.

---

## **Conclusion**
### **Key Takeaways**
✅ The **Black-Scholes model exhibits systematic pricing biases**, particularly in high-volatility markets.  
✅ **Entropy serves as an effective measure of market uncertainty**, aligning with implied volatility fluctuations.  
✅ **Fourier and wavelet analyses** reveal **structured, nonrandom** behavior in pricing errors.  
✅ **Entropy-based and nonlinear corrections** significantly improve pricing accuracy.  
✅ A **trading strategy based on the corrected model** shows **promising profitability**, highlighting practical applications.

### **Future Directions**
🚀 **Refining the Entropy Measure** – Experiment with alternative entropy formulations for better predictive power.  
🚀 **Machine Learning Enhancements** – Introduce deep learning or reinforcement learning for improved corrections.  
🚀 **Applying to Other Asset Classes** – Extend this approach to **cryptocurrencies or exotic options**.  

---

## **How to Use This Repository**
1. Clone the repository:
   ```bash
   git clone https://github.com/bobovski66/BlackScholesEntropy.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook for step-by-step execution.

