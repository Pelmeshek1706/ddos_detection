# Using ML for predict DDOS atack 
#### made by [@pelmeshek1706](https://telegram.me/pelmeshek1706)

 Let's imagine that we are a Data Scientist in some company, and due to constant network attacks on our servers clients often can't get to our website, which makes our popularity drop. A database dump was posted to us that collected some network information and flagged the records as malicious attacks. 

The full EDA is listed in the notebook, but below are some conclusions about the data.

The protocol of choice for cyberattacks has mostly been UDP. This is because UDP is a simple and hopeless protocol that provides unreliable delivery of data between devices. It provides no guarantee of delivery or control over the order in which data is transmitted. UDP is often used for when small amounts of data need to be sent quickly without the need to acknowledge receipt or retransmit the data. 

![malicious_protocols](https://github.com/Pelmeshek1706/ddos_detection/assets/94761102/00be2bf5-ddb8-4989-9683-e4db3837a871)

Therefore, common communications have been using ICMP, which is more secure. 

![benign_protocols](https://github.com/Pelmeshek1706/ddos_detection/assets/94761102/fd8dd229-1d7d-4e1c-9ac4-3341ce65d9a5)


#### Below are the training results of the different models

|№| Model|	Accuracy|	AveragePrecision|	F1|	roc-auc|	Training Time (s)|
|-|------|----------|-------------------|---|--------|---------------------|
|0|	Logistic Regression|	0.842877|	0.723541|	0.793214|	0.829058|	1.063181|
|1|	Decision Tree|	0.999952|	0.999879|	0.999939|	0.999960|	0.690550|
|2|	Random Forest|	1.000000|	1.000000|	1.000000|	1.000000|	8.084639|
|3|	SVC|	0.986008|	0.970139|	0.982363|	0.986204|	144.113225|
|4|	Kneighbours default|	0.980449|	0.961708|	0.975176|	0.979121|	0.006274|
|5|	Gradient Boosting Classifier|	0.998083|	0.996061|	0.997573|	0.998016|	35.632618|
|6|	ADA Boost|	0.995256|	0.990321|	0.993992|	0.995068|	7.909197|
|7|	GaussNaive|	0.668791|	0.524504|	0.658295|	0.693035|	0.044507|

### A fair win for Random Forest and Decision Tree. But due to training time my preference falls on Decision Tree

Data that I used - [DDOS dataset](https://www.kaggle.com/datasets/aikenkazin/ddos-sdn-dataset)

