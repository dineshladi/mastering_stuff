## Python Setup
### Run python in background with avoiding output flushing 

```bash
nohup python3 -u script.py > output.log & 
```

### Launch Jupyter from Python virtual environment
```bash
## create venv 
python3 -m venv project_name
## activate venv
source project_name/bin/activate 
## Install ipykernel in the environment 
python3 -m pip install ipykernel
## create ipykernel for the environment 
ipython kernel install --user --name=project_name
```

## PyTorch
### Class weights in cross entropy loss 
```python
import torch
import numpy as np 
from torch import nn 
### df is dataframe, target is the target column
DEVICE = torch.device("cuda" if torch.cuda.is_available() else "cpu")
class_weights = np.unique(df[target].values, return_counts=True)[1]
class_weights = np.max(class_weights)/class_weights
class_weights = torch.from_numpy(class_weights).to(DEVICE)
criterion = nn.CrossEntropyLoss(weight = class_weights)
```
