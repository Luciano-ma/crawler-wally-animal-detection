Abstract
Edge computing on mobile marine platform is paramount for automated ecological monitoring. The goal of demonstrating the computational feasibility of an Artificial Intelligence (AI)-powered camera for fully automated real-time species-classification on deep-sea crawler platforms was searched by running You-Only-Look-Once (YOLO) model on an edge computing device (NVIDIA Jetson Nano), to evaluate the achievable animal detection performances, execution time and power consumption, using all the available cores. We processed a total of 337 rotating video scans (∼180°), taken during approximately 4 months in 2022 at the methane hydrates site of Barkley Canyon (Vancouver Island; BC; Canada), focusing on three abundant species (i.e., Sablefish Anoplopoma fimbria, Hagfish Eptatretus stoutii, and Rockfish Sebastes spp.). The model was trained on 1926 manually annotated video frames and showed high detection test performances in terms of accuracy (0.98), precision (0.98), and recall (0.99). The trained model was then applied on 337 videos.
In 288 videos we detected a total of 133 Sablefish, 31 Hagfish, and 321 Rockfish nearly in real-time (about 0.31 s/image) with very low power consumption (0.34 J/image). Our results have broad implications on intelligent ecological monitoring. Indeed, YOLO model can meet operational-autonomy criteria for fast image processing with limited computational and energy loads.



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


