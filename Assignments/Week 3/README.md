# Assignment 3

This assignment involved training a model with less than 100,000 parameters without using dense layers to beat the accuracy of a reference model(~82%).



## Highlights

- Kernel level regularization is used for every layer. As mentioned by [Cortes et al.](https://arxiv.org/ftp/arxiv/papers/1205/1205.2653.pdf) in their paper ***L2 Regularization for Learning Kernels***, L2 regularization is used. (Just took inspiration on which method to use **without** reading the full paper).
- Noticed that the model trained well when run for about 100 epochs. Hence needed something to fasten up the learning process. Hence used Super-Convergence as mentioned by [Leslie N. Smith](https://arxiv.org/abs/1708.07120) in their paper **Super-Convergence: Very Fast Training of Neural Networks Using Large Learning Rates**.
- Used **AveragePooling2D** instead of MaxPooling2D and got better results.
- Used **SGD with momentum** for better performance.
- The total number of parameters used in the model is **91,909** which is 91.9% of total number of parameters.
- Model has achieved **88.27% validation accuracy** as compared to 82.10 for the reference model.

## Model Definition