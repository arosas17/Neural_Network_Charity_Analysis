# Neural_Network_Charity_Analysis

## Overview
The company, Alphabet Soup, has raised and donated money to organizations that help the environment and people; however, history has shown that some of the recipients of the donations would vanish as soon as the money is obtained without any impact. To counter this, a project has been initiated to create a deep neural learning network to determine which organizations are too risky to ensure that the money used is more impactful.

## Results

Prior to building the neural network, the data needed to be preprocessed and determine which is the target, features, and the ones that needed to be dropped.

The target of the model are:
* IS_SUCCESSFUL

The features of the model are:
* APPLICATION_TYPE	
* AFFILIATION	
* CLASSIFICATION	
* USE_CASE	
* ORGANIZATION	
* STATUS	
* INCOME_AMT	
* SPECIAL_CONSIDERATIONS 
* ASK_AMT


The columns not needed for the features or target were:
* NAME
* EIN 


I was not able to achieve the target model performance of 75%; the currently optimized model presents an estimated accuracy of 71.1%. The original model gave an accuracy of 69.4% and a loss of 1.06. This was from two layers with nodes_layer1 = 80, nodes_layer2 = 30 and 100 epochs with the "relu" method. Using this as the original model, new models were created with "relu" activations.

The first step to attempt to optimize the model was to take out the "ASK_AMT" from the dataset while keeping the same layer and nodes as the original model. This is because the "ASK_AMT" column has some correlation to the "INCOME_AMT" column with a number of outliners. It is also noticed that most of the data are zeros which typically have an ask amount of 5,000. With this, dropping the column seemed like a way get rid of repetitive data that the machine would take into account, making less noise. This resulted in a 68.5% accuracy and a loss of 4.08. This change was kept to the rest of the attempts.

In the second attempt, the activation method was changed from "relu" to "sigmoid" in attempt to see what would happen considering that this does not seem to be a linear data set. This resulted in an accuracy of 67.8% and a loss of 0.62. The change in activation was kept because the accuracy was not affected much and the loss decreased considerably.

In the third attempt, working off the second attempt, a third layer was added and the nodes were played with to attempt for the highest accuracy as possible; this led to nodes_layer1 = 80, nodes_layer2 = 15, and nodes_layer3 = 15. The number of epochs were decreased from 100 to 70. This placed together lead to an accuracy of 71.1% and a loss of 0.60. This was the highest reading achieved so the checkpoints and h5 file made were out of this model.


## Summary
The results show that the original model gave a result of 69.4%, after which the column "ASK_AMT" was removed, resulting in a slightly lower 68.5%, a small amount. The second attempt changed the activation method from "relu" to "sigmoid," decreasing the accuracy to 67.8% but with a notable decrease in loss (from 4.08 in attempt one to 0.62), so the change was kept and preceded to add one more layer and adjust the nodes and epochs until an accuracy of 71.1% was achieved. Although the achieved target was not achieved, many attempt were made to achieve it.  Although, it is uncertain if it will obtain better results, the RandomForest model may be worth observing with the dataset; it is similar to neural neural network structure and performance so it should be able handle this complex data set well. Also, perhaps one of the more important things a RandomForest model can do for this data is rank the features. A lot of the columns listed are uncertain of how much it actually contributes to the model, to rank the features will assist in this issue.
