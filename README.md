# Classification of breast histopathological slides using transfer learning
This code partially follows the Keras blog post "Building powerful image classification models using very little data". Breast Cancer Histopathological Database (BreakHis) has been used as the dataset. It can be found [here](https://web.inf.ufpr.br/vri/databases/breast-cancer-histopathological-database-breakhis/).

## Rationale
Labelled data in biomedical tasks is typically rare and when present, is usually insuficient to train a deep network from scratch. To overcome this problem, transfer learning can be used. It involves extracting features using a pre-trained network (here, VGG16 pre-trained on the ImageNet datset is used), and removing the last fully connected layer, in place of which a different classifier may be used. How well the chosen pre-trained CNN classifies images belonging to a different task than those it was trained on can then be studied.

## Setting up the procedure
The BreakHis dataset consists of 7909 images of microscopic slides of breast tumors. The images belong to 82 different patients and have been taken at 4 maginfying factors (40X, 100X, 200X, 400X of the same slide). The data is separated into 2 main classes - benign and malignant, with 4 further subclasses. The above figures are examples of images for the 2 main classes and correspond to 200X magnification.
In this experiment, image classification was performed for 'benign' and 'malignant' classes. The model was trained only for the 200X magnified images. The dataset contained 623 Benign and 1390 Malignant images corresponding to 200X magnification. To train the model using balanced data, 500 images per class were taken randomly for training, and 100 images were taken for validation.

