# Model Architecture

<img width="2322" height="926" alt="Model Diagram-1" src="https://github.com/user-attachments/assets/d9c2c820-261b-4ea0-a529-1d25d541cf36" />

### Temporal Generator 
Takes in the Global Latent Vector,  Z, and Track-dependent Latent Vector, Z<sub>i</sub>, and Generates the Temporal Latent Vectors, Z<sub>t</sub> and Z<sub>it</sub> 

### Bar Generator
Takes all the 4 Latent Vectors and generates the pianoroll Bar-by-Bar for every track.


# Checkpoints
Checkpoints after 120 epochs for this model can be found [here](https://www.kaggle.com/datasets/pratyushrao/musegan-trained-checkpoint-120-epochs/data/data)
