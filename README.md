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

### 6) Notebook: EnatailmentApproachtrainClassifierHeadtwitterRobertaAddingFCLayer.ipynb
This code trains the last added FC layer along with the Classifier layer (two FC layer at the last) of cardiffnlp/twitter-roberta-large-emotion-latest Classifier layer on entailment dataset obtained by converting raw data to 'Premise' and 'Hypothesis'
Example:

Original Sample:<br>
'Text':  'But not very happy.'<br>
Labels: [0.0, 0.0, 1.0, 1.0, 0.0]  ('Anger','Fear','Joy','Sadness','Surprise')

Converted to:<br>
'Premise':  'But not very happy.'<br>
'Hypothesis': 'The speaker is feeling Anger'<br>
Labels: [0.0] (Neutral or Contradiction

And likewise for other emotions

### 5) Notebook: 

