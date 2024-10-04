# Named Entity Recognition and Coreference Resolution Using Prompt-based Generative Multimodal Techniques
This paper mainly studies multimodal co-reference resolution. For the problem of pronoun image correspondence in the co-reference resolution task, we propose a generative multimodal co-reference resolution model with an enhanced prompt. This co-reference resolution model uses an advanced prompt strategy to incorporate the pronoun information proposed in named entity recognition into the image, guiding the model to generate more accurate reference information, thereby effectively integrating semantic clues in multimodal data and enhancing the accuracy and efficiency of co-reference resolution.


# Dependence
This code requires the following:
python 3.8

# Prepare dataset
Create a folder: datasets/

# Training
To save the models create a folder and then run the training script below for the final model. saved/final_model<br>
```--use_env main.py --use-ema --use-ssl --model_config configs/mcr_config.json --batch 8 --ssl_loss con --label-prop --bbox-reg --grounding --save_name final_model/```

# Evaluation
## For coreference resolution
This test script will save the predicted coreference chains in the folder. Create this directory prior to running the script.coref/modelrefs/test
```--use_env test_coref.py  --bbox-reg --use-phrase-mask --model_config configs/mcr_config.json --save_name saved/final_model/models_30.pt```
## For narrative grounding
```--use_env test_grounding.py  --bbox-reg --use-phrase-mask --model_config configs/mcr_config.json --save_name saved/final_model/models_30.pt```

# truth coreference annotations
