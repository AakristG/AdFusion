# AdFusion
Research based on ad-copy and image generation.

By enhancing the contextual understanding of LLMs, AdFusion aim to create a model that better grasps the intent and tone of ad copy, resulting in images that are not just relevant but also creatively aligned with the message.


## Fine Tuning

This t5_trainer.ipynb file is used to fine tune the model T5.

You can use [google colab](https://colab.research.google.com/) or install [jupyter notebook](https://jupyter.org/) to fine tune the model.

**Just remember you have to insall Jupyter Notebook and it is strongly suggested you have a GPU (preferrably NVIDIA to use Cuda)**

**If you would like to not worry about Jupyter Notebook, you can use colab which provides you with a GPU called T4 (you just have to switch to it)**

### How to set up Jupyter Notebook

You can either download the Anaconda Navigator and open Jupyter Notebooks from there or directly download Jupyter Notebooks there.

Create a new notebook and set a Python environment that has torch and numpy installed.

Follow the instructions and code in t5_trainer.ipynb to fine tune your model.

### How to set up Google Colab

Sign in with your google account and create a new notebook. 

Since Colab notebook needs to be mounted to drive for it to be saved for later use, you can use this command.

```python 
#Mount the notebook to the drive

from google.colab import drive
drive.mount('/content/drive')

```

To download the required libraries in colab, it has to be installed like this:

```python 
#Example import statements

!pip install sentencepiece
!pip install transformers
!pip install rich[jupyter]

```

### Setting up the data

If you want to fine tune T5-large or T5-base with your own data, then you can change the base_path and the output_file to your correct directory. 

For example, if you are using Colab and want to access your folders:

```python

# This gets data from this folder structure of parent folder LaVi-Bridge to subfolders 1 to n (the number of folders you have) to each captions.txt and img.jpg files
base_path = "/content/drive/My Drive/LaVi-Bridge"
output_file = "/content/drive/My Drive/LaVi-Bridge/captions.txt"
```

**This model trains from images and text, remember to change the name of the text files from "captions" or "images" to the name of your txt and jpg files.**

Finally if your data is in a csv file, then you can use: 

```python 
#Insert your link here

path = "https://github.com"

df = pd.read_csv(path)

```

The folder structure should be like this:

| - - - - - - - - - Other Folders

| - - - - - - - - - LaVi-Bridge

| - - - - - - - - - - 1

| - - - - - - - - - - - captions.txt

| - - - - - - - - - - - img.jpg

| - - - - - - - - - - 2

| - - - - - - - - - - - captions.txt

| - - - - - - - - - - - img.jpg

| - - - - - - - - - - n

| - - - - - - - - - - - captions.txt

| - - - - - - - - - - - img.jpg

| - - - - - - - - - - caption.txt (with fine tuned data)



<!-- ## Train the model -->

## Resources

Huge thanks to these github repositories for inspiration and clarification needed for this code:

- https://github.com/ShihaoZhaoZSH/LaVi-Bridge
- https://github.com/Shivanandroy/T5-Finetuning-PyTorch


