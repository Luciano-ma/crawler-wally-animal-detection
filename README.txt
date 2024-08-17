Files description:

- CONVERGED_WEIGHTS.zip zipped folder containining the converged weights last.pt and best.pt
- FINAL_COUNT.xls excell file containing the name of the video and the corresponding total number of individuals for the detected species
- Out.txt command line script for training and terminal output
- val_Train_DOD-5_moderate_augmentation_no_pretrained.zip zipped folder containining the validation results (confusion matrix, Precision, Recall,...) on the training set.

- val_Test_DOD-5_moderate_augmentation_no_pretrained.zip zipped folder containining the validation results (confusion matrix, Precision, Recall,...) on the test set.

- val_val_DOD-5_moderate_augmentation_no_pretrained.zip zipped folder containining the validation results (confusion matrix, Precision, Recall,...) on the validation set.

- test.zip zipped folder containing the test set (image and labels).

- train yolov8 on COD-5_640x640_moderate_augmentation dataset

- To run the training process lunch 
yolo task=detect mode=train model=yolov8n.yaml batch=-1 workers=8 data="COD-5_640x640_moderate_augmentation/data.yaml" epochs=150 name='DOD-5_moderate_augmentation'

- To run the validation process lunch 

yolo task=detect mode=val model='CONVERGED_WEIGHTS/best.pt' data="DOD-5_moderate_augmentation/data_val.yaml"

- to run yolov8 on the Jetson nano board follow the guides: 

   1) https://docs.ultralytics.com/guides/nvidia-jetson/#why-should-i-use-tensorrt-for-deploying-yolov8-on-nvidia-jetson

   2) https://www.youtube.com/watch?v=X9jt8qb_igo

  using the model CONVERGED_WEIGHTS/best.pt
