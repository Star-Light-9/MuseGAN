## Model Architechture

![WhatsApp Image 2025-10-10 at 15 35 50_a77b8a0f](https://github.com/user-attachments/assets/084d9045-3254-47cf-ad04-376a9f79c8ac)

The Conditional Generator involves a Temporal Encoder which encodes Temporal structure of the input track in a latent vector and feeds it to the Generator Model of Version-1. Rest of the Generator remains same as the Version 1 Codes. The Generator, here, in all outputs 4 Tracks with similar Temporal Structure across bars as the input track. 


## Outputs

![f5c4b6b6-e1ff-49a2-af0c-df16836ad01f](https://github.com/user-attachments/assets/02bcc0b9-4b67-447f-af9f-041067b28a8b)

Outputs of Model After 25th Epoch 

## Checkpoint
The Checkpoints for this model after 25 epochs can be found [here](https://www.kaggle.com/datasets/pratyushrao/musegan-conditional-track-ckpt-25-epooch)
