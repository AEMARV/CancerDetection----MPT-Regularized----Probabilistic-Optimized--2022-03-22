# Cancer detection, MPT regularization, and probabilistic optimization

Opened 2022-03-22.

PyTorch experiments for pancreas segmentation and for maximum-probability training.

`run_panc.py` trains a 2D pancreas segmentation model on the NIH pancreas set. The active loss is a balanced segmentation loss. The runner also names Mayo data and an energy-based training phase.

`runMPT.py` trains the same family of objectives on CIFAR-10, CIFAR-100, and MNIST, across ResNet, DenseNet, VGG, DLA, and DPN models. The objectives are conditional cross-entropy, joint cross-entropy, and a joint probabilistic loss in which each sample weights the gradient by the probability of the label.

`ProbabilisticOptimization` (`mptopt.py`, `DigitalGraph.py`) filters the objective statistically and searches for a wide mode, so the objective does not have to be smooth. `GRS` is the generalized rejection sampler.

The maximum-probability account treats the trained model as an event in a probability space. Regularization is the probability of that event.
