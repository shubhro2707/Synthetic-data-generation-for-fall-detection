![image](https://github.com/user-attachments/assets/3e2b5962-1a40-4bfb-8d76-65f392113e0b)

# **Synthetic CSI Data Generation for Fall Detection Using Variational Autoencoders (VAE)**  

## **Data Sources**  
- **CSI (Channel State Information):** Contains **timestamp, phase, amplitude, and RSSI**.  
- **True Data:** Collected using an **accelerometer** (measuring acceleration across x, y, and z axes).  

---  

## **Data Collection Procedure**  
1. **Accelerometer Placement:** Attached to the subject’s **arm or waist**.  
2. **Wi-Fi Signal Transmission:** Traffic generated between a **router and a Wi-Fi chipset**.  
3. **Fall Scenarios:** Different types of falls occur **within the line of sight**.  
4. **Data Labeling:**  
   - **0 → Non-fall**  
   - **1 → Fall**  
5. **Noise Filtering:** Applied to enhance signal quality.  
6. **Feature Extraction:** Top **subcarriers** selected for further processing with **VAE (Variational Autoencoder)**.  

---  

## **What is a Variational Autoencoder (VAE)?**  
A **VAE** is a deep learning model that learns to **generate new data** similar to its training set. It consists of:  
- **Encoder:** Compresses input data into a **low-dimensional latent space**.  
- **Decoder:** Reconstructs the original data or generates new synthetic samples from this latent space.  

---  

## **How VAE Generates Synthetic CSI Data**  

### **Step 1: Train VAE on Real CSI Data**  
- Collect CSI data for **falling, walking, sitting**, etc.  
- Train **Encoder** to map CSI data into a compact **latent space**.  
- Train **Decoder** to reconstruct CSI data from the latent space.  
- The VAE learns the **underlying distribution** of CSI signals.  

### **Step 2: Generate Synthetic CSI Data**  
- Sample **new latent representations** from the trained model.  
- Pass these representations through the **Decoder** to generate synthetic CSI data.  
- Ensure quality by monitoring **Reconstruction Loss** & **KL Divergence**.  

This approach improves fall detection models by providing **more diverse and realistic training data**.
