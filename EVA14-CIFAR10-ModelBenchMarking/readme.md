##Assignment Summary
This assignment is all about tricks of training a network faster on cipaf10 data. 
It is quite easy to reach accuracy with higher no of accuracy but we need to tricks if we want to ensure faster training. 
We have explored 
- the requirement for detailed customization
- changes in the floating points the importance of profiling our DNN
- importance of moving input data formats like tensorflow
- importance of moving augmentations on GPU etc.

##Notebook Sumamry
Have three notebook and two of them have been able to run in V100 and another one in 2810.
- Have taken Michael page notebook and further modified the same network. This is explained "Bag_Of_Tricks_1_0_ipynb"
- Have taken wide resnet and finetuned further which is explained in "DN_with_widerresnet". This is still under finetune and can be further finetuned.
- Have taken basemodel from Rohan and have further modified. This is explained in "DN_WithCutout8.ipnyb"
