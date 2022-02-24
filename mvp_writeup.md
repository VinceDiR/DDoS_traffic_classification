## Mitigating DDoS attacks and ensuring service availability

The goal of this project is to create a model that can correctly identify benign, legitimate from malclious junk traffic in the midst of a DDoS attack. 

![](https://github.com/NateDiR/DDoS_traffic_classification/blob/main/plots/mvp_confusion.png)

As a first step, I created a logistic regression model using all features in the dataset. Parallelizing the fit process using Dask saved considerable time here.

The figure above depicts the confusion matrix for the first-pass logistic regression model. The recall was 97.17%, and precision was 90.11%.

This result suggests that logistic regression may be a viable candidate for solving this problem, per our success metrics. Some optimization of the  logistic regression mode'ls threshold may get us where we want to be, or a more advanced ensemble model like Random Forest or Gradient Boosting may perform better.
