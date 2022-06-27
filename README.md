# Neural Network Learning
My journey to building basic neural networks

# Sigmoid and Tanh and what they are/were used for:
https://machinelearningmastery.com/rectified-linear-activation-function-for-deep-learning-neural-networks/

It seems Sigmoid and Tanh functions used to be used a lot before big hunky GPUs(Graphics Processing Unit) came along and changed everything up.

Sigmoid and Tanh functions are not very good for deep neural networks because error is back propogated through the network to adjust the weights
because of the nature of the derivative of these functions, the more layers we have, the more the error is DECREASING, hence not changing the weights enough.

This is called the vanishing gradient problem. This is largely because they are *non-linear* functions, which leads me to my next point

The wonderful wonderful ReLU function!



# ReLU (Rectified Linear Activation Function)
(I'm not sure why it's ReLU and not ReLA or ReLAF but here we are - Some people also call it ReL, so maybe the U stands for "U've been pranked" or something?)

Update: Neurons that use it are called Rectified Linear Units, mystery solved

This thing was brought to the limelight in 2009-2011, a stark difference from tanh and sigmoid that were around for decades prior.

It's a linear-*esque* function, but still complex in a way that allows deep learning to be effective. It's an incredibly simple function - 
If the entered value is positive, that value is returned, and if the value is 0 or below then 0 is returned. 

In code:
```
max(0.0, x)
```
OR
```
if x > 0:
  return x
else:
  return 0
```
It's half linear and half non-linear so it's referred to as a "peacewise linear function" or a "hitch" function. Another thing about it is that it can output
a "true zero" value, whereas Sigmoid and Tanh tend to approximate values close to 0.
