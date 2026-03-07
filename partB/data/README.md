# Dataset Information

## Source
The dataset is generated programmatically using `sklearn.datasets.make_classification` inside each notebook. No external data files need to be downloaded.

## Configuration
- **Number of samples**: 500
- **Number of features**: 10 (all informative)
- **Number of classes**: 2
- **Random seed**: 42
- **Train/Test split**: 70/30

## How It Is Used
Each positive sample from the training set is treated as an "exemplar" (analogous to a PASCAL VOC object instance in the original paper). A separate linear SVM is trained for each exemplar with that sample as the sole positive and all samples from the other class as negatives.

## Limitations Compared to Original Paper
- The original paper uses HOG descriptors extracted from image windows; we use raw feature vectors.
- The original paper considers millions of candidate negative windows via sliding-window detection; our negative set is the opposite class in a fixed-size dataset.
- The dataset is much smaller and lower-dimensional than PASCAL VOC 2007.
