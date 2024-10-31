# Machine Learning Course

This repository stores implementations of various methods for data analysis, namely classification methods, regression. In addition, I analyzed datasets with several target variables. The data file contains the data on which the analysis was performed. 

## Regression

First, the gradient descent algorithm was implemented. At the end stochastic gradient descent and mini batch gradient descent were implemented. And tested on the generated data.

![image](https://github.com/user-attachments/assets/3bd1acff-072a-44a1-a8e4-ae3ff3049664)

After that, a dataset was taken in which the target variable is the price of the car. And EDA was made on it. Namely, histograms, boxplot, scatter plot, correlation matrix, barplot were plotted. At the end of the EDA, appropriate conclusions were drawn.

![image](https://github.com/user-attachments/assets/7e8009fc-9ed6-4ea3-b6c4-db77599a669c)

The F-test was used to assess the significance of the factor. 

The data were then divided into training and test samples. Scaling was done.

From the beginning, a linear regression was trained. For clarity, a table was created, with rows (mse-train, mse-test, rmse-train, rmse-test, r2-train, r2-test) and columns (Fold1, Fold2, ..., Foldk, E, STD), where k is the number of folds in the cross-validation, E is the expectation and STD is the standard deviation.
	
					

|           | Fold1          | Fold2         | Fold3      | Fold4      | Fold5      | E          |STD         |
| --------- | -------------- | ------------- | ---------- | ---------- | ---------- | ---------- | ---------- |
| mse-train |6019998.06      |6747838.48     |7694622.60  |12424483.14 |14105183.53 |9398425.16  |3245086.25  |
| mse-test  |4110522.22      |30649890.50    |14923244.48 |6425441.36  |25897156.79 |16401251.07 |10449490.41 |
| rmse-train|2453.57         |2597.66	       |2773.92	    |3524.84	   |3755.69	    |3021.14	   |520.74      |
| rmse-test |2027.44         |5536.23	       |3863.06	    |2534.85	   |5088.92	    |3810.10	   |1372.72     |
| r2-train  |0.85	           |0.80	         |0.88	      |0.83	       |0.84	      |0.84	       |0.03        |
| r2-test   |0.93	           |0.78	         |0.70	      |0.64	       |0.63	      |0.74        |0.11        |


Before training the models, the best number (and subset) of features is selected using Recursive Feature Elimination (RFE) from sklearn.

Several models were trained on the preprocessed data using cross-validation: ridge, linear regression, gradient descent implementations, SGD, mini-batch GD.

|           | LinearRegression | Ridge         | GD         | SGD        | Mini Batch GD |
| --------- | ---------------- | ------------- | ---------- | ---------- | ------------- |
| mse-train |9398425.16	       |9400253.57     |15467407.87 |15710189.60 |15479804.84    |
| mse-test  |16401251.07       |16363658.37    |22827048.63 |22938890.30 |22710667.56    |
| rmse-train|3021.13	       |3021.30	       |3932.86	    |3963.61	 |3934.44        |
| rmse-test |3810.10	       |3806.53	       |4777.77	    |4789.46	 |4765.57        |
| r2-train  |0.84              |0.84	       |0.75	    |0.74	 |0.75           |
| r2-test   |0.74              |0.74	       |0.67	    |0.67	 |0.67           |


