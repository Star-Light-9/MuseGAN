# MuseGAN

## 🎯Aim
To generate polyphonic music of multiple tracks (instruments) using Generative Adversarial Networks (GANs). The models aims to generate 4 bars of multitrack coherent music from scratch for 5 instruments. We also aim to extend the model for Human-AI collaboration where 4 instrument tracks can be conditionally generated on the basis of one Human input track.

## ⚙️ Tech Stack

| **Category** | **Technologies** |
|---------------|------------------|
| **Programming Languages** | [![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/doc/) |
| **Frameworks** | [![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/docs/stable/index.html) |
| **Libraries** | [![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/doc/) [![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/docs/) [![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)](https://docs.scipy.org/doc/scipy/) [![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)](https://matplotlib.org/stable/contents.html) [![tqdm](https://img.shields.io/badge/tqdm-003366?style=for-the-badge)](https://tqdm.github.io/docs/tqdm/) [![os](https://img.shields.io/badge/os-808080?style=for-the-badge)](https://docs.python.org/3/library/os.html) [![torch](https://img.shields.io/badge/torch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/docs/stable/torch.html) |
| **Deep Learning Models** | [![GAN](https://img.shields.io/badge/GAN-FF0000?style=for-the-badge)](https://arxiv.org/abs/1406.2661) [![CNN](https://img.shields.io/badge/CNN-0A84FF?style=for-the-badge)](https://cs231n.github.io/convolutional-networks/) [![WGAN-GP](https://img.shields.io/badge/WGAN--GP-FF8800?style=for-the-badge)](https://arxiv.org/abs/1704.00028) |
| **Datasets** | [![LPD-5 Cleansed](https://img.shields.io/badge/LPD--5%20Cleansed-4B0082?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/datasets/cloudoak/lpd-5-cleansed)  |
| **Tools** | [![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/doc) [![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/docs) |
| **Visualization & Analysis** | [![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)](https://matplotlib.org/stable/contents.html) [![pretty_midi](https://img.shields.io/badge/pretty__midi-008080?style=for-the-badge)](https://craffel.github.io/pretty-midi/) [![pypianoroll](https://img.shields.io/badge/pypianoroll-FF69B4?style=for-the-badge)](https://pypianoroll.readthedocs.io/en/latest/) |

## 💃 Model Structure
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

## 📊Data
The [LPD-5 Cleansed dataset](https://www.kaggle.com/datasets/cloudoak/lpd-5-cleansed) is a curated version of the original Lakh Pianoroll Dataset (LPD-5), which itself is derived from the Lakh MIDI Dataset (LMD) containing MIDI files from various sources. It consists of over 60,000 multi-track piano-rolls, each aligned to 4/4 time. 

## 👏 Acknowledgement
- Thanks to everyone at CoC and ProjectX for helping us in the progress of this project. 
- Special shoutout to our mentors [Kavya Rambhia](https://github.com/kavya-r30) and [Swayam Shah](https://github.com/sonu0305) for their support and guidance throughout
