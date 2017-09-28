# Traffic_Light_Localization_Recognition (WIP Repo)

## How to Fine-Tune:
1. Install TF object detection API  https://github.com/tensorflow/models/tree/master/research/object_detection

2. Download ssd_mobilenet_v1_coco https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/detection_model_zoo.md

3. Download Bosch traffic light dataset https://hci.iwr.uni-heidelberg.de/node/6132

4. Create following folders: `checkpoints`, `data`, `input`

### Training Command
`python train.py --pipeline_config_path=ssd_mobilenet_v1_coco.config --train_dir=./checkpoints`

### Inference Graph Builder
`python export_inference_graph.py \
    --input_type image_tensor \
    --pipeline_config_path ./ssd_mobilenet_v1_coco.config \
    --trained_checkpoint_prefix ./checkpoints/model.ckpt-20 \
    --output_directory ./model`
