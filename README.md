1. This is a deep learning course project. In this work my partner Daniel Nachajon and I explore two broad themes: S&P 500 index benchmarking and smart portfolio construction. Our first aim is to create a model that is able to benchmark and predict the S&P 500. Our second aim is to approach the classic factor model through lens of deep learning. This second set of goals will ask us to use several of the same modeling ideas as in part but geared towards approximating underlying factors or themes of investing rather than the individual stocks themselves. We will use data provided from the Quandl API as well as Bloomberg where available. These sources provide price and economic data time-series for the members of the index.

2. Project Components

Components of the project:
●	Extract the dataset from our data provider
●	Create a cost efficient auto-encoder/decoder network trained on the constituents of our index
●	Implement the proposed ANN to benchmark the underlying index
●	Proof of generalization - Can our model predict the next day returns? If successful can we predict further out in time?
●	Writing technical paper with results and methodology
●	If time permits, 
	○	explore asymmetric loss functions to express preferences over different kinds of errors.
	○	Explore RNNs or LTSMs. Auto-regressive models have a long history in financial modeling and these approaches may provide new insights into classic methods. 

3. Block Diagram of the ANN
  
One of the problems with financial data is distinguishing what is signal and what is noise. Auto-encoding provides a mechanism to produce a cost-efficient representation of the input data against itself. One of our challenges will be to expand this model to the whole index.

For the index recreation and prediction aims of this project we would look to mirror the proposed structure by [1] but with our own data and training.

5. Comparison Between the Original Paper and the Proposed Project

The first goal of our project is to recreate the preliminary results obtained by [1] and [2]. If this seems feasible then we would extend our work to the more interesting task of prediction and “deeply efficient” portfolio construction. Furthermore the work in [1] has a feel of data compression as it attempts to benchmark the S&P 500 with just 10-20 names. We would seek to encode the entire index and introduce loss functions that encode investment preferences.

The source papers don’t make reference to the training times but instead train the network with a rolling window of 1 year’s worth of trading days. If this is unfeasible we may seek to compress this window or introduce more restrictive normalization than what is described in the papers.

6. Risks and Milestones

List of potential risks:
●	Not enough training data to capture the tail behavior of financial data
●	The details of the Auto-encoding framework is not entirely explicit from [1] and [2]. This may take some time to recreate
●	As with most financial data, the results of any analysis may vary widely based on the source of data and its quality of pre-processing.
●	The NNs for recreating the index and for predicting the next day’s returns may be considerably different and require a different architecture and calibration.

There is no clear path for troubleshooting these problems. Rather we will work from smaller problems to larger problems. If we find that we are are  not able to reproduce the author’s results there are a plethora of articles exploring the use of deep learning for trend prediction [3] and we can fall back on these using the processed data to guide our approaches. Ultimately the goal is to demonstrate predictive ability either in returns space or the risk-return tradeoff.

   
7. References

[1] Heaton J.B., Polson N.G., Witte J.H. (Feb 2016) “Deep Learning in Finance”. arXiv:1602.06561v2

[2] Heaton J.B., Polson N.G., Witte J.H. (May 2016) “Deep Portfolio Theory”. arXiv:1605.07230v1

[3] Halliday, R. “Equity Trend Predicting with Neural Networks”. Res. Lett. Inf. Math. Sci., 2004, Vol. 6, pp 15-29

[4] Satinover J.B., Sornette D. (Jun 2008) “Anomalous Returns in a Neural Network Equity-Ranking Predictor”. arXiv:0806.2606

