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
