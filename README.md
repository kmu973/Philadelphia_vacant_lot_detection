# Identifying Vacant Lots in Philadelphia for Community Garden Development Using Satellite Imagery and Deep Learning
### Authors: Teresa Chang (MCP), Minwook Kang (MUSA)
# 1. Introduction
## 1.1 Problem statement
Philadelphia's Land Bank's 2021 Strategic Plan identifies over 40,000 vacant parcels of land within the city. This project seeks to leverage deep learning models to automate the identification of vacant parcels using satellite imagery, providing insights into the distribution of unused land and facilitating urban planning processes.

## 1.2 Motivation
The deep learning model developed in this project aims to identify vacant lots in Philadelphia using satellite imagery, enabling the City of Philadelphia to explore new uses for vacant land management, such as community gardens, parks, and greenways. The model can also support the Philadelphia Community Garden Project in efficiently identifying potential garden sites and evaluating the impact of their efforts.

# 2. Data
## 2.1 Data Source and Collection
Higher-resolution aerial imagery (1/2ft) from Penn State University was utilized. The Philadelphia area dataset consists of 70 tiles (20,000 x 20,000).

## 2.2 Data preprocessing and cleaning
Ten tiles were labeled using Vacant Property Indicators. Images and label data were split into 2,000 x 2,000 segments, resulting in a total of 1,000 training datasets. Image augmentation was used to compensate for data scarcity, resulting in 1,410 training sets. Images were down-sampled to 512 x 512 for model compatibility.

# 3. Method
## 3.1 Deep learning models used
Three main models were employed:

U-Net, a convolutional neural network architecture
Modified U-Net incorporating the pre-trained MobileNetV2 as its encoder
U-Net architecture with an EfficientNetB0 backbone

## 3.2 Model Tuning and Optimization
The model was designed to work effectively with satellite imagery by accepting input images with a shape of (512, 512, 3). Custom metrics such as Intersection over Union (IoU), Dice coefficient, and F1 score were implemented for performance optimization. Callbacks like early stopping and custom plot metrics were used during the training process.

# 4. Results
## 4.1 Model performance
The modified U-Net with MobileNetV2 encoder (Model 2) demonstrated superior results across all considered metrics and was chosen as the optimal model for the given task.

## 4.2 Prediction Result Visualization
A sample of 10 predictions from the validation set showed that the model's performance in predicting vacant lots was considerably more accurate than initially anticipated.

# 5. Discussion
## 5.1 Practical applications and implications
The model can help monitor long-term changes in the total area of vacant lots in Philadelphia, enabling the city to better manage vacant land and inform urban planning processes.

## 5.2 Future work and improvement
Future work can focus on exploring alternative deep learning architectures, applying transfer learning, optimizing hyperparameters, incorporating techniques such as data augmentation and regularization, developing ensemble models, and improving the training and validation process.

# 6. Conclusion
The deep learning model based on the U-Net architecture was successful in automating the identification of vacant parcels in Philadelphia using high-resolution satellite imagery. Future work can focus on enhancing the model's generalizability and optimizing its performance, leading to a more robust and effective tool for analyzing urban land use and promoting sustainable urban development.
