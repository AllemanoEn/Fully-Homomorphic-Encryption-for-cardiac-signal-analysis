# Project description
Data from electrocardiograms (ECGs) are normally analyzed by someone with the skills to identify the presence of atrial fibrillation (AF). This operation can also be performed by an AF detection algorithm. Medical data such as ECGs have a critical level of privacy and must be kept confidential even when analyzed by an untrusted entity.

This Bachelor's thesis carries out a study involving fully homomorphic encryption (FHE) and ECG data. The aim is to analyze the feasibility of applying different AF detection algorithms with FHE. 

The choice of FHE scheme was _Fast Fully Homomorphic Encryption over the Torus_ (TFHE) and the choice of ECG databases was _MIT-BIH Arrhythmia Database_ and the database proposed by the company AliveCore at the _2017 Physionet Challenge_.

To reach a conclusion, the following methodology was carried out:

- adapt each step of the algorithm in question to our use case
- implement the algorithm without FHE
- reimplement functions not supported by the TFHE homomorphic encryption scheme
- adapt the data to be analyzed and the algorithm in question to the limitations of the Concrete framework
- compare the simple result with the result obtained using homomorphic encryption
- analyze the result and draw a conclusion from it


The results of these different analyses show that the biggest problem we face is having to nest all the steps of a AF detection algorithm within the same FHE function. However, the results show that it was possible to calculate a heart rate in real time, using an ECG encrypted with FHE.

To continue this analysis, it would be interesting to look at other AF detection algorithms with different homomorphic encryption schemes, and therefore different FHE libraries.

This GitLab repository contains all the analyses and research carried out for this Bachelor's thesis.

# Requirements
Before running the project, please ensure you have the following points installed on your system:

1. Python 3.10.12
2. Python 3.6.15 (not needed if you do not want to re-extract ECG signals)
3. Jupyter Notebook 

As this repository has been developed using visual studio code, we recommend that you also use it to run this repository.

# Installation
This repo extract ECG signals from two other GitHub projects :
- [Pan_Tompkins_QRS_Detection](/Pan_Tompkins_QRS_Detection)([original repo](https://github.com/antimattercorrade/Pan_Tompkins_QRS_Detection))
- [ecg-features](/ecg-features)([original repo](https://github.com/Seb-Good/ecg-features))

If you just want to execute the `.ipynb` file at the projet root, you only need a python 3.10.12 venv.

> :warning: **ECG signals DB need to be re-downloaded** in the `AF_detection_with_ECG_heart_rate.ipynb ` file, it can take some time.

It's recommended to setup two python venv. 
- one for the whole project
- one for the `ecg-features` directory

Follow the steps below to create separate virtual environments and install the required dependencies.

_The following instructions were tested on Linux OS_

## Creating a Virtual Environment for Python 3.10.12 (Project Root)
```bash
python3.10 -m venv venv_3.10.12
source venv_3.10.12/bin/activate
```

## Installing Dependencies for Python 3.10.12 (Project Root)
With the virtual environment active, use the package manager `pip` to install the project dependencies from the requirements.txt file:

Creating a Virtual Environment for Python 3.10.12 (Project Root)
```bash
pip install -r requirements.txt
```

## Creating a Virtual Environment for Python 3.6.15 (ecg-features directory)
```bash
python3.6 -m venv venv_3.6.15
source venv_3.6.15/bin/activate

```

## Installing Dependencies for Python 3.6.15 (ecg-features directory)
With the virtual environment active, use the package manager `pip` to install the project dependencies from the requirements.txt file:

_Note that if the following command fails and suggests updating pip to a newer version, run the following command :_ `pip install --upgrade pip`

Creating a Virtual Environment for Python 3.10.12 (Project Root)
```bash
pip install -r ecg-features/requirements.txt
```

# Usage
You can now open a `.ipynb` file with Jupyter Notebook and run it with one of the newly created virtual environment.
> :warning: Note that some notebook cells can take a long time to execute.

# Author
- Enzo Allemano, [GitHub profil](https://github.com/AllemanoEn)
