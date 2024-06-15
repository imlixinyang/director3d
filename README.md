
<p align="center">
<!--   <h1 align="center"><img height="100" src="https://github.com/imlixinyang/director3d-page/raw/master/assets/icon.ico"></h1> -->
  <h1 align="center">🎥 <b>Director3D</b>: Real-world Camera Trajectory and 3D Scene Generation from Text</h1>
  <p align="center">
        <a href="http://arxiv.org/abs/2404.11613"><img src='https://img.shields.io/badge/arXiv-Director3D-red?logo=arxiv' alt='Paper PDF'></a>
        <a href='https://imlixinyang.github.io/director3d-page'><img src='https://img.shields.io/badge/Project_Page-Director3D-green' alt='Project Page'></a>
        <a href='https://colab.research.google.com/drive/1LtnxgBU7k4gyymOWuonpOxjatdJ7AI8z?usp=sharing'><img src='https://img.shields.io/badge/Colab_Demo-Director3D-yellow?logo=googlecolab' alt='Project Page'></a>
  </p>

<img src='assets/pipeline.gif'>

**🔥 News**:

- 🥰 Check out our new gradio demo by simply running ```python app.py```.

<img width=300 src='assets/demo.png'>


- 🆓 Try out Director3D for free with our [**Google Colab Demo**](https://colab.research.google.com/drive/1LtnxgBU7k4gyymOWuonpOxjatdJ7AI8z?usp=sharing).

## 📖 Generation Results

❗ All videos are rendered with generated camera trajectories and 3D Gaussians, the only inputs are text prompts!

https://github.com/imlixinyang/director3d/assets/26456614/2dc0ea45-b7a6-46ed-afc8-2359a43e0a54

👀 See more than 200 examples in our [**Gallery**](https://imlixinyang.github.io/director3d-page/gallery_0.html).


## 🔧 Installation
- create a new conda enviroment

```
conda create -n director3d python=3.9
conda activate director3d
```

- install pytorch (or use your own if it is compatible with ```xformers```)
```
conda install pytorch==2.0.1 torchvision==0.15.2 torchaudio==2.0.2 pytorch-cuda=11.7 -c pytorch -c nvidia
```
- install ```xformers``` for momory-efficient attention
```
conda install xformers -c xformers
```
- install ```pip``` packages
```
pip install kiui scipy opencv-python-headless kornia omegaconf imageio imageio-ffmpeg  seaborn==0.12.0 plyfile ninja tqdm diffusers transformers accelerate timm einops matplotlib plotly typing argparse gradio kaleido
pip install "git+https://github.com/facebookresearch/pytorch3d.git@stable"
pip install "git+https://github.com/ashawkey/diff-gaussian-rasterization.git"
```

- clone this repo:
```
git clone https://github.com/imlixinyang/director3d.git
cd director3d
```

- download the pre-trained model by:
```
wget https://huggingface.co/imlixinyang/director3d/resolve/main/model.ckpt?download=true -O model.ckpt
```

## 🧐 General Usage

You can generate 3D scenes with camera trajectories by running the following command:
``` bash
python inference.py --export_all --text "a delicious hamburger on a wooden table."
```

This will take about 5 minutes per sample on a single A100 GPU (or 7 minutes per sample on a single RTX 3090 GPU).
The results can be found in ``./exps/tmp``.

## 💡 Code Overview

Core code of three key components of Director3D can be found in:

- Cinematographer - Trajectory Diffusion Transformer (Traj-DiT) 
```
system_traj_dit.py
```

- Decorator - Gaussian-driven Multi-view Latent Diffusion Model  (GM-LDM) 
```
system_gm_ldm.py
gm_ldm.py
```

- Detailer - SDS++
```
modules/refiners/sds_pp_refiner.py
```

<!-- ## 🚀 GUI Demo

Also, you can try out with GUI:

``` bash
python gradio_app.py
``` -->

<!-- ## Acknowledgement -->
 
## Citation

```
```


## License

Licensed under the CC BY-NC-SA 4.0 (Attribution-NonCommercial-ShareAlike 4.0 International)


The code is released for academic research use only. 

If you have any questions, please contact me via [imlixinyang@gmail.com](mailto:imlixinyang@gmail.com). 

#### 👊 I'm looking for research collaboration in Real-world 3D/4D/Video Generation, please contact me if you're interested.