# MuseGAN 

## 🧠 Overview
MuseGAN model generates polyphonic music of multiple tracks (instruments) using Generative Adversarial Networks (GANs). The models aims to generate 4 bars of multitrack coherent music from scratch for 5 instruments. We also aim to extend the model for Human-AI collaboration where 4 instrument tracks can be conditionally generated on the basis of one Human input track.
Checkout the [GitHub Repo](https://github.com/Star-Light-9/MuseGAN)

---

## 🎯 Objectives
- Generate multi-track Pianorolls music consisting of 5 tracks (drums, bass, guitar, piano, strings).  
- Learn temporal and harmonic relationships across bars and tracks 
- The model is built on CGANs with Wasserstein Loss and Gradient Penalty
---

## 📂 Dataset
### Lakh Pianoroll Dataset (LPD-5 Cleansed)
Derived from the Lakh MIDI Dataset (LMD) and contains over 60,0000 5-track multitrack pianorolls.  
Piano Rolls are a matrix representation of music where the horizontal axis denotes Time-steps, the vertical axis denotes Pitches and a particular point on the matrix stores a Velocity value (loudness of note)
---

## 🧩 Model Structure
The whole MuseGAN model is primarily split into 2 parts - Multitrack and Temporal Models.

### Multi-Track Model
This is further split into 3 types of models: Composer, Jamming and Hybrid models

<img width="400" height="350" alt="image" src="https://github.com/user-attachments/assets/3521f6d0-e0fa-4ce6-a3bd-b05c0f9eec4e" />

- #### Composer Model
It is responsible for creating a uniformity across instruments of all the tracks by using a single generator and a single discriminator.
- #### Jamming Model
It is responsible for giving each instrument tracks its characteristic style by using 5 generators and discriminators for 5 tracks.
- #### Hybrid Model
The Hybrid Model merges both composer and jamming model into one single model using a global vector *Z* and 5 track-dependent vectors *Z<sub>i</sub>*

### Temporal Model
This model is responsible for encoding bar-specific temporal encodings to the latent vectors. Temporal Model also has two types:

- #### Generation From Sratch 
A Temporal Generator (*GTemp*) is used when 5 coherent tracks are to be generated from scratch.
- #### Conditional Generation
If a conditional track input is provided, A Temporal Encoder is used to encode the temporal characteristics of human-input track into the latent vectors.


### Overall Structure
<img width="600" height="200" alt="image" src="https://github.com/user-attachments/assets/d6bef2d8-74dd-438e-8bcf-a2204d3a3ea2" />

This incorporates both Temporal Generators and Bar Generators and consists of a Global Latent Vector, z, Global Temporal Vector, Z<sub>t</sub>, Track Dependent Latent Vectors, Z<sub>i</sub>, and Track Dependent Temporal Vectors, Z<sub>it</sub> 


---

## 💃 Model Versions & Outputs

### Version 1

![WhatsApp Image 2025-10-10 at 01 07 57_738d2936](https://github.com/user-attachments/assets/27d00a7c-5d2f-4d82-a1fa-c59f3949e5d8)

- **Shared Temporal Generator**: Takes two noise vectors and upscales them, this is the temporal context of music - to be given to Private Temporal Generator.
- **Private Temporal Generator**: Takes combined vector containing two outputs from bar generator as well as other two directly passed to it and gives the content for one track.
- **Bar Generator**: Takes the 5 bars generated from the Private Temporal Generator and combines them to form a pianoroll.

**Outputs**

<img width="672" height="567" alt="image" src="https://github.com/user-attachments/assets/b926765e-d4f7-49e5-a967-e3168d6676db" />

### Version 2
<img width="2322" height="926" alt="Model Diagram-1" src="https://github.com/user-attachments/assets/d9c2c820-261b-4ea0-a529-1d25d541cf36" />

- **Temporal Generator:** Takes in the Global Latent Vector,  Z, and Track-dependent Latent Vector, Z<sub>i</sub>, and Generates the Temporal Latent Vectors, Z<sub>t</sub> and Z<sub>it</sub> 

- **Bar Generator:** Takes all the 4 Latent Vectors and generates the pianoroll Bar-by-Bar for every track.

**Outputs**

<img width="1418" height="1178" alt="image" src="https://github.com/user-attachments/assets/9d6c568a-a046-4b85-9151-7cff35801390" />

Outputs of this model 120 epochs

**Checkpoint**

Checkpoints after 120 epochs for this model can be found [here](https://www.kaggle.com/datasets/pratyushrao/musegan-trained-checkpoint-120-epochs/data/data)


### Conditional Generation


![WhatsApp Image 2025-10-10 at 15 35 50_a77b8a0f](https://github.com/user-attachments/assets/084d9045-3254-47cf-ad04-376a9f79c8ac)

The Conditional Generator involves a Temporal Encoder which encodes Temporal structure of the input track in a latent vector and feeds it to the Generator Model of Version-1. Rest of the Generator remains same as the Version 1 Codes. The Generator, here, in all outputs 4 Tracks with similar Temporal Structure across bars as the input track. 


**Outputs**

![f5c4b6b6-e1ff-49a2-af0c-df16836ad01f](https://github.com/user-attachments/assets/02bcc0b9-4b67-447f-af9f-041067b28a8b)

Outputs of Model After 25th Epoch 

**Checkpoint**

The Checkpoints for this model after 25 epochs can be found [here](https://www.kaggle.com/datasets/pratyushrao/musegan-conditional-track-ckpt-25-epooch)



## 🚂 How To Train The Model
- Install the dependencies
  
    `pip install -r requirements`
  
- Go to the particular version folder you want to train and download the `.ipynb` file.
- Run the Nbk locally or in JupyterLab Notebooks 
- To access the trained checkpoint for a particular model, check the `README.md` file in the particular Version's folder

## 🎼 Outputs
To access the output audio, check out the Audio folder under the version Folder

## 👏 Acknowledgement
- Thanks to everyone at CoC and ProjectX for helping us in the progress of this project. 
- Special shoutout to our mentors [Kavya Rambhia](https://github.com/kavya-r30) and [Swayam Shah](https://github.com/sonu0305) for their support and guidance throughout

**Made By [Pratyush Rao](https://github.com/PratyushRao) and [Yashasvi Choudhary](https://github.com/Star-Light-9)**