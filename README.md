# Pop3Net
A series of neural networks to predict primordial star formation and feedback in hydrodynamic simulations.  
This is the code base for the paper "Predicting Localized Primordial Star Forming Regions With Convolutional Neural Networks" 
by Wells & Norman, 2020 (in preparation).

These networks were trained using ```Enzo``` astrophysics simulations with primordial and enriched star 
formation.  The simulations self consistently track radiation from stellar sources, along with H$_2$ 
dissociating radiation background.  

The scripts to run network training are located in ```run_networks```.  Each stage of the prediction/feedback 
has its own unique run script--```run_classifier.py``` for stage 1 classification and ```run_segmentation.py``` for 
stage 2 segmentation.   Within ```run_networks```, you can also find example configuration files for running the training scripts ```*.conf```.

The configuration of the run is dictated by a configuration file, and is processed using the ConfigParser package.
Each network is implemented in ```network_modules```, for the most part, in unique scripts for unique architectures.
There, you can find the small_classifier architechtures, along with the Inception U-net used in the paper.

Within ```network_modules```, you can also find the helper utilities used to track training progress and state, along with other definitions
for loss functions used in the work. In ```testing```, all test scripts and their configurations are found.  The test/training data for this 
project is too large to be hosted; please contact the authors if you need this data.

Saved models are available in the ```checkpoints``` directory; you can see how to load these checkpoints by examining the running scripts in 
```run_networks```. 

Scripts for data preparation are in the ```data_generation``` directory, however they are unique to the data used in the paper--
other simulation codes or methods may have varying success trying to use them as-is.
