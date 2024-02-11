## **Create Virtual Environment (VE)**
```bash
conda create -n [name of VE] python=3.6
```

## Activate VE
```bash
source activate [name of VE]
```
## **Export dependencies of VE using `pip freeze`**
```bash
pip freeze > requirements.txt
```
## **Create VE using `pip freeze`**
```bash
pip install -r requirements.txt
```

## **Export dependencies of VE using `yml-file`**
```bash
conda env export --no-builds > environment.yml
```

## **Create VE using `yml-file`**
```bash
conda env create -f environment.yml
```

## **Print list of VE**
```bash
conda env list
```

## **Remove VE**
```bash
conda env remove -n [name of VE]
```

## **Basic PYthon Packages**
```bash
pip install numpy pandas scikit-learn matplotlib seaborn scipy statsmodels
```

## **How to check library dependencies**
```bash
conda search --info pandas | grep -E '(^version|numpy)'
```
