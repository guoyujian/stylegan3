通过stylegan v3生成一些黑色素瘤皮肤镜图像，后来没用到也没做完。。。

源项目地址：https://github.com/NVlabs/stylegan3
项目的使用参见README_origin.md
也可以看看视频：https://www.bilibili.com/video/BV1Pt4y1x7P9/?spm_id_from=333.880.my_history.page.click

训练参数配置：https://github.com/NVlabs/stylegan3/blob/main/docs/configs.md

训练报错：TypeError: 'tuple' object is not callable 的解决方法：https://github.com/NVlabs/stylegan3/issues/188

训练：
```python 
python train.py --outdir=./training-runs --cfg=stylegan3-r --data=./datasets/mel.zip --gpus=1 --batch=32 --gamma=2 --mirror=1 --batch-gpu=8 --snap=10 --kimg=5000 
```

可选参数：--metrics=none

--resume=<pkl> 从指定的ckpt继续训练。

python train.py --outdir=./training-runs --cfg=stylegan3-r --gpus=1 --batch=32 --gamma=0.5 --batch-gpu=16 --snap=10


python train.py --outdir=./training-runs --cfg=stylegan3-r --data=./datasets/asan.zip --gpus=1 --batch=32 --gamma=0.5 --mirror=1 --batch-gpu=16 --snap=10 --kimg=5000 --resume=

已经生成的图片：fakes001000.png
checkppoint: network-snapshot-001280.pkl ，继续训练可以从这个开始。 (我也没上传。。)
训练数据太多就不上传了，这些训练数据是从ISIC2018中的黑色素瘤+色素痣两类提取并处理之后的。