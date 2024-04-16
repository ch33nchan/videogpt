```bash
git clone https://github.com/ch33nchan/videogpt
cd videoGPT
conda create -n videollava python=3.10 -y
conda activate videollava
pip install --upgrade pip  # enable PEP 660 support
pip install -e .
pip install -e ".[train]"
pip install flash-attn --no-build-isolation
pip install eva-decord opencv-python git+https://github.com/facebookresearch/pytorchvideo.git@28fe037d212663c6a24f373b94cc5d478c8c1a1d
```

now if you want to run an image query run this : 
```bash
CUDA_VISIBLE_DEVICES=0 python -m videollava.serve.cli --model-path "LanguageBind/Video-LLaVA-7B" --file "path/to/your/image.jpg" --load-4bit
```
if it's a video : 
```bash
CUDA_VISIBLE_DEVICES=0 python -m videollava.serve.cli --model-path "LanguageBind/Video-LLaVA-7B" --file "path/to/your/video.mp4" --load-4bit
```
