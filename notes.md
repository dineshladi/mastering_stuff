
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

### Dynamic quantisation of a model
```python
import torch
model = Model()
# quantize the linear layers
quantized_model = torch.quantization.quantize_dynamic(model, {torch.nn.Linear}, dtype=torch.qint8)
torch.save(quantized_model.state_dict(), model_path)
```

## PySpark
### Install Apache Spark 2.4.7 on MacOS
```bash
brew cask install java8
brew install scala@2.11
wget https://downloads.apache.org/spark/spark-2.4.7/spark-2.4.7-bin-hadoop2.7.tgz
export SPARK_HOME="/Users/d0l06db/Documents/spark-2.4.7-bin-hadoop2.7"
export PATH="$SPARK_HOME/bin/:$PATH"
chmod +x /Users/d0l06db/Documents/spark-2.4.7-bin-hadoop2.7/bin/*
export PYSPARK_PYTHON=/usr/bin/python3
export PYSPARK_DRIVER_PYTHON=/usr/bin/python3
```

### Value Counts 
```python
def value_counts(df, col):
    return df.groupBy(col).count().orderBy('count', ascending=False)

```
### Shape of dataframe
```python
def shape(df):
    return (df.count(),len(df.columns))
```

### Missing Values in each column of a dataFrame
```python

```

