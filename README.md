# Data Augmentation with GAN
#### An A.I. used to train another A.I. so the second A.I. can get more powerful

## How does it work
Basically, you train the GAN with a dataset, then use the trained GAN to generate a dataset to feed to the CNN. In general, it works just like a normal data augmentation, where you create data that doesn't necessarily exist.

## Tests
Based on what I've tested (fashion MNIST), this method performed ~2% better on F1 score than only training with the normal dataset. My tests also appointed that it doesn't work with some datasets (like MNIST). The tests were made with 200 epochs and with dataset set to 2,000.
Details:
* 200 Epochs on normal dataset: 0.8122 F1 score.
* 200 Epochs on generated dataset: 0.8305 F1 score.

## Usage
If you want to use, be sure to install Jupyter Notebook on your computer. The code could be written in a `.py` file, but we need to check the outputs of the some pieces of code and have the control over the models.
1. Make sure you have `keras`, `sklearn`, `numpy`, `cv2` and `matplotlib` installed.
2. Extract `dataset.zip` into the folder.
3. Make a folder called `Samples`.
4. Run jupyter notebook on the directory and open `SelfTrainer.ipynb` file.
5. Configure the code, if there's something that might need a little tweaking.
6. Run the code cells and check their output as needed.

## Could it help fixing an unbalanced dataset?
Yes it can. If you've got a very unbalanced dataset, you can use a GAN to help you balance the classes. The results showed an improvement of ~4% on F1 score.
1. Unbalanced dataset: [134, 59, 18, 479, 31, 526, 510, 125, 33, 81] (samples per class)
  1.1. F1 score: 74.59% (dataset only)
  1.2. F1 score: 78.73% (with augmented data from GAN)


## NOTES
* This method works better with limited data, in all cases presented here I used 2,000.
* This method doesn't work with all datasets, MNIST as an example.
* If you want to test, be sure to test both GAN and GAN + DATASET options, performances may vary.
* When training the GAN, samples of the outputs will go into the `Samples` folder, this way you can check the GAN performance.
