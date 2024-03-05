# Image-Colorization
This project is the submission for the Take Home Exam given in CENG483 Introduction to Computer Vision at METU. The explanation of the homework is included in the the3.pdf file.

## Table of Contents
- [Image-Colorization](#image-colorization)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Installation](#installation)

## Project Overview

It aims to train a model to convert grayscale images into RGB images. Moreover the goal of the project is to observe effects of various concept on training. The observations are reported in report.pdf file.

## Installation

- main.ipynb file should be in same folder with all other given .py files.

- test_images.txt file has the following format \
test\images_grayscale\0.jpg


- Pretrained models can be loaded as following (example of use exist in code):
```python
saved_state_dict = torch.load(PATH_OF_PL_FILE) #eg: torch.load("checkpoints/checkpoint.pt")

#change the parameters according to the loaded model
net = Net(num_of_layer,num_of_kernel,batch_norm,use_tanh).to(device=device)  #Parameters of my best model
net.load_state_dict(saved_state_dict)
```

- Plotting and visualizing functions are commented inside the train function. They should be uncommented in use.
```python
visualize_same_batch(net, title)
plot_losses(loss_lst_train,loss_lst_valid,title)
```
- Training function can called as in the following
```python
train(num_of_layer,num_of_kernel,lr,False,False)
#example of use - my best config call
train(num_of_layer = 2,num_of_kernel=8,lr=0.001,batch_norm =False,use_tanh = False)
```

- Lines below exist in the first cell. They should be removed if seed is not wanted.
```python
torch.manual_seed(483) #can be removed if seed is not needed
np.random.seed(483) #can be removed if seed is not needed
```