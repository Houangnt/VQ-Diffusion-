# VQ-Diffusion-
Text-To-Image
#Data Preparing
Microsoft COCO
│MSCOCO_Caption/
├──annotations/
│  ├── captions_train2014.json
│  ├── captions_val2014.json
├──train2014/
│  ├── train2014/
│  │   ├── COCO_train2014_000000000009.jpg
│  │   ├── ......
├──val2014/
│  ├── val2014/
│  │   ├── COCO_val2014_000000000042.jpg
│  │   ├── ......
CUB-200
│CUB-200/
├──images/
│  ├── 001.Black_footed_Albatross/
│  ├── 002.Laysan_Albatross
│  ├── ......
├──text/
│  ├── text/
│  │   ├── 001.Black_footed_Albatross/
│  │   ├── 002.Laysan_Albatross
│  │   ├── ......
├──train/
│  ├── filenames.pickle
├──test/
│  ├── filenames.pickle
#Result after train model on MSCOCO_Dataset

#Some Pretrain model support for training
Openimages: https://drive.google.com/uc?id=1HAl78FcWlZdzqj8CHrA8DNf14XSzvNy6 
CLIP: https://drive.google.com/uc?id=1qhdlE0l8hkKsakqfHotQueXuTx3sVbPV 
after download 2 file weight above, set path link to 2 file pretrain Openimages, CLIP in file coco.yaml 
#Training 
First, change the data_root to correct path in configs/coco.yaml or other configs.
Train Text2Image generation on MSCOCO dataset:
python running_command/run_train_coco.py
Train Text2Image generation on CUB200 dataset:
Train Text2Image generation on CUB200 dataset:
