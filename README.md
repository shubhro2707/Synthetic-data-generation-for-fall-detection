![image](https://github.com/user-attachments/assets/3e2b5962-1a40-4bfb-8d76-65f392113e0b)

# **Synthetic CSI Data Generation for Fall Detection Using Variational Autoencoders (VAE)**  

## **Data Sources**  
For this project, I worked with two primary data sources:  
1. **CSI (Channel State Information)** – Contains **timestamp, phase, amplitude, and RSSI**.  
2. **True Data** – Collected using an **accelerometer**, measuring acceleration across the **x, y, and z** axes.  

---  

## **Data Collection Procedure**  
I designed the data collection process as follows:  

1. **Accelerometer Placement:** Attached to the subject’s **arm** or **waist**.  
2. **Wi-Fi Signal Transmission:** Traffic was generated between a **router** and a **Wi-Fi chipset** (ESP32, Picoscenes, Nexmon).  
3. **Fall Scenarios:** Different types of **falls** were performed within the **line of sight** of the Wi-Fi system.  
4. **Data Labeling:**  
   - **0 → Non-fall**  
   - **1 → Fall**  
5. **Noise Filtering:** Applied to enhance signal quality before processing.  
6. **Feature Extraction:** Selected **top subcarriers** for further processing using **Variational Autoencoder (VAE)**.  

---  

## **What is a Variational Autoencoder (VAE)?**  
A **VAE** is a deep learning model that learns to generate new data **similar** to its training set. It consists of:  

- **Encoder:** Compresses input data into a **low-dimensional latent space**.  
- **Decoder:** Reconstructs the **original data** or generates **new synthetic samples** from the latent space.  

---  

## **How VAE Generates Synthetic CSI Data**  

### **Step 1: Train VAE on Real CSI Data**  
- Collected **CSI data** for different activities (**falling, walking, sitting, etc.**).  
- Trained **Encoder** to map CSI data into a **compact latent space**.  
- Trained **Decoder** to reconstruct CSI data from the latent space.  
- The **VAE** learned the **underlying distribution** of CSI signals.  

### **Step 2: Generate Synthetic CSI Data**  
- Sampled **new latent representations** from the trained model.  
- Passed these representations through the **Decoder** to generate synthetic **CSI data**.  
- Ensured quality by monitoring **Reconstruction Loss & KL Divergence**.  

This approach significantly improves **fall detection models** by providing **diverse and realistic synthetic data**, enhancing model generalization and robustness.
