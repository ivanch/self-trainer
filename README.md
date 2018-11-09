# Data Augmentation with GAN
#### An A.I. used to train another A.I. so the second A.I. can get more powerful

## How does it work
Basically, you train the GAN with a dataset, than use the trained GAN to generate a dataset to feed to the CNN. In general, it works just like a normal data augmentation, where you create data that doesn't necessarily exists.

## Tests
In what I've tested (fashion MNIST), this dataset performed ~2% better on F1 score than only training with the dataset. My tests also appointed that it doesn't work with some datasets (like MNIST). The tests were made with 200 epochs and with dataset set to 2,000.
Details:
* 200 Epochs on normal dataset: 0.8122 F1 score.
* 200 Epochs on generated dataset: 0.8305 F1 score.

## Usage
If you want to use, be sure to install Jupyter Notebook on your computer. The code could be written in a `.py` file, but we need to check the outputs of the some pieces of code and have the control over the models.
0. Make sure you have `keras`, `sklearn`, `numpy`, `cv2` and `matplotlib` installed.
1. Extract `dataset.zip` into the folder.
2. Make a folder called `Samples`.
3. Run jupyter notebook on the directory and open `SelfTrainer.ipynb` file.
4. Configure the code, if there's something that might need a little tweaking.
5. Run the code cells and check their output as needed.

## NOTES
* This project is more "data modification" than "data augmentation".
* This method works better with limited data, in this case I used 2,000.
* This method doesn't work with all datasets, MNIST as an example.
* If you want to test, be sure to test both GAN and GAN + DATASET options, performances may vary.
* When training the GAN, samples of the outputs will go into the `Samples` folder, this way you can check the GAN performance.
