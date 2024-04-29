# ECG Signal Arrhythmia Abnormalities Detection Using Machine Learning

Electrocardiogram (ECG) has long been a pivotal and economical diagnostic tool for identifying heart-related anomalies. Machine learning methods have shown 
remarkable efficacy in detecting abnormalities in clinical ECGs. Machine learning techniques have recently exhibited
notable success in identifying irregularities in clinical ECGs. This study introduces an innovative
approach to differentiate normal from abnormal ECG readings. We preprocess our data through
different stages and make suitable for machine learning models. We utilize ensemble learning
models for feature classification, including Decision Trees, k-nearest neighbor, random forests,
mop, sum, ad boost, naïve bayes, logistic regression and gradient boosting. Our thorough
experimentation reveals that our technique surpasses other methods, achieving a 98% accuracy
rate, especially with the machine learning classifier. This outcome highlights the immense
potential of our approach in discerning pathological states in ECG data.


# Methodology

For our research, we accessed and utilized data from the MIT-BIH database hosted on the Physio
Net platform [19] (http://www.physionet.org). The MIT-BIH Arrhythmia Database comprises 48
half-hour segments of ambulatory ECG recordings featuring two data channels. These recordings
were collected between 1975 and 1979 as part of the BIH Arrhythmia Laboratory's study involving
47 subjects. Among these 48 excerpts, 23 were selected randomly from a larger pool of 4,000 24-
hour ambulatory ECG recordings. This larger dataset consisted of a diverse mix of inpatients
(around 60%) and outpatients (about 40%) from Boston's Beth Israel Hospital.

![Screenshot (24)](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/49aa32d2-1fc8-45a1-b7ca-df2be5e11efb)

The remaining 25 recordings were intentionally chosen from the same pool to ensure the
representation of less common but clinically significant arrhythmias. This was done to enhance
the comprehensiveness of the database, as these arrhythmias would have needed to have been
adequately represented in a smaller random sample. Each of these recordings was digitized at a
rate of 360 samples per second per channel, with a resolution of 11 bits, spanning a 10mV range.

Furthermore, to ensure accuracy, multiple cardiologists independently annotated each record. Any
disagreements among the annotations were carefully resolved to produce a set of computer-
readable reference annotations for each cardiac beat, resulting in approximately 110,000 annotations in total, all of which are included in the database.

# Preprocessing

The Electroencephalogram (ECG) primarily captures brain activity as waveforms, representing
electrical potential differences over time. When these waveforms are displayed as images, each
point on the waveform corresponds to a specific electrical activity at a particular time. Extracting
data points from ECG images is a vital initial step in digital signal processing. While converting
graph points to csv, annotation for each record was also labelled with the help of their corresponding
annotation files. Once removed, these points can be stored in a structured format, like a CSV
(Comma Separated Values) file. This format facilitates easy access, manipulation, and analysis of
the data. The transition from ECG images to a CSV file transforms visual arrythmia signals into a
structured dataset. The initial step in data preprocessing often involves filtering to address various sources of noise in ECG signals, such as power line interference and muscle artifacts. Digital filters, including high-pass, low-pass, band-pass, or notch filters, are commonly applied. High-
pass filters eliminate low-frequency drift, while low-pass filters attenuate high-frequency noise.

Band-pass filters allow signals within a specific frequency range of interest, while notch filters
target specific narrow frequency bands to remove unwanted interference. Following filtering, ECG
signals undergo normalization to standardize the signal amplitudes across different recordings or
channels. Popular normalization methods include z-score normalization, which scales the data to
have zero mean and unit variance, and min-max normalization, which rescales the data to a specific
range, such as [0, 1]. Segmentation is a crucial step where long-duration ECG recordings are
divided into smaller segments to facilitate analysis and classification. Fixed-length windows is
used to identify specific events or epochs of interest within the ECG data. These segments are then
treated as individual instances for further analysis. Additionally, data augmentation techniques are
applied during preprocessing to increase the diversity of the dataset. We sample our imbalanced
dataset to enhance our model performance. In summary, data preprocessing in ECG abnormalities
detection research involves key steps such as filtering, normalization, segmentation, and
potentially data augmentation. These preprocessing techniques help mitigate noise, standardize
data, and enhance the quality of ECG signals before classification. Appropriate data preprocessing
significantly contributes to the accuracy and reliability of subsequent analysis and classification
tasks in ECG abnormalities detection.

# Proposed System

The machine learning process diagram for our research on ECG abnormalities detection involves
several key stages. It starts with collecting ECG data from the Physio Net platform, a publicly
available dataset. The next step is data preprocessing, where we apply filtering techniques to
remove noise and artefacts, normalize the data to a consistent scale, and segment the long-duration
recordings into smaller segments for analysis. After that, we split our data into 70-30 for training
and testing. The next stage is model selection, where we choose appropriate machine learning
algorithms, including K-Nearest Neighbors (KNN), Support Vector Classifier (SVC), Logistic
Regression (LR), Decision Tree (DT), Gaussian Naive Bayes (GNB), Random Forest (RF),
Gradient Boosting (GB), Physio Net and AdaBoost to train and evaluate our models. Once the
models are trained, we evaluate their performance using appropriate metrics and make any
necessary adjustments. Throughout the process, we iterate and refine our models to improve their
accuracy and robustness in detecting ECG abnormalities. Figure 2 shows the proposed block
diagram.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/4950d03f-bdd2-4338-a691-1309ffbbfce0)

