# CNN_for_Ising_Model
Using a Convolutional neural network to predict 2D Ising model energies for 4 neighbours 

Introduction
The code includes an implementation of the Metropolis algorithm, which generates both the input data(Final state of run), and the training result, i.e.
the average energy. 

Methodology
The pseudocode for Metropolis algorithm is taken from Schroeder Introduction to stat Mech and thermodynamics. Avergages are calculated by summing over the observed energies during the run, and weighting the sum by the frequency with which they are observed. We divide by the sum of all frequencies, finally. 
Keras functions are used to implement the network. Most hyperparameters, alongside the loss function are chosen arbitrarily. It is a difficult skill to intuitively pick the correct hyperparameters and trial and error is too costly, time-wise. However, the activation function chose is soft-sign, purely because we want the network to preserve negatives. 

Some Notes About how to use the code and Improvements 
Due to inefficiencies at various stages, generating training data is very costly, both in terms of computation power and time. To train the network, I stuck to N=5 as the length of the square lattice and a total length of 10000 in the Metropolis run. I trained the network on a batchsize of 15, 100 times over. Unfortunately, the results aren't too promising. This maybe due to the fact that I haven't trained for long enough, or that the hyperparameters chosen are just incorrect. Finally, one better way to pass in the data, not implemented, is to use a multichannel input that passes in the state of the network at various stages during the run. 

