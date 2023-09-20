# Progress

1. Take a subset of the data and the see the effect of resmapling if they would change in the accuracy
3. run on  the cluster
4. use inceptionTime classfier in the FewShot

# 2nd meeting
1. A simple cnn
2. Train on cycle A and then test on f
3. Train on A and take support from F and then test on f again using meta learning

 # 3d meeting
 1. bug in the implmentation
 2. make sure that the data is shuffled correctly

# Last meeting
1. task specfic encoder and task specfic decoder and common model
2. chek labelhullacination implmentation
3. the 2 baselines are labelhullicanation and maml

# Questions 

# For my method 

1. For every time dataset I have a specific encoder, a common encoder that it is shared and common decoder. I can compute the loss function and value for the decoder bu how should i back propagate it two the common model
2. For now i am using 2 types of decoders, private and public because i have 2 different datasets for now
3. I train the autoencoder on 1 dataset from the private dataset, then save this model and use it to encode the rest of the datasets. Should I train it for more training or is that enough?
#  For label hallucination

1. For the embeddings, I will train the common model but again here I will need 2 classifier heads based on the number of classes or should I concatenate all of them together? That means i will add the private datasets and public datasets in one big dataset after i encode the private datasets and this way i will only have classification head 
2. After the pseudo labeling. I should relearn the embedding and classification head with decoder with a combination of distillation function and entropy loss function
# For Maml:
1. In Maml training should be built by a certain number of samples for example 5 samples per class → does that mean i rebuild the training dataset by keeping only the n number of samples of class
The maml training is to just adjust the weights of the base dataset and then finetune it?
 So first i’m sampling different tasks(which will be private and public) dataset
2. 2 tasks basically (classifying the private and public dataset)
3. I will use encoder and decoder but again i will share the common model?
4. The support set and query set will be defined by the number of examples what sizes are they
5. After that i will take 5 samples and then finetune the public value?
# Points for arguments:
 That even if label hallucination has a better results or full_run these require relearning all over again when new data is available while in seq run we can train using the new data only(so even if they are better)




    
