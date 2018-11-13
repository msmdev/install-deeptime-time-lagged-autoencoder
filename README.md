# deeptime time-lagged autoencoder installation instructions
Instructions to install the time-lagged autoencoder (tae) package (https://github.com/msmdev/deeptime/tree/master/time-lagged-autoencoder) from deeptime to learn features (using pytorch) of complex molecular systems in a dimension-reduced latent space that can be used to build a Markov state model.

After following this instructions you will have:

1. GPU enabled pytorch (assuming you have a CUDA capable GPU and the nvidia drivers and CUDA installed).
2. The time-lagged autoencoder package from deeptime.
3. PyEMMA (https://github.com/markovmodel/PyEMMA) and mdshare.

```bash
# clone deeptime repository into some folder
cd 'your-folder'
git clone https://github.com/markovmodel/deeptime.git

# create conda env
# install numpy 1.13 and pyemma 2.4 (since newer versions to date don't harmonize with deeptime)
# to run the included benchmarks, you also need to install the packages pyemma and mdshare
# since the tae example is a jupyter notebook, the jupyter package is needed to run them
conda create -n tae python=3.6 numpy=1.13.3 pyemma=2.4 jupyter mdshare -c conda-forge

# activate the created environment
source activate tae

# install torch (cuda 9)
conda install pytorch torchvision cuda90 -c pytorch

# test gpu install
python -c 'import torch; print(torch.rand(2,3).cuda())'

# install time-lagged autoencoder (tae) package of deeptime 
cd deeptime/time-lagged-autoencoder
python setup.py test
python setup.py install
```
