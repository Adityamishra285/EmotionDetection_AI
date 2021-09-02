# EmotionDetection_AI

Emotion detection using deep learning

## Introduction

This project aims to classify the emotion on a person's face into one of **seven emotions** - angry, disgusted, fearful, happy, neutral, sad and surprised., using deep convolutional neural networks. 
The model is trained on the **FER-2013** dataset. 

## Dependencies

- Python 3, [OpenCV](https://opencv.org/), [Tensorflow](https://www.tensorflow.org/)
- To install the required packages, run `pip install -r requirements.txt`.

## Directions

The repository is currently compatible with `tensorflow-2.0` and makes use of the Keras API using the `tensorflow.keras` library.

- First, clone the repository and enter the folder using VSCODE terminal or commnad prompt in windows, use bash in linux.

```bash
cd Emotion-detection
```

- Download the FER-2013 dataset from [here](https://www.kaggle.com/deadskull7/fer2013) and unzip it inside the `src` folder. This will create the folder `data` by running "prepare_dataset.py".

- If you want to train this model, use:

```bash
cd src
python main.py --mode train
```

- If you want to view the predictions without training again, use pre-trained model (model.h5) and then run:

```bash
cd src
python main.py --mode display
```


## Algorithm

- First, the **haar cascade** method is used to detect faces in each frame of the webcam feed.

- The region of image containing the face is resized to **48x48** and is passed as input to the CNN.

- The network outputs a list of **softmax scores** for the seven classes of emotions.

- The emotion with maximum score is displayed on the screen.

## Example Output

The accurecy of the Output is around 60 to 70 percent.

- This implementation by default detects emotions on all faces in the webcam feed. With a simple 4-layer CNN, the test accuracy reached 63.2% in 50 epochs. You can increase the epochs while training the model.
