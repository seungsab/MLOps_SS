## **Create Virtual Environment (VE)**
```bash
conda create -n [name of VE] python=3.6
```

## Activate VE
```bash
source activate [name of VE]
```

## **Export dependencies of VE using yaml-file**
```bash
conda env export --no-builds > environment.yaml
```

## **Create VE using yaml-file**
```bash
conda env create -f environment.yaml
```
