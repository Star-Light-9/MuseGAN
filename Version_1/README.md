**Model Architechture**

![WhatsApp Image 2025-10-10 at 01 07 57_738d2936](https://github.com/user-attachments/assets/27d00a7c-5d2f-4d82-a1fa-c59f3949e5d8)

- **Shared Temporal Generator**: Takes two noise vectors and upscales them, this is the temporal context of music - to be given to Private Temporal Generator.
- **Private Temporal Generator**: Takes combined vector containing two outputs from bar generator as well as other two directly passed to it and gives the content for one track.
- **Bar Generator**: Takes the 5 bars generated from the Private Temporal Generator and combines them to form a pianoroll.

**Outputs**

- **Pianoroll**
<img width="672" height="567" alt="image" src="https://github.com/user-attachments/assets/b926765e-d4f7-49e5-a967-e3168d6676db" />

- **Generator Loss**
<img width="778" height="556" alt="image" src="https://github.com/user-attachments/assets/0351af9d-ffe3-4755-a628-47327e6d899f" />


- **Discriminator Loss**
<img width="760" height="574" alt="image" src="https://github.com/user-attachments/assets/df9b0600-6f0d-4db4-be56-c18666f18acd" />


**Checkpoints**

Refer to .pth files for respective epoch and checkpoints.

