

<div align="center">
	<img src="./img/skydiffusion_icon.png" alt="" height=75>
	<h1>Ground-to-Aerial Image Synthesis with  Diffusion Models and BEV Paradigm</h1>
</div>


<img src="./img/pipeline.jpg" alt="">


## 🏆 Contributions

**Main methods：** We introduce SkyDiffusion, a novel ground-to-aerial synthesis method leveraging diffusion models and BEV paradigm to generate realistic, consistent aerial images.

**Method innovation details：** We design a Curved-BEV method to transform street-view images into satellite views for domain alignment. It also includes "Multi-to-One" mapping strategy to enhance BEV perception range in densely occluded urban areas.

**Dataset Contribution：** We introduce Ground2Aerial-3, a new ground-to-aerial image synthesis dataset, featuring disaster scene aerial image, historical high-resolution satellite image, and low-altitude UAV image

**Experimental results：** We introduce Ground2Aerial-3, a new ground-to-aerial image synthesis dataset, featuring disaster scene aerial image, historical high-resolution satellite image, and low-altitude UAV image

## 🛠️ Requirements and Installation
Clone this repo to a local folder:
```bash
git clone https://github.com/SkyDiffusion/SkyDiffusion-code.git
cd SkyDiffusion-code
```

We provide an available conda environment named skydiffusion. You can configure the necessary Python environment for the experiments by following these steps:
```bash
conda create --name skydiffusion python=3.9
conda activate skydiffusion
conda env update --name skydiffusion --file environment.yaml
```

## 🤗 Data Preparation
The publicly available datasets used in this paper can be obtained from the following sources: 

**Preparing G2A-3 Dataset.**  The dataset can be downloaded [here](https://huggingface.co/datasets/SkyDiff1109/G2A-3). 

**Preparing CVUSA Dataset.**  The dataset can be downloaded [here](https://mvrl.cse.wustl.edu/datasets/cvusa). 

**Preparing CVACT Dataset.**  The dataset can be downloaded [here](https://github.com/Liumouliu/OriCNN). 

**Preparing VIGOR Dataset.**  The dataset can be downloaded [here](https://github.com/Jeff-Zilence/VIGOR/tree/main). 

After unzipping the datasets, prepare the training and testing data as discussed in our paper.



## 🚀 Quick Start
Generating Aerial Images Using Our Pre-trained Model. Use the provided pre-trained model to generate aerial images according to the following code:
```bash
python test.py \
    --num_gpus=8 \
    --config_path=./models/lacldm_v15.yaml \
    --image_width=512 --image_height=512 \
    --result_dir= [Output folder] \
    --model_path=./ckpt/CVACT_SkyDiffusion.ckpt \
    --data_file_path=./examples/examples.csv \
    --dataset_name=CVACT
```

## License

This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for details.
