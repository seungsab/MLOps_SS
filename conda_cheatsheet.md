## **Create Virtual Environment (VE)**
```bash
conda create -n [name of VE] python=3.6
```

## Activate VE
```bash
source activate [name of VE]
```

## **Export dependencies of VE using yml-file**
```bash
conda env export --no-builds > environment.yml
```

## **Create VE using yml-file**
```bash
conda env create -f environment.yml
```
