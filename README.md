# VQ-Diffusion-
Text-To-Image <br />
<br />
# Data Preparing <br />
Microsoft COCO <br />
│MSCOCO_Caption/ <br />
├──annotations/ <br />
│  ├── captions_train2014.json <br />
│  ├── captions_val2014.json <br />
├──train2014/ <br />
│  ├── train2014/ <br />
│  │   ├── COCO_train2014_000000000009.jpg <br />
│  │   ├── ...... <br />
├──val2014/ <br />
│  ├── val2014/ <br />
│  │   ├── COCO_val2014_000000000042.jpg <br />
│  │   ├── ...... <br />
<br />
<br />
CUB-200 <br />
│CUB-200/ <br />
├──images/ <br />
│  ├── 001.Black_footed_Albatross/ <br />
│  ├── 002.Laysan_Albatross <br />
│  ├── ...... <br />
├──text/ <br />
│  ├── text/ <br />
│  │   ├── 001.Black_footed_Albatross/ <br />
│  │   ├── 002.Laysan_Albatross <br />
│  │   ├── ...... <br />
├──train/ <br />
│  ├── filenames.pickle <br />
├──test/ <br />
│  ├── filenames.pickle <br />
<br />
<br />
# Result after train model on MSCOCO_Dataset<br />

Some Pretrain model support for train model <br />
Openimages: https://drive.google.com/uc?id=1HAl78FcWlZdzqj8CHrA8DNf14XSzvNy6  <br />
CLIP: https://drive.google.com/uc?id=1qhdlE0l8hkKsakqfHotQueXuTx3sVbPV  <br />
after download 2 file weight above, set path link to 2 file pretrain Openimages, CLIP in file coco.yaml  <br />
File weight after train model on LAION-Human Dataset : https://drive.google.com/file/d/12py7Zx3JdMjcoRQRx3bxqA-NkMGLM55o/view?usp=sharing
<br />
<br />
# Training 
First, change the data_root to correct path in configs/coco.yaml or other configs. <br />
Train Text2Image generation on MSCOCO dataset: <br />
python running_command/run_train_coco.py <br />
Train Text2Image generation on CUB200 dataset: <br />
python running_command/run_train_cub.py <br />
<br />
<br />
# Inference 
from inference_VQ_Diffusion import VQ_Diffusion < br /> 
VQ_Diffusion_model = VQ_Diffusion(config='OUTPUT/pretrained_model/config_text.yaml', path='OUTPUT/pretrained_model/coco_pretrained.pth') <br />
VQ_Diffusion_model.inference_generate_sample_with_condition("a beautiful woman",truncation_rate=0.85, save_root="RESULT",batch_size=4)  <br />
VQ_Diffusion_model.inference_generate_sample_with_condition("a young girl in blue skirt",truncation_rate=0.85, save_root="RESULT",batch_size=4,fast=2) # for fast inference <br />
<br /> 
<br />
# cite VQ-Diffusion <br />
article{gu2021vector, <br />
  title={Vector Quantized Diffusion Model for Text-to-Image Synthesis}, <br />
  author={Gu, Shuyang and Chen, Dong and Bao, Jianmin and Wen, Fang and Zhang, Bo and Chen, Dongdong and Yuan, Lu and Guo, Baining}, <br />
  journal={arXiv preprint arXiv:2111.14822}, <br />
  year={2021} <br />
} <br />
