---
type: concept
domain: machine-learning
category: preprocessing
status: evergreen
---

# Feature Encoding

> Feature encoding is the process of converting **categorical variables** into numerical representations that machine learning algorithms can understand.

---

## 1. Core Idea

Most ML algorithms operate on numbers, not categories.

Feature encoding:
- Translates categorical values into numeric form
- Preserves (or approximates) the underlying information
- Enables algorithms to learn from categorical data

---

## 2. Why Feature Encoding Is Necessary

Without proper encoding:
- Models cannot process categorical features
- Artificial ordering may be introduced
- Distance- and gradient-based methods break

Encoding directly affects **model performance and validity**.

---

## 3. Types of Categorical Variables

### Nominal
- No inherent order  
- Example: color, city, gender

### Ordinal
- Natural order exists  
- Example: low / medium / high, education level

Correct encoding depends on the type.

---

## 4. Common Feature Encoding Techniques

---

### 4.1 Label Encoding

Assigns an integer to each category.

- Simple
- Introduces artificial order

Best for:
- Tree-based models
- Ordinal categories (with care)

🔗 Related:
- [[Decision Tree Classifier]]

---

### 4.2 One-Hot Encoding

Creates binary indicator columns for each category.

- No artificial ordering
- Increases dimensionality

Best for:
- Linear models
- Logistic Regression
- Small to medium cardinality features

🔗 Related:
- [[Linear Models — MOC]]
- [[Logistic Regression]]

---

### 4.3 Ordinal Encoding

Encodes categories according to a known order.

- Preserves rank information
- Requires domain knowledge

Best for:
- Ordered categories

---

### 4.4 Target Encoding (Mean Encoding)

Encodes categories using target statistics.

- Powerful
- High risk of data leakage if done incorrectly

Best for:
- High-cardinality features
- Boosting models (with care)

🔗 Related:
- [[Target Encoding]]
- [[Data Leakage]]

---

### 4.5 Frequency / Count Encoding

Encodes categories by their frequency.

- Simple
- No target leakage
- Loses class-specific information

Best for:
- High-cardinality categorical variables

---

### 4.6 Binary Encoding

Encodes categories using binary digits.

- Reduces dimensionality
- Compromise between label & one-hot encoding

Best for:
- Very high cardinality features

---

## 5. Algorithm-Specific Encoding Preferences

| Algorithm Family | Preferred Encoding |
|----------------|--------------------|
| Linear Models | One-Hot |
| Logistic Regression | One-Hot |
| k-NN | One-Hot (after scaling) |
| SVM | One-Hot |
| Tree-Based Models | Label / Ordinal |
| Random Forest | Label |
| Gradient Boosting | Label / Target |
| XGBoost | Label / Target |
| LightGBM | Native categorical / Label |
| CatBoost | Native categorical |

---

## 6. Native Categorical Handling

Some algorithms handle categorical variables internally:

- LightGBM
- CatBoost

These models:
- Avoid explicit encoding
- Reduce leakage risk
- Improve performance on categorical-heavy data

🔗 Related:
- [[LightGBM Classifier]]
- [[CatBoost Classifier]]

---

## 7. Feature Encoding and Data Leakage ⚠️

High-risk encodings:
- Target encoding
- Mean encoding
- Aggregation-based encodings

Correct workflow:
1. Split data
2. Fit encoder on training set only
3. Apply to validation/test sets

🔗 Core concept:
- [[Data Leakage]]

---

## 8. Feature Encoding and Feature Scaling

- One-hot encoded features often require scaling
- Label encoded features usually do not
- Distance-based models are sensitive to encoding choice

🔗 Related:
- [[Feature Scaling]]
- [[Distance-Based Models — MOC]]

---

## 9. Feature Encoding and Model Interpretability

- One-hot encoding → clearer interpretation
- Target encoding → harder to explain
- Tree-based models abstract encoding internally

---

## 10. Common Mistakes

- ❌ Label encoding nominal variables for linear models  
- ❌ One-hot encoding very high-cardinality features  
- ❌ Target encoding before data split  
- ❌ Ignoring domain meaning of categories  

Encoding mistakes silently degrade models.

---

## 11. How to Choose an Encoding Method

Ask:
1. Is the variable nominal or ordinal?
2. What algorithm am I using?
3. What is the feature cardinality?
4. Is leakage possible?

There is no universal best encoding.

---

## 12. Why Feature Encoding Matters

Feature encoding determines:
- Whether the model learns meaningful patterns
- Whether distances and similarities make sense
- Whether leakage occurs
- Whether performance is stable

It is **as important as model choice**.

---

## Usage Notes

- Link this note from:
  - Feature Scaling
  - Data Leakage
  - Tree-Based Models
  - Linear Models
  - Boosting Models
- Do NOT duplicate encoding explanations elsewhere
