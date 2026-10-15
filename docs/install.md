# Environments
We train and test on the below setting.
CUDA==11.8,
Python==3.10.18,
torch==2.6.0

```bash
ENV_NAME="hogwarts_test"
conda create --name $ENV_NAME python=3.10.18
conda activate $ENV_NAME
```

# Requirements
Install torch following the instructions below, or you can choose your version according to your CUDA.

```bash
pip install torch==2.6.0 torchvision==0.21.0 --index-url https://download.pytorch.org/whl/cu118
```

Install other requirements.

```bash
pip install -r requirements.txt
```

Install additional requirements for the demo.

```bash
pip install -r requirements-demo.txt
```

## torchgeometry library

Please follow below before run the code:

you need to change L301~L304 of `~/anaconda3/envs/hogwarts/lib/python3.10/site-packages/torchgeometry/core/conversions.py` to below.

```bash
mask_c0 = mask_d2.float() * mask_d0_d1.float()
mask_c1 = mask_d2.float() * (1 - mask_d0_d1.float())
mask_c2 = (1 - mask_d2.float()) * mask_d0_nd1.float()
mask_c3 = (1 - mask_d2.float()) * (1 - mask_d0_nd1.float())
```
