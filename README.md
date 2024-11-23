# TBED-CS779-IITK
Text Based Emotion Detection SemEval-2025 Task 11

## Track A:
### 1) Notebook: twitterRobertaLarge.ipynb
This notebook shows the code to predict the multiemotion labels of Track A training Dataset without finetuning. The model used was cardiffnlp/twitter-roberta-large-emotion-latest available on huggingface. The model predicts 11 emotions out of which 5 required emotion labels are selected as prediction.

### 2) Notebook: trainTwitterRoberta_accuracy.ipynb
This notebook contains the code of full finetuning of cardiffnlp/twitter-roberta-large-emotion-latest model. The model predicts 11 emotions out of which 5 required emotion labels are selected as prediction.

### 3) Notebook: traintwitterRobertaAddingFCLayer.ipynb
This notebook contains the code of finetuning the last added FC layer of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer. Since the base model prediction was for 11 labels, we have added an FC layer with 5 desired emotion labels and train only this layer freezing the base model.

### 4) Notebook: trainClassifierHeadtwitterRobertaAddingFCLayer.ipynb
This notebook shows the code of finetuning the last added FC layer along with the Classifier layer (two FC layer at the last) of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer. Since the base model prediction was for 11 labels, we have added an FC layer with 5 desired emotion labels and train only this layer freezing the base model.

### 5) Notebook: AUGMENTED_trainGoEmotionsRoberta_accuracy.ipynb
This notebook shows the code of finetuning the last added FC layer along with the Classifier layer (two FC layer at the last) of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer. Synthetic points were generated to overcome the imbalanced class distribution. ChatGPT 4o was used to create new data points.

### 6) Notebook: EnatailmentApproachtrainClassifierHeadtwitterRobertaAddingFCLayer.ipynb
This code trains the last added FC layer along with the Classifier layer (two FC layer at the last) of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer on entailment dataset obtained by converting raw data to 'Premise' and 'Hypothesis'. Here also base model weights was from except Classfier layers.
Example:

Original Sample:<br>
'Text':  'But not very happy.'<br>
Labels: [0.0, 0.0, 1.0, 1.0, 0.0]  ('Anger','Fear','Joy','Sadness','Surprise')

Converted to:<br>
'Premise':  'But not very happy.'<br>
'Hypothesis': 'The speaker is feeling Anger'<br>
Labels: [0.0] (Neutral or Contradiction

And likewise for other emotions.

### 7) Notebook: BalMinoritytrainClassifierHeadtwitterRobertaAddingFCLayer.ipynb
This code trains the last added FC layer along with the Classifier layer (two FC layer at the last) of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer on balanced obtained by oversampling the minortity class with oversampling. The base model weights was from except Classfier layers.<br>
Oversampling Method-1: Selected the class with lowest representation and selected those samples which have 1 in the that emotion label and all others 0. We randomly sampled 100 samples from it and then again checked for lowest class representations and repeated the procedure till we got balanced samples

### 8) Notebook: BalMinority2trainClassifierHeadtwitterRobertaAddingFCLayer.ipynb
This code trains the last added FC layer along with the Classifier layer (two FC layer at the last) of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer on balanced obtained by oversampling the minortity class with oversampling. The base model weights was from except Classfier layers.<br>
Oversampling Method-2: Selected the class with lowest representation and sampled those rows which do not have 1 in the majority label class (like Anger which had 1611 samples). We randomly sampled 100 samples from it and then again checked for lowest class representations and repeated the procedure till we got balanced samples

## Track B:
### 1) Notebook: TrackBtrainClassifierHeadtwitterRobertaAddingFCLayer.ipynb
This notebook shows the code of finetuning the last added FC layer along with the Classifier layer (two FC layer at the last) of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer. Since the base model prediction was for 11 labels, we have added an FC layer with 5 desired emotion labels and train only this layer freezing the base model.<br>
Since the base model was trained on dataset with 0/1 labels and ours was an intensity prediction problem, we first converted the intensities into range 0 to 1 with the following rule:<br>
label-0: 0.0<br> 
label-1: 0.6<br>
label-2: 0.75<br>
label-3: 1.0<br>
After prediction the score was reconverted to desired labels with another set of rules as follows: <br>
Score< 0.5: label-0<br>
0.5 <= Score < 0.7: label-1<br>
0.7 <= Score < 0.8: label-2<br>
0.8 <= Score <= 1.0: label-3<br>

## Track C:
### 1) Notebook: dataset_XED_train_trackC.ipynb

### 2) Notebook: dataset_XED_similarity_score.ipynb

