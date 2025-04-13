# 👯‍♀️ Pose Transfer using GANs

This project implements a Pose Transfer pipeline using MediaPipe Pose for keypoint extraction and a U-Net based GAN (Generator + Patch Discriminator) in PyTorch. The model takes a source person and transfers their appearance onto a target pose.

---

## 📁 Project Structure
. ├── dataset/ │ ├── resized_images/ # Resized DeepFashion images │ ├── pose_keypoints.json # MediaPipe extracted keypoints │ └── pose_triplets.json # Source-target pose pairs ├── models/ │ ├── generator.py # U-Net based Generator │ └── discriminator.py # Patch Discriminator ├── train.py # Main training script ├── utils/ │ └── keypoint_utils.py # Keypoint to heatmap conversion ├── requirements.txt └── README.md


---

## 🧠 Pipeline Overview

1. **Keypoint Extraction**:  
   MediaPipe Pose extracts normalized 2D keypoints `(x, y, visibility)` from images.

2. **Triplet Creation**:  
   Pairs of source images and target poses are created randomly to form training samples.

3. **Pose-to-Heatmap**:  
   Keypoints are converted to 18-channel heatmaps for model input.

4. **Model Architecture**:
   - **Generator**: U-Net takes source image + target pose and generates a new image.
   - **Discriminator**: PatchGAN determines if generated images are real or fake.

---

🧪 Dataset
This project uses a resized version of the DeepFashion dataset. You can use any image dataset containing full-body people images.

📊 Results
After training, the generator will be able to produce a new image of the source person in the target pose. Example visualizations and loss curves will be added soon!