# Result Analysis

This research paper thoroughly analyzed ten different machine learning models applied to a
specific dataset. These models encompassed a variety of algorithms, including Logistic
Regression, Decision Tree, Random Forest, Gradient Boosting, AdaBoost, Support Vector
Machine (SVM), K-Nearest Neighbors (KNN), Naive Bayes, Multi-Layer Perceptron (MLP), and
Gaussian Process. Each model underwent a comprehensive evaluation process involving training,
prediction, and the generation of classification reports. Notably, the Random Forest, SVM, KNN,
and MLP models demonstrated outstanding performance, achieving high accuracy and balanced
precision, recall, and F1 scores across all classes. In contrast, AdaBoost and Naive Bayes exhibited
comparatively lower performance, suggesting the need for further optimization or alternative
modelling approaches.

- Logistic Regression: This model achieves an accuracy of 83%, with precision, recall, and F1 scores varying across classes. It performs reasonably well in most classes, with the highest F1 score of 0.92 for class 2. Its training and test scores are 83%.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/45c08ae4-3f76-4e59-8f55-e78b275163b2)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/8c212bab-ea6d-4b8e-8b46-c5e7cf0884d3)

- Decision Tree: The Decision Tree model outperforms Logistic Regression with an accuracy of 93% with 100% training and 93% test score. It excels in precision, recall, and F1 scores for all classes, demonstrating its effectiveness in classification.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/bd3d69cf-0055-4d15-b154-4954642961fa)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/69bf2936-f74e-42ab-a29e-8ba60b75eeaa)

- Random Forest: Random Forest exhibits even better performance with an accuracy of 98% with 100% training and 98% test score. It consistently achieves high precision, recall, and F1 scores across all classes, indicating robust classification capabilities.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/c50a5325-01fe-4aa2-a251-3f7f1794c6c1)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/a4f8b93c-6231-4eb6-a73f-e0dc9627c617)

- Gradient Boosting: This model attains an accuracy of 94% and showcases balanced precision, recall, and F1 scores across classes, highlighting its reliability for classification tasks. Its training and test scores are 97% and 94% respectively.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/c75b0a2b-3bf7-4c1f-ad64-c6928f3baec8)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/3c4a215d-d87c-41d4-865c-baeade88df0e)

- AdaBoost: AdaBoost, while achieving an accuracy of 67%, exhibits lower precision, recall, and F1 scores than other models, especially for class 2. It may require further tuning or consideration of alternative models. The training and test scores 68% and 67%.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/e645a84a-3b73-42bb-940f-2b91ffc4de1b)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/34946ac7-56fd-4e82-a9e0-4e67b90566b9)

- SVM (Support Vector Machine): SVM shines with an accuracy of 96% with 96% and 95% training and test scores, offering vital precision, recall, and F1 scores across classes, demonstrating its suitability for this classification problem.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/6eb04135-1a6b-40f9-a96c-f0db0b46e114)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/d5d58ad9-958a-42c7-a907-45777afac62b)

- K-Nearest Neighbors (KNN): KNN performs admirably with an accuracy of 96% and training and test scores are 98% and 96%, consistently delivering high precision, recall, and F1 scores across all classes.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/2f435122-df52-458c-bc1f-ad4ad16e16a9)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/f0ab97be-9148-44fb-b854-784b38df7e04)

- Naive Bayes: Naive Bayes achieves an accuracy of 66% and demonstrates moderate precision, recall, and F1 scores. It may benefit from further feature engineering or alternative models for improved performance.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/cf42b592-b717-4134-9647-399f9979692b)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/3457db6b-ac1a-4a1b-b9a8-13949cd915d0)

- MLP (Multi-Layer Perceptron): MLP excels with an accuracy of 98% with high training and test scores, offering high precision, recall, and F1 scores across all classes, indicating its robust classification capabilities.

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/5ca8e14e-b3b0-49bd-8554-e150950610e7)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/5548ba7a-6fd8-4f34-b345-e678da7bc184)

Accuracies of Implemented Models:

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/3711395d-0788-4f75-99c1-386946392cc8)

![image](https://github.com/Lab1ba/ECG_Abnormalities_Detection/assets/100675446/409a6aaf-dbd9-4614-ab9f-978894cf36bd)

Overall, this comprehensive model evaluation provides valuable insights into their performance,
enabling informed decisions about selecting the most suitable model for the specific classification
task. Models like Random Forest, SVM, KNN, and MLP exhibit strong performance and may be
preferred choices for this dataset. At the same time, AdaBoost and Naive Bayes may require further
optimization or consideration of alternative approaches. Also, by visualizing the training and test
scores, we can say that they are not overfitting. Their scores are balanced. Models like Random
Forest and MLP with high training scores also demonstrated high test scores. These findings
provide valuable insights for selecting the most suitable machine learning model for this
classification task, contributing to the broader understanding of model selection in real-world
applications.
