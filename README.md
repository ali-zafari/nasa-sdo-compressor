# NASA SDO Neural Image Compression
This is a minimal working code to evaluate a pre-trained simple neural compression model on Solar Dynamics Observatory (SDO) images. This code is based on [CompressAI](https://github.com/InterDigitalInc/CompressAI), but to keep it uncluttered a tiny clone of the package is provided here.

Model definition can be found in [`tiny_compressai/models/nasa.py`](tiny_compressai/models/nasa.py).

## Usage
A local clone of the CompressAI is provided (`tiny_compressai`) to make the model integration easier.

### Installation
In a virtual environment follow the steps below (verified on Ubuntu):
```bash
git clone https://github.com/ali-zafari/nasa-sdo-compressor nasa_compressor
cd nasa_compressor
pip install -U pip
pip install -e .
```

### Evaluation
For bulk data evaluation of a saved checkpoint, `compressai.utils.eval` is used. An example to test the rate-distoriton perfomance of a NASACompressor checkpoint:

```bash
python -m tiny_compressai.utils.eval_model checkpoint path/to/data/directory  -a nasa-compressor --cuda -v -p path/to/a/checkpoint
```
To download a set of data and a checkpoint: [Sample Data + Pretrained Network](#sample-data--pretrained-network)

## Jupyter Notebook
A jupyter notebook ([compression_evaluation.ipynb](compression_evaluation.ipynb)) is also provided to make clear the procedure of model instantation and single image evaluation.
Use the following command to install Jupyter before running the notebook.
```bash
pip install jupyterlab
```

## Sample Data + Pretrained Network
- [32 SDO images for test](https://drive.google.com/file/d/1Mhiuy3jOkhikD2QRENaXIynOrgljkukH/view?usp=sharing)
- [PyTorch Pretrained Model](https://drive.google.com/file/d/1AdEbdvYql747zV-vL8qqwWZADhhHFRwZ/view?usp=sharing)
