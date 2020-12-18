# ML_FP_UrbanSound  

Members:   
Rebanta Roy  rr3659  
Christian Lourido  cl4906  

This is the final project for the Machine Learning Class course at NYU, for professor Sundeep Rangan.  

Classification of UrbanSound dataset
For this project, we explored the classification for the audio-based UrbanSound8k dataset. This dataset consists of 8000 audio files that record 10 different classes of data and are based on different kinds of noises we generally find in an urban environment. It is a popular dataset for researchers to work on as it has a vast number of compact and labeled audio files, very much suitable for training. 

This problem does have existing solutions using CNN architectures such as:
Convolution2D, Maxpooling2D, GlobalAveragePooling 2D. Other solutions use Softmax layers, Sequential layers and Basic Dropout or Flatten and Activation layers. Here, we explored 3 different approaches to the existing ones, to evaluate the performance of the same and analyze if the accuracy can be improved. 

The approaches in this repository are:  
1. Approach 1
The approach 1 was dependent on Transformer like network. In this one, Mel spectrograms were considered as the primary feature for machine learning. In this model, the mean of the time range was taken where the feature extraction can provide us with the best features. The Librosa library was used in order to detect the features. Then those spectrograms were taken through a self-embedding convoluted layer where each other sequentially arranged data points could be gone through individually as well. Finally, K-fold validation of 10 folds were taken and the out of fold accuracy came out as 84%. However, this model is very much expensive for the processing unit. A high GPU system is recommended for this. 

2. Approach 2
The approach 2 is a much basic approach than that of the first one. The Librosa library was used in order to detect the features. Over here, the data are read in MFCCs and not Mel spectrograms. Therefore, the dimension of input data also gets decreased. However, the quality of data extracted becomes rich. Also, in order to give access to external noise, the time range was not considered in this one. This allowed reading the whole length of every file. Some noise was invoked due to this reason, but that makes this model more robust. Finally, a Dense layer was applied with an increased number of units and then classified. The accuracy on the test data was calculated to be 87%. This is way less expensive on the GPU. So, it can be used easily.

3. Approach 3  
The approach 3 is a fully Transformer based approach. Generally, Transformers are used for text predictions and classifications. Here, we introduce every word and tokenize it to a certain digit in a known range. After tokenizing those numbers are read in a sequential manner and every datapoint is embedded with the whole processed dataset. Then after attention layers are introduced with for every node and finally the Transformer block embeds every token initially recognized. In here, we saw this Transformer model work very good for a similar kind of continuous speech pattern recognition model. Therefore, it was tried on UrbanSound 8k dataset as well. Here, the words are replaced by MFCCs acquired by Librosa library. And after post processing of the data after acquiring them, they are trained and tested. The accuracy came out as low as 14% in this one. It gives us scope to analyze where we went wrong using Transformers and changing which part shall make it better.

Each notebook has its own instructions. To run the models, the dataset should be downloaded first. 

To download the dataset, you will need to fill a simple form before getting access to the dataset. You can fill it using this link:
https://urbansounddataset.weebly.com/download-urbansound8k.html



