device:RTX4070ti 14600kf wsl-ubuntu20.04

```bash
conda create --name UniMODE -y python=3.8
conda activate UniMODE

pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 -f https://download.pytorch.org/whl/torch_stable.html

pip install openmim
pip install mmcv-full==1.7.0 -f https://download.openmmlab.com/mmcv/dist/cu111/torch1.9/index.html
pip install mmdet==v2.28.2
pip install mmsegmentation==0.30.0
pip install mmdet3d==v1.0.0rc4

pip install cython opencv-python timm transformers einops ftfy opencv-python-headless tensorboardX tensorflow rope ninja
pip install 'git+https://github.com/cocodataset/cocoapi.git#subdirectory=PythonAPI'

git clone https://github.com/facebookresearch/detectron2.git
python -m pip install -e detectron2

git clone https://github.com/facebookresearch/pytorch3d.git
cd pytorch3d
pip install -e .
cd ..

pip install flash-attn==1.0.4
pip install spconv-cu113==2.2.2


python setup_voxel_pooling.py develop

pip install setuptools==59.5.0
pip install Pillow==8.2.0
pip install numba==0.56.4

cd model/deformable_ops
python setup.py develop
cd ../..
```

```bash
(UniMODE) remake@DianaCavendish:~$ conda list
# packages in environment at /home/remake/miniconda3/envs/UniMODE:
#
# Name                    Version                   Build  Channel
_libgcc_mutex             0.1                        main
_openmp_mutex             5.1                       1_gnu
absl-py                   2.1.0                    pypi_0    pypi
addict                    2.4.0                    pypi_0    pypi
aliyun-python-sdk-core    2.16.0                   pypi_0    pypi
aliyun-python-sdk-kms     2.16.5                   pypi_0    pypi
antlr4-python3-runtime    4.9.3                    pypi_0    pypi
astunparse                1.6.3                    pypi_0    pypi
black                     24.8.0                   pypi_0    pypi
ca-certificates           2025.2.25            h06a4308_0
cachetools                5.5.2                    pypi_0    pypi
ccimport                  0.4.4                    pypi_0    pypi
certifi                   2025.1.31                pypi_0    pypi
cffi                      1.17.1                   pypi_0    pypi
charset-normalizer        3.4.1                    pypi_0    pypi
click                     8.1.8                    pypi_0    pypi
cloudpickle               3.1.1                    pypi_0    pypi
colorama                  0.4.6                    pypi_0    pypi
contourpy                 1.1.1                    pypi_0    pypi
crcmod                    1.7                      pypi_0    pypi
cryptography              44.0.2                   pypi_0    pypi
cudatoolkit               11.3.1              h9edb442_10    conda-forge
cumm-cu113                0.5.3                    pypi_0    pypi
cycler                    0.12.1                   pypi_0    pypi
cython                    3.0.12                   pypi_0    pypi
decorator                 5.2.1                    pypi_0    pypi
descartes                 1.1.0                    pypi_0    pypi
detectron2                0.6                       dev_0    <develop>
einops                    0.8.1                    pypi_0    pypi
exceptiongroup            1.2.2                    pypi_0    pypi
filelock                  3.14.0                   pypi_0    pypi
fire                      0.7.0                    pypi_0    pypi
flake8                    7.1.2                    pypi_0    pypi
flash-attn                1.0.4                    pypi_0    pypi
flatbuffers               25.2.10                  pypi_0    pypi
fonttools                 4.56.0                   pypi_0    pypi
fsspec                    2025.2.0                 pypi_0    pypi
ftfy                      6.2.3                    pypi_0    pypi
fvcore                    0.1.5.post20221221          pypi_0    pypi
gast                      0.4.0                    pypi_0    pypi
google-auth               2.38.0                   pypi_0    pypi
google-auth-oauthlib      1.0.0                    pypi_0    pypi
google-pasta              0.2.0                    pypi_0    pypi
grpcio                    1.70.0                   pypi_0    pypi
h5py                      3.11.0                   pypi_0    pypi
huggingface-hub           0.29.1                   pypi_0    pypi
hydra-core                1.3.2                    pypi_0    pypi
idna                      3.10                     pypi_0    pypi
imageio                   2.35.1                   pypi_0    pypi
importlib-metadata        8.5.0                    pypi_0    pypi
importlib-resources       6.4.5                    pypi_0    pypi
iniconfig                 2.0.0                    pypi_0    pypi
iopath                    0.1.9                    pypi_0    pypi
jmespath                  0.10.0                   pypi_0    pypi
joblib                    1.4.2                    pypi_0    pypi
keras                     2.13.1                   pypi_0    pypi
kiwisolver                1.4.7                    pypi_0    pypi
lark                      1.2.2                    pypi_0    pypi
ld_impl_linux-64          2.40                 h12ee557_0
libclang                  18.1.1                   pypi_0    pypi
libffi                    3.4.4                h6a678d5_1
libgcc-ng                 11.2.0               h1234567_1
libgomp                   11.2.0               h1234567_1
libstdcxx-ng              11.2.0               h1234567_1
llvmlite                  0.39.1                   pypi_0    pypi
lyft-dataset-sdk          0.0.8                    pypi_0    pypi
markdown                  3.7                      pypi_0    pypi
markdown-it-py            3.0.0                    pypi_0    pypi
markupsafe                2.1.5                    pypi_0    pypi
matplotlib                3.5.3                    pypi_0    pypi
mccabe                    0.7.0                    pypi_0    pypi
mdurl                     0.1.2                    pypi_0    pypi
mmcls                     0.25.0                   pypi_0    pypi
mmcv-full                 1.7.0                    pypi_0    pypi
mmdet                     2.28.2                   pypi_0    pypi
mmdet3d                   1.0.0rc4                 pypi_0    pypi
mmsegmentation            0.30.0                   pypi_0    pypi
model-index               0.1.11                   pypi_0    pypi
multiscaledeformableattention 1.0                       dev_0    <develop>
mypy-extensions           1.0.0                    pypi_0    pypi
narwhals                  1.29.0                   pypi_0    pypi
ncurses                   6.4                  h6a678d5_0
networkx                  2.2                      pypi_0    pypi
ninja                     1.11.1.3                 pypi_0    pypi
numba                     0.56.4                   pypi_0    pypi
numpy                     1.23.5                   pypi_0    pypi
nuscenes-devkit           1.1.11                   pypi_0    pypi
oauthlib                  3.2.2                    pypi_0    pypi
omegaconf                 2.3.0                    pypi_0    pypi
opencv-python             4.11.0.86                pypi_0    pypi
opencv-python-headless    4.11.0.86                pypi_0    pypi
opendatalab               0.0.10                   pypi_0    pypi
openmim                   0.3.9                    pypi_0    pypi
openssl                   3.0.16               h5eee18b_0
openxlab                  0.1.2                    pypi_0    pypi
opt-einsum                3.4.0                    pypi_0    pypi
ordered-set               4.1.0                    pypi_0    pypi
oss2                      2.17.0                   pypi_0    pypi
packaging                 24.2                     pypi_0    pypi
pandas                    2.0.3                    pypi_0    pypi
pathspec                  0.12.1                   pypi_0    pypi
pccm                      0.4.16                   pypi_0    pypi
pillow                    8.2.0                    pypi_0    pypi
pip                       24.2             py38h06a4308_0
platformdirs              4.3.6                    pypi_0    pypi
plotly                    6.0.0                    pypi_0    pypi
pluggy                    1.5.0                    pypi_0    pypi
plyfile                   1.0.3                    pypi_0    pypi
portalocker               3.0.0                    pypi_0    pypi
prettytable               3.11.0                   pypi_0    pypi
protobuf                  4.25.6                   pypi_0    pypi
pyasn1                    0.6.1                    pypi_0    pypi
pyasn1-modules            0.4.1                    pypi_0    pypi
pybind11                  2.13.6                   pypi_0    pypi
pycocotools               2.0.7                    pypi_0    pypi
pycodestyle               2.12.1                   pypi_0    pypi
pycparser                 2.22                     pypi_0    pypi
pycryptodome              3.21.0                   pypi_0    pypi
pyflakes                  3.2.0                    pypi_0    pypi
pygments                  2.19.1                   pypi_0    pypi
pyparsing                 3.1.4                    pypi_0    pypi
pyquaternion              0.9.9                    pypi_0    pypi
pytest                    8.3.5                    pypi_0    pypi
python                    3.8.20               he870216_0
python-dateutil           2.9.0.post0              pypi_0    pypi
pytoolconfig              1.3.1                    pypi_0    pypi
pytorch3d                 0.7.8                     dev_0    <develop>
pytz                      2023.4                   pypi_0    pypi
pywavelets                1.4.1                    pypi_0    pypi
pyyaml                    6.0.2                    pypi_0    pypi
readline                  8.2                  h5eee18b_0
regex                     2024.11.6                pypi_0    pypi
requests                  2.28.2                   pypi_0    pypi
requests-oauthlib         2.0.0                    pypi_0    pypi
rich                      13.4.2                   pypi_0    pypi
rope                      1.13.0                   pypi_0    pypi
rsa                       4.9                      pypi_0    pypi
safetensors               0.5.3                    pypi_0    pypi
scikit-image              0.19.3                   pypi_0    pypi
scikit-learn              1.3.2                    pypi_0    pypi
scipy                     1.10.1                   pypi_0    pypi
setuptools                59.5.0                   pypi_0    pypi
shapely                   1.8.5.post1              pypi_0    pypi
six                       1.17.0                   pypi_0    pypi
spconv-cu113              2.2.2                    pypi_0    pypi
sqlite                    3.45.3               h5eee18b_0
tabulate                  0.9.0                    pypi_0    pypi
tensorboard               2.13.0                   pypi_0    pypi
tensorboard-data-server   0.7.2                    pypi_0    pypi
tensorboardx              2.6.2.2                  pypi_0    pypi
tensorflow                2.13.1                   pypi_0    pypi
tensorflow-estimator      2.13.0                   pypi_0    pypi
tensorflow-io-gcs-filesystem 0.34.0                   pypi_0    pypi
termcolor                 2.4.0                    pypi_0    pypi
terminaltables            3.1.10                   pypi_0    pypi
threadpoolctl             3.5.0                    pypi_0    pypi
tifffile                  2023.7.10                pypi_0    pypi
timm                      1.0.15                   pypi_0    pypi
tk                        8.6.14               h39e8969_0
tokenizers                0.20.3                   pypi_0    pypi
tomli                     2.2.1                    pypi_0    pypi
torch                     1.9.0+cu111              pypi_0    pypi
torchvision               0.10.0+cu111             pypi_0    pypi
tqdm                      4.65.2                   pypi_0    pypi
transformers              4.46.3                   pypi_0    pypi
trimesh                   2.35.39                  pypi_0    pypi
typing-extensions         4.5.0                    pypi_0    pypi
tzdata                    2025.1                   pypi_0    pypi
urllib3                   1.26.20                  pypi_0    pypi
voxelpooling              0.0.1                     dev_0    <develop>
wcwidth                   0.2.13                   pypi_0    pypi
werkzeug                  3.0.6                    pypi_0    pypi
wheel                     0.44.0           py38h06a4308_0
wrapt                     1.17.2                   pypi_0    pypi
xz                        5.6.4                h5eee18b_1
yacs                      0.1.8                    pypi_0    pypi
yapf                      0.43.0                   pypi_0    pypi
zipp                      3.20.2                   pypi_0    pypi
zlib                      1.2.13               h5eee18b_1
```
