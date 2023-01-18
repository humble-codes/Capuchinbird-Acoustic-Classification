# Capuchinbird-Acoustic-Classification
## Objective 
Built a CNN architecture to test/evaluate the impact of raw data augmentation techniques and different amplitude scaling methods for spectrograms. There have been 4 different models developed which can be differentiated on the following basis : <ol type = 'i'>
<li>  Inclusion/Exclusion of data augmentation </li>
<li>  Amplitude scaling used for spectrograms </li>
</ol>

Model-Name | Augmentation | Amplitude Scaling | 
| --- | --- | --- |
| LiSP | false | linear |
| LiSP_AUG | true | linear |
| LoSP | false | logarithmic |
| LoSP_AUG | true | logarithmic |

The underlying architecture for all the 4 models is the same.

## Architecture
The CNN model can be subdivided into two parts: 
#### Feature extraction layer
- This sub-architecture deals with feature identification part.
- It consists of two stacked layers, each layer consisting of a Conv2D layer stacked with a pooling layer.
- The former stacked layer consists of a conv2D layer of 64 kernels connected to an average pooling layer, whereas the latter stacked layer consists of a conv2D layer of 32 kernels connected to a Max Pooling layer.
- Each convo2D layer uses a ReLU activation function.

#### Fully connected layer
- This sub-architecture's job is to classify the identified features into capuchinbird calls or non_capuchinbird calls.
- It consists of two dense layers of 64 and 32 neurons, respectively.
- These neurons are interconnected with each other.
- The final output layer consists of a single neuron using sigmoid activation function.
