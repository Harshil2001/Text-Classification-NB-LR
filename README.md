# Text-Classification-NB-LR

In this project I have implemented and evaluated Naive Bayes and Logistic Regression for text classification.

For this project I did the following steps that are mentioned in the project description.

- Downloaded the required datasets and uploaded them into colab.
- Unzipped the datasets and dealt with the anomaly of the path for dataset enron2
- Converted each of the text dataset into a matrix of features × examples for both Bag of Words model and Bernoulli model, where the features only consist of words using the alphabets. Here the Bag of Words representation has the frequency of words while the Bernoulli representation has either 0/1.
- Implemented the Multinomial NB algorithm in log scale along with add-one laplace smoothing. Here, I computed the priors and the conditional probabilities in log scale and using add-one laplace smoothing. And then predicted the values using the prior and conditional probabilities for the testing dataset. This was implemented for the Bag of Words model.
- Implemented the Discrete NB algorithm in log scale along with add-one laplace smoothing. Here, I computed the priors and the conditional probabilities in log scale and using add-one laplace smoothing. And then predicted the values using the prior and conditional probabilities for the testing dataset. This was implemented for the Bernoulli model.
- Implemented the MCAP LR algorithm along with L2 regularization. This was implemented for both the Bag of Words and Bernoulli models. Here, I computed the value of the sigmoid function, and then I computed the gradient of the conditional log likelihood. Using the gradient along with penalizing the weights using L2 regularization I trained the model. Before training the model on the full dataset, I trained it on 70% training data and simultaneously validated on the remaining 30% training data, for different lambdas, this was done in order to get the best lambda for training. For me, out of the values [0.1, 0.3, 0.5], the best lambda came out to be 0.1. I choose the learning rate to be 0.01. To find the best lambda, the number of iterations used was 30. For the final training, the maximum number of iterations was set to 80 epochs, along with checking the conditional log likelihood or loss, so, if the log_cll<0.1 then we will break the loop and stop the training. Finally, after the completion of the training, I tested the implementation using the testing dataset along with the parameters realized from training. 
- Implemented the SGDClassifier algorithm from sklearn and tuned the parameters using GridSearchCV from sklearn. This was implemented for both the Bag of Words and Bernoulli models. I tuned the following parameters: alpha, loss function, maximum iterations. I imputed the following: for alpha or learning rate, (0.001 and 0.01); for loss, (squared hinge, hinge and log): for maximum iterations, (30, 50, and 80). The tuning was done on the 30% training dataset, while the final training was done on the full training dataset. Finally, I tested the implementation using the trained classifier.

# Usage

To run: Upload and Run the TextClassifier.ipynb file on Google Colab or Jupyter Notebook

To run this file, unzip it in the same folder as the datasets

The result for every database can be replicated by running the code one by one on all database separately.
This can be done by running all the code snippets till the 3rd last snippet.
Then you can run the 2nd last snippet and enter the following values in lowercase:
Enter the dataset number: This can take the numerical values such as '1', '2', and '4' which coreesponds 
	to the datasets named - enron1, enron2, enron4
Enter the algorithm name: This can take the following values:
	'mnb' for Multinomial Naive Bayes
	'dnb' for Discrete Naive Bayes
	'mcap' for MCAP Logistic Regression
	'sgd' for SGDClassifier
Enter the representation: This can take only 2 values:
	'bow' for Bag of Words representation
	'bern' for Bernoulli representation
Kindly input the 'bow' for MNB and 'bern' for DNB

**
The other alternative is to 'not' run the 2nd last snippet and instead run the 'Last' snippet
	This will output the metrics for all datasets, all algorithms, and using both the representations
