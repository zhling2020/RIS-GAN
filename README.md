# RIS-GAN
This repository contains TensorFlow code for the paper titled "RIS-GAN: Explore Residual and Illumination with Generative Adversarial Networks for Shadow Removal" [pdf](https://arxiv.org/abs/1911.09178) (http://www.chengjianglong.com/publications/RISGAN_AAAI.pdf).

##RIS-GAN Architecture
Attached below is the architecture diagram of RIS-GAN as given in the paper.


## Notes: 
1. The GAN component is dervied from paper "Single Image Haze Removal using a Generative Adversarial Network". 
2. This RIS-GAN can be used for any application, and is not limited to Shadow removal. 

## Requirements:
- TensorFlow (version 1.4+)
- Matplotlib
- Numpy
- Scikit-Image

## Instructions:
1. We use the pretrained VGG-19 on the ImageNet dataset to calculate Perceptual loss. 
    We used the weights provided by [machrisaa](https://github.com/machrisaa/tensorflow-vgg)'s implementation. Download the weights from this [link](https://mega.nz/#!xZ8glS6J!MAnE91ND_WyfZ_8mvkuSa2YcA7q-1ehfSm-Q1fxOvvs) and include it in this repository.

2. Download the dataset.
- We used the [ISTD](https://drive.google.com/file/d/1I0qw65KBA6np8vIZzO6oeiOvcDBttAY/view?usp=sharing) dataset for training. The shadow images and corresponding shadow-free images will be placed in directories `A` and `B` respectively. 

3. In case you want to use your own dataset, follow these instructions. If not, skip this step.
- Create two directories `A` and `B` in this repository. 
- Place the input images into directory `A` and target images into directory `B`. 
- Ensure that an input and target image pair has the **same name**, otherwise the program will throw an error (For instance, if `1.jpg` is present in `A` it must also be present in `B`). 

4. Train the model by using the following code. 
```
python main.py --A_dir A --B_dir B --mode train
```
The file `main.py` supports a lot of parameters, which are given a default value. You can set a new value to suit your needs.

5. Test by using the follwing code.
```
python main.py --A_dir shadow --B_dir result --mode inference
```

##Sample results
Attached below are some shadow removal results from the test set.


### Citation
If you use the code in your own research, please cite:
```
@InProceedings{Zhang:AAA2020,  
  title = {RIS-GAN: Explore Residual and Illumination with Generative Adversarial Networks for Shadow Removal},
  author = {Zhang, Ling and Long, Chengjiang and Zhang, Xiaolong and Xiao, Chunxia},
  booktitle = {AAAI Conference on Artificial Intelligence (AAAI)},
  year = {2020}
}
```

Depending on the setup you use, consider also citing paper "Single Image Haze Removal using a Generative Adversarial Network".
