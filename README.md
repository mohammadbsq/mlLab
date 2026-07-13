**To run python in VScode:**
- Need to install extention `Python` and for notebook `Jupyter`
- Python file extention `.py` and Jupyter notebook file extention `.ipynb` that full form is Interactive Python Notebook.
- Require Packages for python `jupyter` and `ipykernel`

**Install uv in arch based linux**
```
sudo pacman -S uv
```
1
**Create Directory**
```
mkdir pyPro
```

**In this directory create virtual environment** 
```
uv venv
# for project specific/ isolated environment
```

**and activate it**
```
source .venv/bin/activate
```

**now install uv pillow here** for CV
```
uv pip install pillow
```

Install `jupyter ipykernel`
```
uv pip install jupyter ipykernel
```

Show python packages 
```
uv pip list
```

For `interactive` kernel 
- Select kernel of `uv venv`


Take existing packages in `requirements.txt` 

```
uv pip freeze > requirements.txt
```


## Console এ File তৈরি করার উপায়:

### সবচেয়ে সহজ — `touch`

```bash
touch main.py
touch index.html
```

### Content সহ — `echo`

```bash
echo "print('hello')" > main.py
```

### Multi-line content — `cat`

```bash
cat > main.py << EOF
def hello():
    print("Hello World")

hello()
EOF
```

### খালি file — `>`

```bash
> main.py
```

---

**সবচেয়ে বেশি ব্যবহার হয়:**

```bash
touch main.py   # খালি file বানাতে
```


## ML Project — Standard Reference

---

### Project Creation

```bash
uv init mllab --python 3.12
cd mllab
uv add --dev ruff pytest ipykernel
uv add numpy pandas scikit-learn matplotlib jupyter
rm main.py
#nested folder creation
mkdir -p data/raw data/processed notebooks src models outputs
touch src/data_prep.py src/train.py src/utils.py
touch notebooks/01_eda.ipynb
echo "data/" >> .gitignore
```

---

### Git Init

```bash
git init
git add .
git commit -m "Initial project structure"
git branch -M main 
git remote add origin https://github.com/'username'/'repository'.git
git push
```

---

### Standard Pipeline

```
Train (sklearn/PyTorch)
        ↓
Track (MLflow)
        ↓
Export (ONNX)
        ↓
Serve (FastAPI)
        ↓
Deploy (Docker)
```

---

### প্রতিটা Step কী করে

|Step|Tool|কাজ|
|---|---|---|
|**Train**|sklearn / PyTorch|Model বানাও|
|**Track**|MLflow|Experiment save করো|
|**Export**|ONNX|Universal format এ convert করো|
|**Serve**|FastAPI|API বানাও|
|**Deploy**|Docker|সব package করো|

---

### Daily Git Workflow

```bash
# কাজ শুরুতে
git pull

# কাজ শেষে
git add .
git commit -m "feat: description"
git push
```

---

