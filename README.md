# Chest x-ray image caption generation
In this repository we have provided the model for captioning chest x-ray images to facilitate examination of these images.
Colons can be used to align columns.


|Problme        |X-Ray image captioning         | 
| ------------- |:-------------:|
|Dataset      |Indiana university chest x-ray |
|Dataset link      |https://www.kaggle.com/datasets/raddar/chest-xrays-indiana-university      |
|Train set |2559 pairs of frontal chest x-ray and corresponding captions|
|Validation set |320 pairs of frontal chest x-ray and corresponding captions|
|Test set |320 pairs of frontal chest x-ray and corresponding captions|
|Models|1. CNN-LSTM <br>2. Blip(https://huggingface.co/Salesforce/blip-image-captioning-base) <br>3. GIT(https://huggingface.co/microsoft/git-large) <br>4. Blip2(future work)|
|Evaluation metric|BLEU score|

# 1️⃣ CNN-LSTM
Our base model is based on encoder-decoder architecture. In the image encoder part, we will use pre-trained CheXnet which is a DenseNet with 121 layers and has been trained on 112,000 chest X-ray images. To obtain text embeddings, we have used the Glove model. <br>
![Alt Text](https://github.com/NLP-Final-Projects/chest_xray/blob/main/Picture1.png?raw=true)


# 2️⃣ Blip
This model has used ViT-L/16 for the image encoder part and Bert model for the text encoder part. Pretrained on COCO dataset.
![Alt Text](https://production-media.paperswithcode.com/methods/bf9bd9a4-da80-4059-bdc1-3f49549d4044.png)

# 3️⃣ GIT
GIT is a Transformer decoder conditioned on both CLIP image tokens and text tokens. The model is trained using "teacher forcing" on a lot of (image, text) pairs. The goal for the model is simply to predict the next text token, giving the image tokens and previous text tokens.
Pretrained on COCO dataset.
![Alt Text](https://huggingface.co/datasets/huggingface/documentation-images/resolve/main/transformers/model_doc/git_architecture.jpg)


# How to use
|Model        |directory path        | 
| ------------- |:-------------:|
|CNN-LSTM      |Base_model/Base_model.ipynb|
|Blip      |Blip/Blip_model.ipynb|
|Blip results(images with generated captions)|Blip/Blip_test.ipynb|
|GIT |GIT/GIT_test.ipynb|
|GIT results(images with generated captions)|GIT/GIT_test.ipynb|

# Evaluation table
|Model        |average Bleu        | 
| ------------- |:-------------:|
|CNN-LSTM  Beam-serach    |0.1521 |
|CNN-LSTM  Greedy-search     |0.1482|
|Blip      |0.205 |
|GIT |0.212 |


# Contributors
|Name        |Mail        | 
| ------------- |:-------------:|
|Mehrab Moradzadeh      |moradzadeh1999@gmail.com|
|Ali Derakhsesh      |ali.derakhshesh79@gmail.com|
|Mohammad Taha Teimuri Jervakani |teimuri.ce@gmail.com|
|Abolfazl malekahmadi|abolfazlmalekahmadi@gmail.com|
|Alireza Aghaei|aghaei.alirezza@gmail.com|
