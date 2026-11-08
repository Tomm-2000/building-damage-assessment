# Building Damage Assessment

Computer vision experiments using the Roboflow xView2 v4 export. The primary notebook fine-tunes YOLOv8n for object detection. A separate ResNet50 experiment uses the first annotated box to assign an image-level class.

| Notebook | Workflow |
| --- | --- |
| [Building damage detection](building-damage-detection.ipynb) | Download data, train YOLOv8n, evaluate on the validation split, and optionally predict on a local image |
| [ResNet50 classification experiment](resnet50-classification-experiment.ipynb) | Organize images by their first box label, train a classifier, and evaluate it on the test split |

## Run locally on Windows

From the repository folder, in PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
$env:ROBOFLOW_API_KEY = Read-Host -MaskInput "Roboflow API key" # PowerShell 7+
.\.venv\Scripts\python.exe -m jupyterlab
```

On Windows PowerShell 5.1, set the environment variable through your system settings or launch Jupyter from PowerShell 7. Run the cells in order. The first run needs internet access for the dataset and pretrained weights. A GPU is useful for training. If memory is limited, reduce the batch size and image size. The repository contains the notebooks and setup files. The data and trained checkpoints are generated or downloaded locally.

The original notebooks were reorganized for local use. Results depend on the dataset export and training environment.
