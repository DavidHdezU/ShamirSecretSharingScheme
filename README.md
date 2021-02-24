# Shamir Secret Share Scheme
[![Generic badge](https://img.shields.io/badge/version-3.09.10-<COLOR>.svg)](https://shields.io/)
[![Open Source Love png1](https://badges.frapsoft.com/os/v1/open-source.png?v=103)](https://github.com/ellerbrock/open-source-badges/)
[![Generic badge](https://img.shields.io/badge/contributors-2-blue)](https://shields.io/)  
[![forthebadge made-with-python](https://forthebadge.com/images/badges/made-with-python.svg)](https://www.python.org/)  	

# About
An implementation of the Shamir Secrete Share Scheme

# How to start
It is necessary to mention that the program is written in Python, under versions greater than or equal to Python 3.6, so it is advisable to update your computer to the most recent Python version, otherwise some failures could occur, and in the same way We recommend running on computers with GNU LINUX Operating System in any of its versions.
It is also necessary to install some extra libraries.

## Requerimients
* Check to use a version higher than Python3.6:
```
python --version
```
> `Python 3.6 +` is adviced

  Note, on some Linux distros, you will run it like:
  ```
  python3 --version
  ```


* You can check if you have PyPI installed as well as Python
  Available in the following article
  [PyPI] (https://www.tecmint.com/install-pip-in-linux/) up.

* Have installed pip "Pip Installs Packages" to install the necessary libraries

## Installation

* First of all you must install all the libraries that are needed for the program to run, for this just run the following command


```
pip install -r requirements.txt
```

# Use
* To check that everything is in order we will run the unit tests, to run them execute the following command
```
bash test.sh
```
In case the script crashes, you can use:
```
cd src/
python -m pytest
python -m pytest -v
```

* The program works in 2 ways, to encrypt and to decrypt files.
* This program implements the Shamir Secrete Share Scheme, so we need to generate a polynomial of degree k-1 and n evaluations of the polynomial

* To encrypt a file you must execute the following command
```
python3 src/main.py c <archivo> <n> <k>
```
* n [INTEGER] are the number of evaluations that will be made and later distributed
* k [INT] are the minimum number of evaluations to decrypt the file
```
n >= k > 1
```
* After having encrypted the file, there will be 2 new files in the folder "exit_files/" that will have the names:
```
archivo.frg 
```
y
```
archivo.aes
```
* The first file is a file where the n evaluations were saved, to later be distributed
* The second file is the encrypted file


* Now to decrypt a file the following command must be executed
```
python3 src/main.py d archivo.frg archivo.aes
```
* file.frg does not necessarily have to be the previously generated file, it may be another file that follows the same nomenclature as the originally generated .frg file, but in order to properly describe the.aes ​​file, at least k evaluations are required

* file.aes ​​is the file that was generated when the original file was encrypted

* If the file was correctly decrypted, the original file should appear again with its original content, if not, it is because less than k evaluations were evaluated or because the evaluations were not correct.

## Generate Documentation
* To generate the documentation about the project, the following command must be run
```
bash python-docs.sh
```
* The documentation is visible in
```
/docs
```

In case the script fails you can use
```
mkdir docs
pydoctor --make-html --html-output=docs/ src/main.py src/Controller/*.py src/Vista/*.py
```

### Important note
If you want to delete or add key lines to the .frg file, you must enter key per line, that is, in the form
```
QQQQQQQQQQQQQQQQQQQQQQQ,XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX
WWWWWWWWWWWWWWWWWWWWWWW,MMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMMM
SSSSSSSSSSSSSSSSSSSSSSS,DDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDDD
```
otherwise, the decryption process will not be correct or valuable data could be lost

--------Wrong way-----------
```
QQQQQQQQQQQQQQQQQQQQQ,XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX WWWWWWWWWWWWWWWWWWWWWWWWWWWWWW,MMMMMMMMMMMMMMMMMMMMMMMMMMMMMM 
```
Or similar



# Developed by:
#### David Hernández Urióstegui & Ian Israel García Vázquez

[<img src="https://img.shields.io/badge/gmail-D14836?&style=for-the-badge&logo=gmail&logoColor=white"/>](https://mail.google.com/mail/?view=cm&source=mailto&to=iangarcia@ciencias.unam.mx)
[<img src="https://img.shields.io/badge/gmail-D14836?&style=for-the-badge&logo=gmail&logoColor=white"/>](https://mail.google.com/mail/?view=cm&source=mailto&to=Dhdezu@ciencias.unam.mx)





---
![forthebadge biult-with-love](https://forthebadge.com/images/badges/built-with-love.svg) 
[![forthebadge powered-by-electricity](https://forthebadge.com/images/badges/powered-by-electricity.svg)](http://ForTheBadge.com)  
