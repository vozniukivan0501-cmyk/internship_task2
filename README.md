# Internship Task 2: Animals entity recognition and animals image classification

## Project Overview
*This repository contains the solution for the internship Task 2 test. It implements 2 models for NER, animals images classification and a final pipeline.
It contains generated data for NER model training, synthetic text requests generator, translator module for animals10 dataset.
Repository also contains trained MobileNetV2-based model.

## Model and Dataset setup
* DestilledBert-based model is too big to upload on GitHub, same as animals dataset.
* How to load necessary data and train DestilledBert-based model:
  1) Download dataset from: https://www.kaggle.com/datasets/alessiocorrado99/animals10
  2) Unpack all directories from 'raw-img' into data/animals10
  3) Run translator.py with: python src/translator.py
  4) Run train_ner.py with: python src/train_ner.py (recommended args are set by default, but can be changed)
  5) Wait until model save
 
## Project Structure
base dir/

  data/
    1) animals10 / <10 dirs with images> - should be uploaded by user, contains dataset for train CV model
    2) ner_data / ner_dataset.json - dataset with generated text conversation for NER model
    
  models/
    1) ner_checkpoints - temp files for NER model, setting up automatically after NER model training
    2) ner_model - dir contains saved NER model, setting up automatically after NER model training
    3) cv_model.keras - saved and trained MobileNetV2-based CV model
    
  notebooks/ 
    1) EDA.ipynb - contains notebook with EDA visualization and conclusions about animals10 dataset
    2) DEMO.ipynb - contains demonstration of pipeline performance and edge cases descriptions

  src/
    1)cv_model_module.py - initialize CV model class
    2)ner_model_module.py - initialize NER model class
    3)train_cv.py - file with parametrized training script for train and save CV model
    4)train_ner.py - file with parametrized training script for train and save NER model
    5)inference_cv.py - file with parametrized inference script for CV model
    6)inference_ner.py - file with parametrized inference script for NER model
    7)pipeline.py - file to unify inference of 2 models
    8)translator.py - script which is translating default italian dir names to english (for animals10 dataset)
    9)request_generator.py - script to generate synthetic human-like requests for NER model

  ## Installation and Setup

  1) Clone the repository: git clone https://github.com/vozniukivan0501-cmyk/internship_task2
  2) Install dependencies: pip install -r requirements.txt
  3) Do all steps from "Model and Dataset setup"
  4) Run in terminal python src/pipeline.py --request "..." --image_path "..."
    
  
  
  
  
