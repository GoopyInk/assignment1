# Assignment 1

## Overview

Assignment 1 includes 1 part:
1. KNN

File structure:
```
assignment1
├── README.md  (this file)
├── algorithms  (source code folder)
├── knn.ipynb  (notebook)
├── get_datasets.py  (download script)
└── datasets  (datasets folder)
```

## Prepare Datasets

Before you start, you need to run the following command (in terminal or in notebook beginning with `!` ) to download the datasets:

```sh
# This command will download required datasets and put it in "./datasets".
python get_datasets.py
```

## Implementation

You should run all code blocks in the following jupyter notebook(s) and write your answers to all inline questions included in the notebook(s):

1. `knn.ipynb`

Go through the notebook(s) to understand the structure. These notebook(s) will require you to complete the following implementations:

1. `algorithms/knn.py`: Implement KNN algorithm

## Submission

### Things to keep in mind:

1. Edit **only** the parts that are asked of you. Do **not** change the random seed where it is set. This might not make it possible to get similar results.
2. **Only answer questions and plot figures at givens cells**. TAs may miss your answer if you put it at the wrong cell.

After you complete all the functions and questions, you should upload the following files to Gradescope:

- **Assignment 1**  
  Submit `answers_hw1.txt` and the notebook PDF (e.g., `knn.pdf`).  
  No zip file is needed. Upload **one `.txt` file and one `.pdf` file**.

- **Assignment 1 – Code**  
  Submit `algorithms/knn.py`.  
  No zip file is needed. This should be **a single Python file**.

## Appendix

### How to Use Jupyter Notebook

Part of our skeleton code is provided using Jupyter notebook(`*.ipynb`). So there we provide a short instruction about how to use Jupyter Notebook.

Jupyter notebook is a powerfull interactive developement tool. In this assignment, we refer to a Jupyter Notebook file simply as a notebook.

Jupyter notebook is pre-installed on Datahub, you can just use it via web-portal. You could also install it on your local machine. Here is the official install instruction([https://jupyter.org/install](https://jupyter.org/install)), which also included how to run it via terminal.

You may find on Jupyter website, they provide Jupyter Lab. Jupyter Lab is basically a new version of Jupyter notebook with more features and different interface. The basic usage is almost the same.

All notebooks are made up with multiple blocks. There are different kinds of blocks, the most common blocks are:

- Code block
- Markdown block

#### Code

For code block, you can write python code in code block, after finishing your code you could press run bottom on the jupyter note interface(normally on the top of the web interface). You can also use `Ctrl + Enter` or `Shift + Enter` to execute the block.

After you execute a block, Jupyter Notebook will execute your code with python and store all the function and variable you defined in memory. So you could still use those variables and function is other blocks.

For code blocks, you can think of jupyter notebook as a python console with an interface.

#### Markdown

Markdown block is where you can write some text.

When you execute Markdown block(the same method as Code block), your text will be compiled using Markdown grammar, instead of executing it with python.

In our assignment, we put some inline questions in notebooks, you are supposed to answer them with text.

#### Conclusion

In all, notebooks are basically some combination of code and text.

### How to Set Up Python Environment for Assignment 1 (Optional)

If you run the assignment on Datahub, you do **not** need to set up python environment. Our code is tested on Datahub with Python 3.11.9 (ipykernel).

If you run the assignment on your local machine or other environment and meet some problems, you **may** need to set up a new python environment.

We prepare a `requirements.txt` file (same versions as the datahub packages) for you to install python packages. You can install the packages by running the following command in terminal:

```sh
pip install -r requirements.txt
```

This should solve most package issues. But if you still have some problems, we recommend you to use conda environment. You can install anaconda or miniconda by following the instruction on [https://docs.anaconda.com/anaconda/install/index.html](https://docs.anaconda.com/anaconda/install/index.html). After you install it, you can run the following command to set up a new python environment:

```sh
conda create -n assignment1 python=3.11.9  # same python version as the datahub default ipykernel
conda activate assignment1
pip install -r requirements.txt
```

If you have any questions, feel free to post on Piazza.

### Other Tips

#### Unzip a Zip File

```sh
unzip XX.zip  # in terminal or in notebook beginning with `!`
```

#### Error Running HOG
If you are using an older version of `scikit-image` (for example, 0.18), you may encounter the error `TypeError: hog() got an unexpected keyword argument ...`. In that case, please replace the code with the **following code**.

```python
# Use a subset of CIFAR10 for KNN assignments
hog_p_func = partial(
    HOG_preprocess,
    orientations=9,
    pixels_per_cell=(4, 4),
    cells_per_block=(1, 1),
    visualize=False,
    multichannel=True,
)
```