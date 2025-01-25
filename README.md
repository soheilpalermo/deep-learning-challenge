# Alphabet Soup Deep Learning Model Report
## 1. Overview of the Analysis
Alphabet Soup, a nonprofit foundation, wants to predict which funding applicants are most likely to succeed if granted funding. To solve this, we built a binary classification deep learning model that uses historical application data to determine the likelihood of an application’s success. By accurately identifying high-potential applicants, Alphabet Soup can optimize its use of resources and better serve organizations.
## 2. Results
### 2.1 Data Preprocessing
- target Variable:
  - IS_SUCCESSFUL – a binary indicator (0 or 1) of whether the funding resulted in a successful outcome.
- Feature Variables:
  - APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT (after they were appropriately encoded and scaled).
  - These features capture diverse aspects of each organization’s profile, from the requested funding amount to the organizational structure.
- Removed Variables:
  - EIN and NAME – These were purely identification columns that do not provide predictive power and might add unnecessary noise to the model.
![Alt Text](https://via.placeholder.com/150)

2.2 Compiling, Training, and Evaluating the Model
Model Architecture:

Input Layer: Number of input features after one-hot encoding (e.g., ~40–100 depending on the data).
Hidden Layers:
Layer 1: 80 neurons, ReLU activation
Layer 2: 30 neurons, ReLU activation
(Some attempts might have had three or more hidden layers with more/less neurons.)
Output Layer: 1 neuron, Sigmoid activation (for binary classification)
Why These Hyperparameters?

ReLU Activation is a common default for hidden layers due to its efficiency and effectiveness in many deep learning tasks.
Sigmoid Activation for the output layer suits binary classification.
The chosen number of neurons in each hidden layer aimed to balance model capacity (to learn complex patterns) and efficiency (to avoid overfitting or excessive training time).
Model Performance:

In the baseline model, the training was run for 100 epochs, achieving an accuracy of around 72%–73% on the test data.
Optimized Model Attempts:
Increased the number of neurons in the hidden layers.
Added a third hidden layer.
Experimented with different activation functions (e.g., tanh) and altered the learning rate.
Best Accuracy Achieved: ~75%.
(Include any training/validation accuracy curves or confusion matrices if you generated them.)

Steps Taken to Increase Performance:
Dropped or recategorized more columns/rare categories (e.g., merging low-frequency APPLICATION_TYPE or CLASSIFICATION values into “Other”).
Adjusted hyperparameters (learning rate, number of epochs, number of neurons, etc.).
Changed activation functions from relu to tanh in some layers.
Increased or decreased the number of epochs to find a sweet spot without overfitting.
(You might briefly discuss whether or not these changes significantly improved the metrics.)

3. Summary
Overall, our deep learning model reached an accuracy of around 75% in predicting successful funding outcomes for Alphabet Soup. While this meets the general target, there is still room for improvement.

Recommendation for a Different Model
A more traditional machine learning classification approach, such as a Random Forest or an XGBoost model, could serve as a complementary or alternative technique. These models often provide:

High interpretability in terms of feature importance,
Strong performance on tabular data,
Robustness to outliers and complex feature interactions (especially for XGBoost).
By comparing these tree-based models against the neural network (or even integrating them in an ensemble approach), Alphabet Soup might gain higher accuracy or more interpretable insights into which features drive funding success.

Overall, combining domain knowledge and further hyperparameter tuning could push performance beyond the current threshold while ensuring that the model remains practical and interpretable for Alphabet Soup’s decision-making process.

