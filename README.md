[![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg)](LICENSE)

# Project #

This code is based on the paper __A Robust Indoor Scene Recognition Method based on Sparse Representation__ presented on the __22nd Iberoamerican Congress on Pattern Recognition__ (CIARP 2017). The goal of this software is to build a robust representation of scene images, that conveys global as well as local information, for the task of scene recognition. We  built  an  over-complete dictionary  whose  base  vectors  are feature vectors extracted from fragments of a scene, and the final representation of an image is a linear combination of the visual features of objects’ fragments. 

For more information, please access the [project page](http://www.verlab.dcc.ufmg.br/scene-understanding/).


## Contact ##

### Authors ###

* Guilherme Nascimento - MSc student - UFMG - guigonasc@gmail.com
* Camila Laranjeira - MSc student - UFMG - mila.laranjeira@gmail.com
* Vinicius Braz - Undergraduate Student - UFMG - viniciusbraz30@gmail.com
* Anisio Lacerda - Co-Avisor - CEFET-MG - anisiom@gmail.com
* Erickson R. Nascimento - Advisor - UFMG - erickson@dcc.ufmg.br


### Institution ###

Federal University of Minas Gerais (UFMG)  
Computer Science Department  
Belo Horizonte - Minas Gerais -Brazil 

### Laboratory ###

__VeRLab:__ Laboratory of Computer Vison and Robotics   
http://www.verlab.dcc.ufmg.br

## Program ##

### Dependencies ###

* [OpenCV 3.2.0](http://docs.opencv.org/3.3.0/)
* [Caffe 1.0.0](http://caffe.berkeleyvision.org/)
* [Spams 2.5](http://spams-devel.gforge.inria.fr/downloads.html)
* [CUDA 8.0 (GPU version only)](https://developer.nvidia.com/cuda-toolkit)
* [cuDNN v5 (GPU version only)](https://developer.nvidia.com/cudnn)
* [Numpy](https://docs.scipy.org/doc/numpy-1.13.0/reference/), [Scikit Image](http://scikit-image.org/docs/dev/), [Scikit Learn](http://scikit-learn.org/stable/documentation.html), [Scipy](https://docs.scipy.org/doc/scipy/reference/), [Pickle](https://docs.python.org/2/library/pickle.html)


### Usage ###
1. **Generate Train/Test split:**   
Example provided in folder CFG_FILES (fold4.cfg). The source code also contains the script kfold.py if you wish to generate new splits.

2. **Edit Config files:**   
Examples provided in folder CFG_FILES. Config files should be stored in the same path as the on provided in --folder parameter (as seen later). The code requires two files:
* IMNET.cfg: referring to VGG16 trained on ImageNet 
* PLACES.cfg: referring to VGG16 trained on Places205   

3. **Execution:**   
Execute run_test.py using the following parameters:

* -f, --folder: Path to folder you wish to save the outputs of the code;  
* -o, --output: Path to file you wish to save the output statistics (e.g. accuracy); 
* -k, --fold: Index of Train/Test split (referring to the parameter [folds] in the Config files);
* -m, --mode: Operation mode ('train' or 'test'); 
* -d, --ns1: Size of dictionary for scale 1; 
* -e, --ns2: Size of dictionary for scale 2; 
* -l, --lambda: Sparsity (e.g. 0.1 to activate at most 10% of the dictionary);
* -t, --method: Minimization Method ('OMP', 'SOMP' or 'LASSO');
* -j, --dl: Sparsity controller for dictionary learning.


Example of Usage:
```bash
python run_test.py -f /root/output -o /root/output/result_ -k 4 -m train -d 603 -e 3283 -l 0.1 -t OMP -j 0.03 
```

## Citation ##

If you are using it for academic purposes, please cite: 

G. Nascimento, C. Laranjeira, V. Braz, A. Lacerda, E. R. Nascimento, __A Robust Indoor Scene Recognition Method based on Sparse Representation__, in: 22nd Iberoamerican Congress on Pattern Recognition, CIARP, Springer International Publishing, Valparaiso, CL, 2017. To appear. 


### Bibtex entry ###

> @inproceedings{Nascimento2017,  
> Title = {A Robust Indoor Scene Recognition Method based on Sparse Representation},  
> Author = {Nascimento, Guilherme and Laranjeira, Camila and Braz, Vinicius and Lacerda, Anisio and Nascimento, Erickson Rangel},  
> booktitle = {22nd Iberoamerican Congress on Pattern Recognition. CIARP},  
> Publisher = {Springer International Publishing},  
> Year = {2017},  
> Address = {Valparaiso, CL},  
> note = {To appear},  
> }  

###### Enjoy it. ######
