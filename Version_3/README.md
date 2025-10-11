# Model Architecture

<img width="2322" height="926" alt="Model Diagram-1" src="https://github.com/user-attachments/assets/d74c6a25-d465-45b1-b663-daa7344d84cd" />

This model follows the same overview Architecture of Version 2. However, the Temporal Generator (for Version 2) makes the model too large to train on GPUs with lesser VRAMs. This model reduces the Temporal Generator (GTemp) to a single Fully Connected Linear Layer so as to reduce the overall size of model.

