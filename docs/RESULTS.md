# Official V2 results

Only the official leakage-controlled V2 model is used for final reporting and application inference.

## Evaluation summary

| Metric | Value |
|---|---:|
| Test images | 313 |
| Correct predictions | 288 |
| Test accuracy | 92.01% |
| Macro F1-score | 0.9119 |
| Weighted F1-score | 0.9209 |

The test set was held out from training and contained within the leakage-controlled V2 split. The complete classification report, confusion matrix, representative predictions, incorrect-case analysis, and Grad-CAM visualisations are stored as outputs in `notebooks/HeritageLens_Model_Training.ipynb`.

## Interpretation

Accuracy reports the overall percentage of correct test predictions. Macro F1 gives equal importance to every architectural class, while weighted F1 accounts for the number of test images in each class. Reporting both values is important because the class distribution is not perfectly balanced.

The results demonstrate strong five-class performance on the held-out dataset, but they do not guarantee correct classification for every real-world building. Mixed architectural styles, partial façades, unusual viewpoints, low-resolution images, and geographically different examples remain difficult cases.
