
- train yolov8 on COD-5_640x640_moderate_augmentation dataset

yolo task=detect mode=train model=yolov8n.yaml batch=-1 workers=8 data="COD-5_640x640_moderate_augmentation/data.yaml" epochs=150 name='DOD-5_moderate_augmentation'

- validate the model 

yolo task=detect mode=val model='CONVERGED_WEIGHTS/best.pt' data="DOD-5_moderate_augmentation/data_val.yaml"

- to run yolov8 on the Jetson nano board follow the guides: 

   1) https://docs.ultralytics.com/guides/nvidia-jetson/#why-should-i-use-tensorrt-for-deploying-yolov8-on-nvidia-jetson

   2) https://www.youtube.com/watch?v=X9jt8qb_igo

  using the model CONVERGED_WEIGHTS/best.pt
