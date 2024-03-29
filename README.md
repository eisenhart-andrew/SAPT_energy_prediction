# SAPT_energy_prediction
## Prediction of SAPT energy components for randomly arranged water dimers
<img src="https://raw.github.com/eisenhart-andrew/SAPT_energy_prediction/main/images/toc_image.png" width="700" height="600">
# Abstract
This project showcases the ability of simple molecular representations, in theis case colombic matrix, to provide sufficient information for a multi-layer perceptron to predict segmented interaction energies of water dimers arranged in 3D space. This test case shows that predictions of symmetry adapted peturbation theory (SAPT) calculated inteaction energies with accuracies < 0.1 kcal/mol are possible.

# Methods
<img src="https://raw.github.com/eisenhart-andrew/SAPT_energy_prediction/main/images/diagram.png" width="600" height="800">

The dimer dataset was created by centering a water molecule in a 5x5x5 angstrom cubic box. A second water molecule was then randomly added to this box, Van der waal radii were used to avoid atomic overlap. 10k of these configurations were created in the GROMACS ".gro" format which were then converted into the molecular ".sdf" format, and stacked into a single input file (stored as dimer.sdf). The target values were generated by splicing the dimer coordinates into a template PSI4 input file and remotely running the SAPT(0) calculations. Target values were then harvested from the resulting output files and combined into a single "csv" file (stored as dimer.sdf.csv).
<img src="https://raw.github.com/eisenhart-andrew/SAPT_energy_prediction/main/images/Input_data.jpg" width="800" height="600">

The columbic matrices and modeling training were done using the deepchem machine learning architecture (https://github.com/deepchem/deepchem). Several featurizations and models were tested with the combination of colombic matrix featurization and Deep Tensor Neural Network proving among the most accurate and quickest to train using a simple 80/10/10 training/test/validation data split.   

# Results

<img src="https://raw.github.com/eisenhart-andrew/SAPT_energy_prediction/main/images/combined_accuracy_prediction_plot.jpg" width="800" height="600">



<img src="https://raw.github.com/eisenhart-andrew/SAPT_energy_prediction/main/images/MEA_measures_spectrum.jpg" width="700" height="700">
