# Dimensionality Reduction
Recognizing patterns from high-dimensional feature space is what Machine Learning Algorithms are used for. Although the capabilities of Machine Learning algorithms to work with higher dimensions are imposing. The peak performance of Machine Learning model declines with expanding dimensions. This paradox is widely known as  **Curse of Dimensionality** .  

With Increase in dimensions, computation cost builds up exponentially. The feature space becomes sparse and it becomes challenging for Machine Learning models to get solid accuracies.  

If we consider columns of our dataset as input features. Inclusion of more columns will result in expansion of volume of our feature space. The points in the feature space i.e. the rows of our dataset will now represent a small and non-representative sample of our database. Our algorithm will not fit the dataset accordingly and will end up with nominal accuracies due to overfitting.  

### Thus, simply put Dimensionality Reduction is techniques / methods that are used to cut down the input features from our training dataset.  
## Frequently used Dimensionality Reduction techniques include:  
### 1. Feature selection  
This method uses statistics to recognize the relation between input feature and target variable of our dataset. Thus features with powerful relationship with the target variables are selected.
Selection of filtering method is done taking into consideration the data type of feature.

Method | Explanation | Techniques
--- | --- | ---- 
Wrapper | This method fits subset of different input features of the training data. subset with the best score is selected. <br> In reality no statistical analysis is performed but combinations are used to find features that will give best scores. | `RFE [Recursive Feature Elimination]` 
Filter | We statistically detect relationship between feature and target. Based on the filter scores we ascertain which features to keep. These methods are type of univariate analysis.<br> **These Methods are datatype specific and should be used accordingly.**<br> datatype include Numeric[N]: Integers & Float<br>Categorical[C]: Boolean, ordinal & nominal | **target -> N & data -> N**<br> `Pearson's correlation` & `Spearson's ranked-based analysis`<br> **target -> N & data -> C**<br> `ANOVA` & `kendall's rank coefficient`<br> **target -> C & data -> C**<br> `chi-squared` & `Mutual Information`
Intrinsic | These methods do feature selection on the training data independently while training. | `Lasso`, `RF` & `XGBoost`  

### 2. Matrix Factorization
Training dataset is assessed as a Matrix by Machine Learning algorithms. These techniques consist of factorizing the training matrix to get factors also called as constituents.  
These subparts are then ranked based on their salient features & scores individually.  

Techniques |  Explanation
--- | --- 
LU matrix decomposition | It is used for square matrix. Training matrix is divided into lower triangular[L] & upper triangular[U] matrix<br> Original matrix is reconstructed by taking dot product.  
QR matrix decomposition |  It is used for m * n matrix. It handles training matrix similar to LU, only difference is this method is used for m * n matrix.
Cholesky Decomposition | This method gives double efficiency than LU decomposition. Here Training matrix is divided like L * L^T or U * U^T
PCA [ Principal Component Analysis] | It belongs to projection type of methods. Here the training matrix with m columns is reduced to a matrix with less than m columns.<br> Essence of the dataset is retained by using simple linear algebra. 

### 3. Auto Encoders
Deep learning model is used for feature selection. Model is trained such that the input is made to compress in a bottleneck version of the input with reduced dimensions.
Part of the model that trains the input is called as encoder and the output part from where bottlenecked version of input is obtained is called as decoder.  

Technique | Explanation 
--- | ---
LSTM Encoders | LSTM models is used for video, text, audio, and time series sequence data. This networks perform unsupervised learning to get compressed representation of the inputs. 

### 4. Manifold Learning  
These methods are taken from high dimension statistics. Main purpose of these techniques was to visualize high-dimensionality data in a low-dimension form. Low-Dimension representation is created by retaining salient-features and relationship between the data.

Methods include:  `Kohonen Self-Organizing Map (SOM)`, `Sammons Mapping`, `Multidimensional Scaling (MDS)`, `t-distributed Stochastic Neighbor Embedding (t-SNE)`.
