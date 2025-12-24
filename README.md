# Plant Disease Detection 

This project uses a convolutional neural network (CNN) to classify plant leaf diseases from images. The notebook can train a model from the dataset or load a pretrained model and run single-image predictions.

## Project files
- Plant Disease Detection Code.ipynb: main notebook
- Dataset/: image dataset folder (ImageFolder format)
- disease_info.csv: disease label mapping
- plant_disease_model_1_latest.pt: pretrained model weights
- test_images/: sample images for prediction

## Requirements
- Python 3.8+ (Anaconda is fine)
- Jupyter Notebook or JupyterLab
- Packages: numpy, pandas, matplotlib, torch, torchvision, pillow

Example install (Anaconda prompt):

```
conda install -y numpy pandas matplotlib pytorch torchvision cpuonly -c pytorch
pip install pillow
```

If you have a GPU and a compatible CUDA setup, install the CUDA build of PyTorch instead of cpuonly.

## How to run (Jupyter)
1) Open a terminal in this project folder.
2) Start Jupyter:

```
jupyter notebook
```

3) Open `Plant Disease Detection Code.ipynb`.
4) Select a Python kernel that has the required packages.
5) Run cells top to bottom (Shift+Enter), or use "Kernel -> Restart & Run All".

## Paths expected by the notebook
- Dataset directory: `Dataset/`
- CSV file: `disease_info.csv`
- Pretrained model: `plant_disease_model_1_latest.pt`

Make sure these are present in the project root (same folder as the notebook).

## Final output (single image prediction)
The notebook defines a helper called `single_prediction(image_path)`. Run this cell after the model is loaded, then call it with an image path:

```
single_prediction("test_images/tomato_bacterial_spot.JPG")
```

Expected output:
- A line that prints the original filename
- The predicted disease name (from `disease_info.csv`)

## Notes
- The warning about `torchvision` weights is safe to ignore, or update the model load code to the new `weights=` API.
- Training is time-consuming; if you only want predictions, skip the training cell(s) and load `plant_disease_model_1_latest.pt`.

## Troubleshooting
- If `Dataset` is missing or empty, the notebook will fail when creating the `ImageFolder`.
- If `torchvision` or `torch` is not installed in the selected kernel, install packages and restart the kernel.
- If the model file is missing, either train the model or place `plant_disease_model_1_latest.pt` in the project root.
