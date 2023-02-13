# Fudan PRML22 Fall Final Project

Congratulations, you have come to the last challenge!

Having finished the past two assignments, we think all you guys already have a solid foundation in the field of machine learning and deep learning. And now you are qualified to apply machine learning algorithms to the real-world tasks you are interested in, or start your machine learning research.

In this final project, you are free to choose a topic you are passionate about. The project can be an application one, a theoretical one or implementing your own amazing machine learning or deep learning framework like a toy pytorch. If you don't have any idea, we also provide you with a default one you can play with.


## Default Project: Text-Iamge Transformation

### Track One: Image Caption

TA: Give an introduction to the image caption task.
ChatGPT: The image caption task is the process of generating a natural language description of an image. This is a difficult problem in artificial intelligence because it requires the model to not only understand the content of the image, but also to use natural language processing techniques to generate a coherent and accurate description. In recent years, significant progress has been made in this field thanks to the development of deep learning models that can learn to automatically generate descriptive captions for images. These models are typically trained on large datasets of images and their corresponding captions, and can generate descriptions that range from simple labels to more complex and detailed sentences. The goal of the image caption task is to create systems that can automatically generate accurate and informative descriptions of images, which can be useful for a variety of applications such as image search and accessibility for the visually impaired.


### Track Two: Text-to-Iamge

TA: Give an introduction to the text-to-image task.

ChatGPT: The text-to-image task is the process of generating an image based on a given natural language description. This is a challenging problem in artificial intelligence because it requires the model to understand the meaning of the text and then generate an image that accurately reflects that meaning. This task is related to the image caption task, but is more difficult because it involves generating an image from scratch rather than just describing an existing image. In recent years, significant progress has been made in this field thanks to the development of deep learning models that can learn to generate images from text descriptions. These models are typically trained on large datasets of images and their corresponding captions, and can generate a wide range of images that are consistent with the given text description. The goal of the text-to-image task is to create systems that can automatically generate realistic images from natural language descriptions, which can be useful for a variety of applications such as image generation and data augmentation for computer vision tasks.


### Dataset

TA: Give an introduction to the Flickr30k dataset.

ChatGPT: The Flickr30k dataset is a collection of 30,000 images and their corresponding natural language captions. It is one of the most widely used datasets for the image caption task, and has been used in many research papers and benchmark studies. The dataset was created by collecting images from the Flickr website and then having human annotators provide descriptive captions for each image. The captions in the dataset are written in natural language and describe the contents of the images in a variety of ways, ranging from simple labels to more detailed sentences. The Flickr30k dataset is an important resource for researchers working on the image caption task because it provides a large and diverse set of images and captions that can be used to train and evaluate image captioning models.

The Flickr30k dataset can be downloaded via this link (http://shannon.cs.illinois.edu/DenotationGraph/data/index.html),
- Images: Flickr 30k images.
- Texts: Publicly Distributable Version of the Flickr 30k Dataset (image links + captions)
or you can use this dataset on the PaddlePaddle platform directly.


### Precautions

- You can use your favorite framework like PyTorch, but we can't provide computing power for it for the time being;
- You can use public pre-trained models, but we value your overall workload more than the final performance;
- Done is Better Than Perfect. Implement the simplest model first, and then keep improving it.


### Resources
- Google;
- Papers from top ML/DL/CV/NLP venues;
- NNDL Chap15: Sequence Generation Model;
- Sequence-to-Sequence Learning Tutorial(https://github.com/bentrevett/pytorch-seq2seq): A tutorial implementing neural (deep learning based) sequence-to-sequence models in PyTorch with torchtext, by implementing six NMT papers;

### Implementation
Automatic generation of image captions shows the computer's understanding of images and is a fundamental task of artificial intelligence. For the caption model, in addition to finding out which objects are contained in the image, it also needs to be able to express the relationship between them in natural language. We can do this by the classical encoder-decoder model. In the model, I used resnet50 as the encoder and take its output, the features, as the input of the decoder. I used LSTM as the decoder.In order to better recognize these objects and clarify their relationships, I implemented the attention mechanism in the project, which can capture the most important information in the image and the relationship between these features. In the project, I applied an additive model, Bahdanau attention.

The model was trained on flickr30k dataset. It can master a certain number of new words and speak fluent sentences, and identify the presence of people in the scene. However, due to overfitting and imbalanced samples, the model cannot accurately distinguish the gender, animal, and scene. Regularization and image augmentation did not solve this problem. It is hoped that the image caption task can be effectively completed after learning more knowledge.

The first time I did this kind of slightly larger project, I found myself a lot of shortcomings, but I have been on the way to improve myself.