### **Evaluation of Kappa Coefficient and Overall Accuracy**





#### **Metrics:**
1. **Kappa Coefficient**: Measures above-chance agreement in classifications. The closer to 1, the better, and below 0 reflects random performance.
2. **Overall Accuracy**: A measure of the proportion of correctly classified instances. More desirable values are closer to 1.

---

### **WindowSize Filter Performance**


#### **3x3 Filters**
**Best: Local Sigma**
- **Kappa 0.693** as well as **Overall Accuracy 0.753**, both highest among all filters.
- Suggests better performance in classification agreement and accuracy.
 
- **Worst: Kuan**
  - **Kappa (-0.0004)** and **Overall Accuracy (0.219)** suggest the worst performance.
  - Indicates random behavior in classification.
 
#### **5x5 Filters**
- **Best: Local Sigma**
  - **Kappa (0.6602)** and **Overall Accuracy (0.728)** still suggests its excellent performance.
  - Marginal drop from the 3x3 window but still better than other filters.
 
- **Worst: Kuan**
- **Kappa (-0.0504)** and **Overall Accuracy (0.092)** are still very low and do not improve with window size.

#### **7x7 Filters**
- **Best: Local Sigma**
  - **Kappa (0.6448)** and **Overall Accuracy (0.717)** are strong and show consistent performance for all window sizes.
  
- **Worst: Kuan**
  - **Kappa (-0.0496)** and **Overall Accuracy (0.085)** are indicative of continued poor performance.

#### **9x9 Filters**
- **Best: Local Sigma**
- **Kappa (0.6314)** and **Overall Accuracy (0.707)** degrade but are still the highest.
 
-Worst: Kuan
-Kappa (-0.0496) and Overall Accuracy (0.085) remains the same, which reflects that these filters are not good.

-----

### Filter Performance Across All Window Sizes

#### Best Performing Filters:
1. Local Sigma
   Always highest Kappa and Overall Accuracy across all window sizes.
- Shows slight performance drop with increasing window size but remains effective.

2. **Lee**
   - Second best in most cases with **Kappa** values ranging from 0.6458 to 0.6693.
   - Slightly outperformed by Local Sigma in larger window sizes.

3. **Gaussian LPF (3x3)**
   - **Kappa (0.606)** and **Overall Accuracy (0.682)** show good classification capability, especially for the smallest window.

---

#### **Worst Performing Filters:**
1. **Kuan**
- Negative values of **Kappa** for all window sizes.
   - The **Overall Accuracy** improves very less and remains below 0.22 for all the sizes.

2. **Frost & Gamma**
   - Poor **Kappa** and **Overall Accuracy** values.
   - The larger the window size, performance degrades.

3. **Median**
   - Noise reduction is good; classification performance is poor.
- **Kappa** lies between 0.1449 and 0.2078, and **Overall Accuracy** is still below 0.33.

---

### Window Size Effect

- **Local Sigma, Lee**, have strong performance for all sizes, so these are probably very robust.
- **Median, Enhanced Frost, Gamma**, begin to degrade as window size increases; possibly because over-smoothing is too destructive.
- Larger window sizes often compromise accuracy for most filters, indicating a tradeoff between noise reduction and the quality of classification.

---
### **Conclusion**
- **Best Performer**: Local Sigma with all sizes but especially 3x3 offers the best compromise between classification accuracy and robustness.
- **Worst Performer**: Kuan Filter, as it always ranks worst and has negative Kappa values and low accuracy in classification.
Recommendation: Use Local Sigma or Lee filters with a smaller window size of 3x3 or 5x5 for best results in terms of accuracy and classification.
