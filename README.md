# ProjectAI_Group20_AI-Plant-Classification

# Plant Subspecies Image Classification using Convolutional Neural Networks (CNN)

## 📌 Course Details
* **Institute:** Universiti Kuala Lumpur - Malaysian Institute of Information Technology (UniKL MIIT)
* **Course Name:** Principle of Artificial Intelligence
* **Course Code:** ISB46703
* **Lecturer:** Ahmad Zhafri Hariz Bin Roslan
* **Semester & Year:** March 2026
* **Assessment:** Project Assignment (20%)

---

## 👥 Group Members & Roles
We have divided our group of three into the distinct roles required by the project guidelines to handle the machine learning pipeline efficiently:

* **Muhammad A’isy Rizqi** — **Data Engineer**
  * *Responsibilities:* Data collection, image standardization, configuration of preprocessing pipelines, and dataset partitioning (70% Train, 15% Val, 15% Test).
* **Muhamad Aqasha** — **Data Scientist**
  * *Responsibilities:* Model architecture creation (ResNet50, DenseNet121, MobileNetV3), transfer learning implementation, and model training/hyperparameter tuning.
* **Mohamad Aiman Danish** — **Data Analyst**
  * *Responsibilities:* Training performance tracking, evaluation visualization (Loss/Accuracy curves, Confusion Matrix), testing dataset assessment, and final model comparative analysis.

---

## 📊 Dataset Selection & Justification

### Selected Domain: Plant Subspecies
Our group selected the **Plant Subspecies** domain out of the 5 allowable tracks. 

### Why We Chose This Data:
1. **High Visual Variance for Deep Learning:** Subspecies classification provides a realistic challenge for deep learning models. Different types of plants share similar green features, stems, and shapes, making it an excellent benchmark to test the feature-extraction capabilities of complex CNN networks like ResNet and DenseNet.
2. **Data Cleanliness and Structure:** We utilized the official TensorFlow `flower_photos` archive, capturing **3,670 images** divided across **5 distinct classes**:
   * *Daisy*
   * *Dandelion*
   * *Roses*
   * *Sunflowers*
   * *Tulips*
3. **Optimized for Deadline & Computational Efficiency:** Rather than spending critical time dealing with broken links, corrupted files, and unverified data from a manual web crawler, downloading a verified archive allowed us to immediately focus on data preparation and modeling constraints. It ensures 100% of the images are authentic, high-quality representations of the sub-classes.

### Data Engineering & Standardization Applied:
* **Image Resizing:** All images were automatically standardized to a uniform resolution of **224x224 pixels**. This step is vital because pre-trained architectures (specifically ResNet50 and MobileNetV3) natively require this size format to avoid dimension errors.
* **Dataset Splitting:** The data was systematically split using a strict **70/15/15 ratio** to meet the rubric requirements:
  * **Training Set (70%):** Used by the Data Scientist to teach features to the models.
  * **Validation Set (15%):** Used to check for overfitting during training epochs.
  * **Testing Set (15%):** Reserved entirely as unseen data for final validation by the Data Analyst.

---

## 🛠️ Project Architecture & Pipeline

The project is structured within a unified Google Colab environment using a shared pipeline:

1. **Phase 1: Data Preparation** *(Completed)*
   * Automated loading via `tf.keras.utils.image_dataset_from_directory`.
   * Input caching and `prefetch(buffer_size=AUTOTUNE)` optimization applied to clear RAM/GPU latency.
2. **Phase 2: Data Modelling** *(In Progress)*
   * Training 3 distinct Keras models for **50 epochs** each:
     * **ResNet50**
     * **DenseNet121**
     * **MobileNetV3**
   * Metrics tracked: Accuracy and mAP (Mean Average Precision), along with execution runtimes.
3. **Phase 3: Data Visualization** *(Pending)*
   * Generation of performance metrics (Loss and Accuracy graphs).
   * Deployment of Evaluation Confusion Matrices to deduce structural classification weaknesses.
