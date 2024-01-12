# Text-Classification-NB-LR

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
