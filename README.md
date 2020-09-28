# Deep Learning


## Basic Idea

First Step: Input values (each represents one field/column in a row) are applied certain weight

Second Step: Sum up the weighted value from input values

Third Step: Take the sum in step 2 and apply activation function to get the output value. The output value can be 0 - 1 or sometimes -1 to 1 depending on the activation function applied) or with rectifier it can go above 1. 

Through backpropagation the weights get adjusted, until we find the lowest error out of `cost function`. This is done through `Gradiant Decent`  - to find the global minimum (so you don't need to brute force every single possible combination).

### Activation Functions

After each input value is applied certain weight and summed in the second step, the 

Four common activation function:
 - Threshold function: if x < 0 y = 0 else 1 -> binary 
 - Sigmoid function: y = 1/(1+e**(-x))  -> 0 to 1 
 - Rectifier function: y = max(x, 0)  -> this is the most used activation function
 - Hyperbolic Tangent: y = (1 - e**(-2x))/(1 + e**-2x) -> goes from -1 to 1
 
 
## Convolution Neural Networks

- There is a cool tool you can use to visualize each layer:
https://www.cs.ryerson.ca/~aharley/vis/conv/flat.html


### Step 1 - Convolution
For a given `input image`, you apply `feature detector`(or some call filter) and generates `feature map`.

`feature map` preserves the important features that we should focus, just like the human brain.

You apply multiple feature detector and receive multiple feature maps

Depending on the feature detector type, you can get different versions (like "sharpen", "blur", "edge detect") of images.

There are couple of steps here:

#### Step 1(b) ReLu Layer

Relu - Rectifier Linear Unit
Applying rectifier activation function.

### Step 2 - Max Pooling (also called Downsampling)

Max Pooling is a techneque to generalize the fitting to have flexibility - essentially you are reduing the size of the pixels (i.e., blur it with lower resolution)! From the `feature map`, move thru each chunk and preserve the max value from each chunk (so you can rid of 75% of the unimportant information), so in the end you will create a `Pooled featured map` that is still able to preserve the features and reduce the size. And more importantly to avoid overfitting. 

### Step 3 - Flattening

Once pooling is done, we then flattern/tranform the pooled fature maps into vecrors (so one matrix becomes a record - a row in a table)

### Step 4 - Full Connection - Apply ANN

Finally, take the vectors as input values and start the ANN process for training. The hidden layers in the CNN process are also called `fully connected layers`. The last layer of the ANN in this case represents all the features to determin the class (like cat or dog) - also called "voting". We can do multiple classifications. 


