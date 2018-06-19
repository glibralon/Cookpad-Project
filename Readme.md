To execute the Jupyter notebooks in this repository, please download it, with the same directories and file structure, into your Home dir. Then execute the Dockerfile. Unfortunately, I could not make Docker works in my machine in order to test whether the Dockerfile is correct.

--Summary of the experiments made
The proposed problem and data are similar to the ImageNet challenge, in which different non-standardized images represent the same class and need to be correctly classified.

For this kind of problem, Convolutional Neural Networks (CNNs) are the best choice, that's why I used it. All the code was developed in Python and Jupyter notebooks, the Keras framework with the Tensorflow background was also used.

The 'cookpad_deepLearning' Notebook presents two distinct CNNs used to first explore the data and see the results. The architectures are slightly different (the dropout method is used and also a new variation of the 'relu' function aiming to obtain better models/avoid overfitting/reduce complexity/improve performance). Also, a simple preprocessing is done in the images before analysis.

The difference among 'cookpad_deepLearning_v02_MODELNAME_01' and 'cookpad_deepLearning_v02_MODELNAME_02' notebooks is the size of the batch presented during the training/validation process. MODELNAME indicates the ImageNet models used, to know: VGG16, VGG19, Resnet, and InceptionV3. In all these models, the images were rescaled between 0-1 before analysis and the imagenet pre-existent weights were used.

I chose to use these models once it's expected to obtain better results because they were already tested and trained before, thus reducing the time spent in the experiments and hopefully improving the final accuracy (considering production deadlines).

Further improvements/modifications needed to deploy would be the use of these models as feature extractors, reducing the complexity of the input data to train a CNN to predict the outputs. As the data isn't enough to ensure good results to the models, generate artificial data to increase the number of samples in the dataset, which could produce better (more precise) models. A third relevant possibility is to use GPUs and not only CPUs in the experiments, to reduce the time spent in building the models.

GPUs were not used in my experiments because the machine I used, with enough CPUs processing and memory space, is with a GPU unknown problem which didn't allow me to do this kind of experimentation. 

The possibilities mentioned in the above sentence were not implemented because the problem is computationally intensive and time was short, even the experiments presented here were hard to execute in the existent machines of our Research Lab. 

These would be only preliminary tests to find a good model for production purposes, and all the possibilities I could think to reduce the deployment time are mentioned or presented here. Unfortunately, I obtained only poor results (no more than a chance) with the developed models.

Surprinsigly, one of the simple CNN proposed performed a little better (acc: 60%-70%) than the pre-trained imagenet models investigated. 
