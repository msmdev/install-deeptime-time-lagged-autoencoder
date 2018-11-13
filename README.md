# deeptime time-lagged autoencoder installation instructions
Instructions to install the time-lagged autoencoder (tae) package (https://github.com/msmdev/deeptime/tree/master/time-lagged-autoencoder) from deeptime to learn features (using pytorch) of complex molecular systems in a dimension-reduced latent space that can be used to build a Markov state model.

After following this instructions you will have:

1. GPU enabled pytorch.
2. The time-lagged autoencoder package from deeptime.
3. PyEMMA (https://github.com/markovmodel/PyEMMA) and mdshare.

```bash
# clone deeptime repository into some folder
cd 'your-folder'
git clone https://github.com/markovmodel/deeptime.git

# create conda env
conda create -n torch python=3.6

# activate the created environment
conda activate torch

# install numpy
pip install numpy

# install torch (cuda 9)
conda install pytorch torchvision cuda90 -c pytorch

# test gpu install
python -c 'import torch; print(torch.rand(2,3).cuda())'

# install time-lagged autoencoder (tae) package of deeptime 
cd deeptime/time-lagged-autoencoder
python setup.py test
python setup.py install

# to run the included benchmarks, you also need to install the packages pyemma and mdshare
conda install pyemma -c conda-forge
conda install mdshare -c conda-forge

# since the tae example is a jupyter notebook, the jupyter package is needed to run them
conda install jupyter
```
