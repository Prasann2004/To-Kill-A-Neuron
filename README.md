# To-Kill-A-Neuron-
#### I was wondering how will the prediction of a neural network will change if I kill a neuron in the network. 
    
#### A `dead neuron` is a neuron that will always output `0` regardless of the input data. This can be easily done by changing the weights and bias to `0`.

#### In this experiment I will kill each neuron one by one and see the effect on the confusion matix.


## Result:

I will analyze the effect neuron by neuron and layer by layer:

- Killing Neuron 0 in Layer 0:

   Confusion Matrix:
   
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         72        |         2         |         3         |
   | Class 1|         5         |         72        |         3         |
   | Class 2|         65        |         24        |         4         |

   We can clearly see a shift in biasness of the model. Moreover, its accuracy in predicting class 2 has fallen.

- Killing Neuron 1 in Layer 0:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         73        |         0         |         4         |
   | Class 1|         67        |         0         |        13         |
   | Class 2|         26        |         0         |         67        |

   We can clearly see a shift in biasness of the model. Moreover, its accuracy in predicting class 1 has fallen so much that it has not at all predicted class 1.

- Killing Neuron 2 in Layer 0:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         9         |         0         |        68         |
   | Class 1|         0         |         65        |        15         |
   | Class 2|         2         |         14        |        77         |

   We can clearly see a shift in biasness of the model. Moreover, its accuracy in predicting class 0 has fallen.

- Killing Neuron 0 in Layer 1:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         72         |         0         |        5         |
   | Class 1|         0         |         0        |        80         |
   | Class 2|         10         |         0        |        83         |

   We can clearly see a shift in biasness of the model. Moreover, its accuracy in predicting class 1 has fallen so much that it is 0.
   
- Killing Neuron 1 in Layer 1:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         0         |         26         |        51         |
   | Class 1|         0         |         65        |        15         |
   | Class 2|         0         |         17        |        76         |

   We can clearly see a shift in biasness of the model. Moreover, its accuracy in predicting class 0 has fallen so much that it is 0.
   
- Killing Neuron 2 in Layer 1:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         71         |         1         |        5         |
   | Class 1|         0         |         68        |        12         |
   | Class 2|         11         |         19        |        63         |

   This time there was not much shift in prediction.
   
- Killing Neuron 0 in Layer 2:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         71         |         0         |        6         |
   | Class 1|         1         |         65        |        14         |
   | Class 2|         19         |         14        |        60         |

   This time there was not much shift in prediction.
   
- Killing Neuron 1 in Layer 2:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         71         |         1         |        5         |
   | Class 1|         0         |         55        |        25         |
   | Class 2|         9         |         24        |        60         |

   This time there was not much shift in prediction.
   
- Killing Neuron 2 in Layer 2:

   Confusion Matrix:
   |        | Predicted Class 0 | Predicted Class 1 | Predicted Class 2 |
   |--------|-------------------|-------------------|-------------------|
   | Class 0|         71         |         0         |        6         |
   | Class 1|         0         |         65        |        15         |
   | Class 2|         9         |         14        |        70         |

   This time there was not much shift in prediction.Infact the accuracy remained same. It may be considered as a redundent neuron.


  Based on the analysis of the effect of killing neurons layer by layer:

1. **Layer 0:**
   - Killing Neuron 0: Significant bias shift, particularly affecting the accuracy of predicting class 2.
   - Killing Neuron 1: Major shift in bias, resulting in no predictions for class 1.
   - Killing Neuron 2: Noticeable bias shift, impacting the accuracy of predicting class 0.

2. **Layer 1:**
   - Killing Neuron 0: Major impact on the accuracy of predicting class 1, reducing it to 0.
   - Killing Neuron 1: Significant impact on the accuracy of predicting class 0, reducing it to 0.
   - Killing Neuron 2: Minimal impact on predictions, indicating potential redundancy in the neuron.

3. **Layer 2:**
   - Killing Neuron 0: Moderate impact on predictions, shifting biases slightly.
   - Killing Neuron 1: Moderate impact on predictions, particularly affecting the accuracy of predicting class 1.
   - Killing Neuron 2: Minimal impact on predictions, with no significant shift in biases.

**Conclusion:**
- The model's performance is highly sensitive to the neurons in the earlier layers, particularly in Layer 0 and Layer 1, where killing certain neurons led to drastic shifts in biases and accuracy reductions, especially for specific classes.
- Neurons in later layers seem to have lesser impact on the overall model performance, with some showing redundancy as their removal doesn't significantly affect the predictions.
- Overall, this analysis highlights the importance of understanding the role of individual neurons in neural networks for model interpretability and optimization.
