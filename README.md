## Fine tuning the whisper-small (244M) multilingual model on Mozilla common voice dataset for uzbek language

### Whisper is a Transformer based encoder-decoder model, also referred to as a sequence-to-sequence model. It was trained on 680k hours of labelled speech data annotated using large-scale weak supervision.

### I will train the modes on [Common-voice-8-0](https://huggingface.co/datasets/mozilla-foundation/common_voice_8_0) dataset (uzbek language). The Model will be trained on the task of speech recognition. For speech recognition, the model predicts transcriptions in the same language as the audio.


## Dataset size is 0.43 GB because of the hardware limitations

## Model is trained on P100 GPU with 16 GB of VRAM on Kaggle for 9.7 hours


### It achieves the following results on the evaluation set:
- Loss: 0.3743
- Wer: 29.1593


### Training results

| Training Loss | Epoch  | Step | Validation Loss | Wer     |
|:-------------:|:------:|:----:|:---------------:|:-------:|
| 0.3146        | 1.3514 | 1000 | 0.4122          | 35.3898 |
| 0.1332        | 2.7027 | 2000 | 0.3529          | 29.7356 |
| 0.0256        | 4.0541 | 3000 | 0.3658          | 29.2881 |
| 0.0134        | 5.4054 | 4000 | 0.3743          | 29.1593 |


### Training hyperparameters

The following hyperparameters were used during training:
- learning_rate: 1e-05
- train_batch_size: 16
- eval_batch_size: 8
- seed: 42
- optimizer: Adam with betas=(0.9,0.999) and epsilon=1e-08
- lr_scheduler_type: linear
- lr_scheduler_warmup_steps: 500
- training_steps: 4000
- mixed_precision_training: Native AMP



## Fine tuned model with all the output files.
### [Model](https://huggingface.co/azamat45/whisper-small-uz)
