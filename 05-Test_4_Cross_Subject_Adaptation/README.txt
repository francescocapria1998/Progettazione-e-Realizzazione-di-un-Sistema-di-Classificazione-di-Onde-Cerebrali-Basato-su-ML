Due to the reduced performance observed in the previous test (with unseen subjects), an Adaptation phase is introduced, structured as follows:

- Pre-Training: the network is initialized with the weights obtained from the training on the 15 known subjects (instead of random initialization, as usually done);

- Adaptation: an additional training phase is performed using a small percentage of the new subject’s data, allowing the network to adapt its weights;

- Test: performance evaluation is carried out on the remaining subjects, considered individually.


Inside this folder, the following scripts are provided:

- Test 4_1: During the Adaptation phase, all network weights are frozen except for the last layer (the one with the softmax), whose weights are updated.
	Consequence: limited adaptation.

- Test 4_2: All network weights are initially frozen, and during the Adaptation phase the following layers are unfrozen:
	Dense “base” layer (256 units);
	Dense “residual” layer (256 units);
	Final Dense layer (softmax).
	Consequence: significantly more effective adaptation and improved cross-subject performance.