![image](https://github.com/user-attachments/assets/3e2b5962-1a40-4bfb-8d76-65f392113e0b)

Data: CSI (Channel State Information). Consists of timestamp, phase, amplitude and RSSI

True data : Accelerometer (calculation of acceleration accross x,y and z axis)

Procedure:
1. Accelerometer attached to the subject's arm or waist.

2. Traffic being generated between router and the wifi chipset.

3. Types of falls occuring in the line of sight

4. Data labelling done for the entire duration of data (0 for non fall and 1 for fall)

5. Filters are further used for noise removal.

6. Next, feature extraction techniques are used to select the top subcarriers that will be pushed further to the VAE (Variational Autoencoder Architecture)

Using Variational Autoencoders (VAE) for Synthetic CSI Data Generation in Fall Detection

1. What is a VAE?
A Variational Autoencoder (VAE) is a type of neural network that can learn to generate new data similar to the data it was trained on. It consists of two main parts:

Encoder: Compresses input data into a smaller, meaningful representation (latent space).
Decoder: Uses this compressed representation to reconstruct the original data or generate new synthetic data.

2. Why Use VAE for CSI-Based Fall Detection?
CSI (Channel State Information) data captures changes in Wi-Fi signals, which can help detect human activities, including falls.
Real fall data is rare and difficult to collect, so generating synthetic CSI data can improve model training.
VAEs learn important patterns from real CSI data and can generate realistic but new data that mimics actual falls and non-falls.

3. How VAE Generates Synthetic CSI Data?

Step 1: Train VAE on Real CSI Data
Collect CSI data for different activities (falling, walking, sitting, etc.).
Train the Encoder to map CSI data into a low-dimensional latent space (compressed representation).
Train the Decoder to reconstruct the original CSI data from this latent space.
The VAE learns the underlying distribution of CSI signals.

Step 2: Generate Synthetic CSI Data
After training, sample new latent representations (slightly modified versions of learned patterns).
Pass these latent representations through the Decoder to create new synthetic CSI data.
The generated CSI data will be similar but not identical to real fall and non-fall samples.

Reconstruction loss and KL divergence to monitor quality of training.


