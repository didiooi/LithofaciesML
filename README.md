# Ensemble Learning Approach to Lithofacies Classification Using Well Logs
* *for Janet Watson 2018 Big Data Explosion Meeting*  

Didi Ooi, Licheng Zhang, Cheng Zhan  
Email: didi.ooi@bristol.ac.uk  

[**Link**](https://github.com/seg/2016-ml-contest/tree/master/HouMath) to SEG ML Contest organized by Matt Hall and Brendon Hall.


## Abstract for Technical Talk  

This talk presents a geologic facies classification using a supervised machine learning gradient boosting classifier, implemented in scikit-learn. With over 4000 training examples based on 7 predictor variables from logs in ten wells and over 800 test data in two wells to predict 9 different facies classes from a carbonate gas reservoir, the classifier algorithm resulted in F1 score of 0.630.  

Geoscientists have been analyzing extensive amounts of data over the years. The proliferation of computing power, open-source tools and robust algorithms have made the process more robust and efficient.  Facies classification consists of assigning a rock type based on measured properties from indirect measurement (i.e. wireline logs) and/or direct study of the cores. However, core sampling is often not ideal budget-wise and conventional lithofacies classification by human interpreters is very time-consuming. Alternative methods using machine learning with neural networks have been proposed by Busch et al. (1987), but this technique is yet to be exploited due to constraints in computing power.  

We propose the use of a meta-algorithm method called ensemble learning which combines several machine learning techniques to enhance the model’s predictive accuracy. This algorithm was applied through participation of the SEG Machine Learning Contest. The training data set consists of seven features: gamma ray, resistivity, photoelectric effect, density/neutron porosity difference, average density/neutron porosity, nonmarine/marine indicator, and relative position. The association of the features result in rock facies hand-labelled at half-foot depth intervals.   

This small supervised multi-class classification problem employs an extreme gradient boosted trees model which is an ensemble of decision trees. During each training layer, a decision tree classifier learns a set of thresholds to separate features belonging to different classes. This method combines prediction of large numbers of near random decision trees, but they have the tendency to overfit the training data. To avoid this, gradient boosting classifiers such as XGBoost algorithm can help by splitting training data observations into different subsets (Friedman, 2000). A limited number of features are then selected from each subset to train a separate decision tree.  

The importance of feature engineering, which requires domain knowledge expertise to generate additional features, is crucial to improve the model performance. A set of augmented features based on neighbouring intervals, which exploits the spatial correlation of the data, were adopted, capturing the greatest gradient of the feature vectors for each variable between two adjacent samples. This has improved the accuracy of our lithofacies classification model by 47%, as compared to the benchmark score (Hall, 2016), providing a welcoming reassurance that human experts still have a valuable role to play.  

Due to the proprietary nature of geoscience data, the data size is limited to what was provided, but this provides a stepping stone for geoscientists to further explore and apply machine learning techniques to lithofacies prediction, while employing their domain knowledge to further enhance the accuracy of predictive models. Potential applications can be used in many ways including validating velocity models for seismic data, fault interpretation and well top interpretation.  


 
![Figure 1.  Left to right: A series of well logs - Gamma ray (GR), resistivity (ILD_log10), photoelectric effect (PE) neutron-density porosity difference (DeltaPHI), average neutron-density porosity (PHIND); followed by facies classification solution showing the predicted facies (Prediction) and true interpreted facies (True Labels). The facies are, from top to bottom: bafflestone (BS), packestone (PS), dolomite (D), wackestone (WS), mudstone (MS), siltstone and shale (SiSh), nonmarine fine siltstone (FSiS), nonmarine coarse siltstone (CSiS), nonmarine sandstone (SS).](https://github.com/didiooi/LithofaciesML/blob/master/Figure.png)

### Acknowledgements:
Thanks to Matt Hall (Agile) and Brendon Hall (Enthought) for organizing the SEG Machine Learning challenge.
References
Hall, B. (2016). Facies classification using machine learning. The Leading Edge, 35(10), 906-909.
Friedman, J. H. (2000) Greedy function approximation: A gradient boosting machine: Annals of Statistics, 29, 1189–1232.

