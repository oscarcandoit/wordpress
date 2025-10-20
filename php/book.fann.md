---
url: https://www.php.net/manual/en/book.fann.php
scraped_at: 2025-10-20T02:47:01.663Z
---

Change language:EnglishGermanSpanishFrenchItalianJapaneseBrazilian PortugueseRussianTurkishUkrainianChinese (Simplified)Other

# FANN (Fast Artificial Neural Network) [¶](https://www.php.net/manual/en/book.fann.php\#book.fann)

- [Introduction](https://www.php.net/manual/en/intro.fann.php)
- [Installing/Configuring](https://www.php.net/manual/en/fann.setup.php)
  - [Requirements](https://www.php.net/manual/en/fann.requirements.php)
  - [Installation](https://www.php.net/manual/en/fann.installation.php)
  - [Resource Types](https://www.php.net/manual/en/fann.resources.php)
- [Predefined Constants](https://www.php.net/manual/en/fann.constants.php)
- [Examples](https://www.php.net/manual/en/fann.examples.php)
  - [XOR training](https://www.php.net/manual/en/fann.examples-1.php)
- [Fann Functions](https://www.php.net/manual/en/ref.fann.php)
  - [fann\_cascadetrain\_on\_data](https://www.php.net/manual/en/function.fann-cascadetrain-on-data.php) — Trains on an entire dataset, for a period of time using the Cascade2 training algorithm
  - [fann\_cascadetrain\_on\_file](https://www.php.net/manual/en/function.fann-cascadetrain-on-file.php) — Trains on an entire dataset read from file, for a period of time using the Cascade2 training algorithm
  - [fann\_clear\_scaling\_params](https://www.php.net/manual/en/function.fann-clear-scaling-params.php) — Clears scaling parameters
  - [fann\_copy](https://www.php.net/manual/en/function.fann-copy.php) — Creates a copy of a fann structure
  - [fann\_create\_from\_file](https://www.php.net/manual/en/function.fann-create-from-file.php) — Constructs a backpropagation neural network from a configuration file
  - [fann\_create\_shortcut](https://www.php.net/manual/en/function.fann-create-shortcut.php) — Creates a standard backpropagation neural network which is not fully connectected and has shortcut connections
  - [fann\_create\_shortcut\_array](https://www.php.net/manual/en/function.fann-create-shortcut-array.php) — Creates a standard backpropagation neural network which is not fully connectected and has shortcut connections
  - [fann\_create\_sparse](https://www.php.net/manual/en/function.fann-create-sparse.php) — Creates a standard backpropagation neural network, which is not fully connected
  - [fann\_create\_sparse\_array](https://www.php.net/manual/en/function.fann-create-sparse-array.php) — Creates a standard backpropagation neural network, which is not fully connected using an array of layer sizes
  - [fann\_create\_standard](https://www.php.net/manual/en/function.fann-create-standard.php) — Creates a standard fully connected backpropagation neural network
  - [fann\_create\_standard\_array](https://www.php.net/manual/en/function.fann-create-standard-array.php) — Creates a standard fully connected backpropagation neural network using an array of layer sizes
  - [fann\_create\_train](https://www.php.net/manual/en/function.fann-create-train.php) — Creates an empty training data struct
  - [fann\_create\_train\_from\_callback](https://www.php.net/manual/en/function.fann-create-train-from-callback.php) — Creates the training data struct from a user supplied function
  - [fann\_descale\_input](https://www.php.net/manual/en/function.fann-descale-input.php) — Scale data in input vector after get it from ann based on previously calculated parameters
  - [fann\_descale\_output](https://www.php.net/manual/en/function.fann-descale-output.php) — Scale data in output vector after get it from ann based on previously calculated parameters
  - [fann\_descale\_train](https://www.php.net/manual/en/function.fann-descale-train.php) — Descale input and output data based on previously calculated parameters
  - [fann\_destroy](https://www.php.net/manual/en/function.fann-destroy.php) — Destroys the entire network and properly freeing all the associated memory
  - [fann\_destroy\_train](https://www.php.net/manual/en/function.fann-destroy-train.php) — Destructs the training data
  - [fann\_duplicate\_train\_data](https://www.php.net/manual/en/function.fann-duplicate-train-data.php) — Returns an exact copy of a fann train data
  - [fann\_get\_activation\_function](https://www.php.net/manual/en/function.fann-get-activation-function.php) — Returns the activation function
  - [fann\_get\_activation\_steepness](https://www.php.net/manual/en/function.fann-get-activation-steepness.php) — Returns the activation steepness for supplied neuron and layer number
  - [fann\_get\_bias\_array](https://www.php.net/manual/en/function.fann-get-bias-array.php) — Get the number of bias in each layer in the network
  - [fann\_get\_bit\_fail](https://www.php.net/manual/en/function.fann-get-bit-fail.php) — The number of fail bits
  - [fann\_get\_bit\_fail\_limit](https://www.php.net/manual/en/function.fann-get-bit-fail-limit.php) — Returns the bit fail limit used during training
  - [fann\_get\_cascade\_activation\_functions](https://www.php.net/manual/en/function.fann-get-cascade-activation-functions.php) — Returns the cascade activation functions
  - [fann\_get\_cascade\_activation\_functions\_count](https://www.php.net/manual/en/function.fann-get-cascade-activation-functions-count.php) — Returns the number of cascade activation functions
  - [fann\_get\_cascade\_activation\_steepnesses](https://www.php.net/manual/en/function.fann-get-cascade-activation-steepnesses.php) — Returns the cascade activation steepnesses
  - [fann\_get\_cascade\_activation\_steepnesses\_count](https://www.php.net/manual/en/function.fann-get-cascade-activation-steepnesses-count.php) — The number of activation steepnesses
  - [fann\_get\_cascade\_candidate\_change\_fraction](https://www.php.net/manual/en/function.fann-get-cascade-candidate-change-fraction.php) — Returns the cascade candidate change fraction
  - [fann\_get\_cascade\_candidate\_limit](https://www.php.net/manual/en/function.fann-get-cascade-candidate-limit.php) — Return the candidate limit
  - [fann\_get\_cascade\_candidate\_stagnation\_epochs](https://www.php.net/manual/en/function.fann-get-cascade-candidate-stagnation-epochs.php) — Returns the number of cascade candidate stagnation epochs
  - [fann\_get\_cascade\_max\_cand\_epochs](https://www.php.net/manual/en/function.fann-get-cascade-max-cand-epochs.php) — Returns the maximum candidate epochs
  - [fann\_get\_cascade\_max\_out\_epochs](https://www.php.net/manual/en/function.fann-get-cascade-max-out-epochs.php) — Returns the maximum out epochs
  - [fann\_get\_cascade\_min\_cand\_epochs](https://www.php.net/manual/en/function.fann-get-cascade-min-cand-epochs.php) — Returns the minimum candidate epochs
  - [fann\_get\_cascade\_min\_out\_epochs](https://www.php.net/manual/en/function.fann-get-cascade-min-out-epochs.php) — Returns the minimum out epochs
  - [fann\_get\_cascade\_num\_candidate\_groups](https://www.php.net/manual/en/function.fann-get-cascade-num-candidate-groups.php) — Returns the number of candidate groups
  - [fann\_get\_cascade\_num\_candidates](https://www.php.net/manual/en/function.fann-get-cascade-num-candidates.php) — Returns the number of candidates used during training
  - [fann\_get\_cascade\_output\_change\_fraction](https://www.php.net/manual/en/function.fann-get-cascade-output-change-fraction.php) — Returns the cascade output change fraction
  - [fann\_get\_cascade\_output\_stagnation\_epochs](https://www.php.net/manual/en/function.fann-get-cascade-output-stagnation-epochs.php) — Returns the number of cascade output stagnation epochs
  - [fann\_get\_cascade\_weight\_multiplier](https://www.php.net/manual/en/function.fann-get-cascade-weight-multiplier.php) — Returns the weight multiplier
  - [fann\_get\_connection\_array](https://www.php.net/manual/en/function.fann-get-connection-array.php) — Get connections in the network
  - [fann\_get\_connection\_rate](https://www.php.net/manual/en/function.fann-get-connection-rate.php) — Get the connection rate used when the network was created
  - [fann\_get\_errno](https://www.php.net/manual/en/function.fann-get-errno.php) — Returns the last error number
  - [fann\_get\_errstr](https://www.php.net/manual/en/function.fann-get-errstr.php) — Returns the last errstr
  - [fann\_get\_layer\_array](https://www.php.net/manual/en/function.fann-get-layer-array.php) — Get the number of neurons in each layer in the network
  - [fann\_get\_learning\_momentum](https://www.php.net/manual/en/function.fann-get-learning-momentum.php) — Returns the learning momentum
  - [fann\_get\_learning\_rate](https://www.php.net/manual/en/function.fann-get-learning-rate.php) — Returns the learning rate
  - [fann\_get\_MSE](https://www.php.net/manual/en/function.fann-get-mse.php) — Reads the mean square error from the network
  - [fann\_get\_network\_type](https://www.php.net/manual/en/function.fann-get-network-type.php) — Get the type of neural network it was created as
  - [fann\_get\_num\_input](https://www.php.net/manual/en/function.fann-get-num-input.php) — Get the number of input neurons
  - [fann\_get\_num\_layers](https://www.php.net/manual/en/function.fann-get-num-layers.php) — Get the number of layers in the neural network
  - [fann\_get\_num\_output](https://www.php.net/manual/en/function.fann-get-num-output.php) — Get the number of output neurons
  - [fann\_get\_quickprop\_decay](https://www.php.net/manual/en/function.fann-get-quickprop-decay.php) — Returns the decay which is a factor that weights should decrease in each iteration during quickprop training
  - [fann\_get\_quickprop\_mu](https://www.php.net/manual/en/function.fann-get-quickprop-mu.php) — Returns the mu factor
  - [fann\_get\_rprop\_decrease\_factor](https://www.php.net/manual/en/function.fann-get-rprop-decrease-factor.php) — Returns the increase factor used during RPROP training
  - [fann\_get\_rprop\_delta\_max](https://www.php.net/manual/en/function.fann-get-rprop-delta-max.php) — Returns the maximum step-size
  - [fann\_get\_rprop\_delta\_min](https://www.php.net/manual/en/function.fann-get-rprop-delta-min.php) — Returns the minimum step-size
  - [fann\_get\_rprop\_delta\_zero](https://www.php.net/manual/en/function.fann-get-rprop-delta-zero.php) — Returns the initial step-size
  - [fann\_get\_rprop\_increase\_factor](https://www.php.net/manual/en/function.fann-get-rprop-increase-factor.php) — Returns the increase factor used during RPROP training
  - [fann\_get\_sarprop\_step\_error\_shift](https://www.php.net/manual/en/function.fann-get-sarprop-step-error-shift.php) — Returns the sarprop step error shift
  - [fann\_get\_sarprop\_step\_error\_threshold\_factor](https://www.php.net/manual/en/function.fann-get-sarprop-step-error-threshold-factor.php) — Returns the sarprop step error threshold factor
  - [fann\_get\_sarprop\_temperature](https://www.php.net/manual/en/function.fann-get-sarprop-temperature.php) — Returns the sarprop temperature
  - [fann\_get\_sarprop\_weight\_decay\_shift](https://www.php.net/manual/en/function.fann-get-sarprop-weight-decay-shift.php) — Returns the sarprop weight decay shift
  - [fann\_get\_total\_connections](https://www.php.net/manual/en/function.fann-get-total-connections.php) — Get the total number of connections in the entire network
  - [fann\_get\_total\_neurons](https://www.php.net/manual/en/function.fann-get-total-neurons.php) — Get the total number of neurons in the entire network
  - [fann\_get\_train\_error\_function](https://www.php.net/manual/en/function.fann-get-train-error-function.php) — Returns the error function used during training
  - [fann\_get\_train\_stop\_function](https://www.php.net/manual/en/function.fann-get-train-stop-function.php) — Returns the stop function used during training
  - [fann\_get\_training\_algorithm](https://www.php.net/manual/en/function.fann-get-training-algorithm.php) — Returns the training algorithm
  - [fann\_init\_weights](https://www.php.net/manual/en/function.fann-init-weights.php) — Initialize the weights using Widrow + Nguyen’s algorithm
  - [fann\_length\_train\_data](https://www.php.net/manual/en/function.fann-length-train-data.php) — Returns the number of training patterns in the train data
  - [fann\_merge\_train\_data](https://www.php.net/manual/en/function.fann-merge-train-data.php) — Merges the train data
  - [fann\_num\_input\_train\_data](https://www.php.net/manual/en/function.fann-num-input-train-data.php) — Returns the number of inputs in each of the training patterns in the train data
  - [fann\_num\_output\_train\_data](https://www.php.net/manual/en/function.fann-num-output-train-data.php) — Returns the number of outputs in each of the training patterns in the train data
  - [fann\_print\_error](https://www.php.net/manual/en/function.fann-print-error.php) — Prints the error string
  - [fann\_randomize\_weights](https://www.php.net/manual/en/function.fann-randomize-weights.php) — Give each connection a random weight between min\_weight and max\_weight
  - [fann\_read\_train\_from\_file](https://www.php.net/manual/en/function.fann-read-train-from-file.php) — Reads a file that stores training data
  - [fann\_reset\_errno](https://www.php.net/manual/en/function.fann-reset-errno.php) — Resets the last error number
  - [fann\_reset\_errstr](https://www.php.net/manual/en/function.fann-reset-errstr.php) — Resets the last error string
  - [fann\_reset\_MSE](https://www.php.net/manual/en/function.fann-reset-mse.php) — Resets the mean square error from the network
  - [fann\_run](https://www.php.net/manual/en/function.fann-run.php) — Will run input through the neural network
  - [fann\_save](https://www.php.net/manual/en/function.fann-save.php) — Saves the entire network to a configuration file
  - [fann\_save\_train](https://www.php.net/manual/en/function.fann-save-train.php) — Save the training structure to a file
  - [fann\_scale\_input](https://www.php.net/manual/en/function.fann-scale-input.php) — Scale data in input vector before feed it to ann based on previously calculated parameters
  - [fann\_scale\_input\_train\_data](https://www.php.net/manual/en/function.fann-scale-input-train-data.php) — Scales the inputs in the training data to the specified range
  - [fann\_scale\_output](https://www.php.net/manual/en/function.fann-scale-output.php) — Scale data in output vector before feed it to ann based on previously calculated parameters
  - [fann\_scale\_output\_train\_data](https://www.php.net/manual/en/function.fann-scale-output-train-data.php) — Scales the outputs in the training data to the specified range
  - [fann\_scale\_train](https://www.php.net/manual/en/function.fann-scale-train.php) — Scale input and output data based on previously calculated parameters
  - [fann\_scale\_train\_data](https://www.php.net/manual/en/function.fann-scale-train-data.php) — Scales the inputs and outputs in the training data to the specified range
  - [fann\_set\_activation\_function](https://www.php.net/manual/en/function.fann-set-activation-function.php) — Sets the activation function for supplied neuron and layer
  - [fann\_set\_activation\_function\_hidden](https://www.php.net/manual/en/function.fann-set-activation-function-hidden.php) — Sets the activation function for all of the hidden layers
  - [fann\_set\_activation\_function\_layer](https://www.php.net/manual/en/function.fann-set-activation-function-layer.php) — Sets the activation function for all the neurons in the supplied layer
  - [fann\_set\_activation\_function\_output](https://www.php.net/manual/en/function.fann-set-activation-function-output.php) — Sets the activation function for the output layer
  - [fann\_set\_activation\_steepness](https://www.php.net/manual/en/function.fann-set-activation-steepness.php) — Sets the activation steepness for supplied neuron and layer number
  - [fann\_set\_activation\_steepness\_hidden](https://www.php.net/manual/en/function.fann-set-activation-steepness-hidden.php) — Sets the steepness of the activation steepness for all neurons in the all hidden layers
  - [fann\_set\_activation\_steepness\_layer](https://www.php.net/manual/en/function.fann-set-activation-steepness-layer.php) — Sets the activation steepness for all of the neurons in the supplied layer number
  - [fann\_set\_activation\_steepness\_output](https://www.php.net/manual/en/function.fann-set-activation-steepness-output.php) — Sets the steepness of the activation steepness in the output layer
  - [fann\_set\_bit\_fail\_limit](https://www.php.net/manual/en/function.fann-set-bit-fail-limit.php) — Set the bit fail limit used during training
  - [fann\_set\_callback](https://www.php.net/manual/en/function.fann-set-callback.php) — Sets the callback function for use during training
  - [fann\_set\_cascade\_activation\_functions](https://www.php.net/manual/en/function.fann-set-cascade-activation-functions.php) — Sets the array of cascade candidate activation functions
  - [fann\_set\_cascade\_activation\_steepnesses](https://www.php.net/manual/en/function.fann-set-cascade-activation-steepnesses.php) — Sets the array of cascade candidate activation steepnesses
  - [fann\_set\_cascade\_candidate\_change\_fraction](https://www.php.net/manual/en/function.fann-set-cascade-candidate-change-fraction.php) — Sets the cascade candidate change fraction
  - [fann\_set\_cascade\_candidate\_limit](https://www.php.net/manual/en/function.fann-set-cascade-candidate-limit.php) — Sets the candidate limit
  - [fann\_set\_cascade\_candidate\_stagnation\_epochs](https://www.php.net/manual/en/function.fann-set-cascade-candidate-stagnation-epochs.php) — Sets the number of cascade candidate stagnation epochs
  - [fann\_set\_cascade\_max\_cand\_epochs](https://www.php.net/manual/en/function.fann-set-cascade-max-cand-epochs.php) — Sets the max candidate epochs
  - [fann\_set\_cascade\_max\_out\_epochs](https://www.php.net/manual/en/function.fann-set-cascade-max-out-epochs.php) — Sets the maximum out epochs
  - [fann\_set\_cascade\_min\_cand\_epochs](https://www.php.net/manual/en/function.fann-set-cascade-min-cand-epochs.php) — Sets the min candidate epochs
  - [fann\_set\_cascade\_min\_out\_epochs](https://www.php.net/manual/en/function.fann-set-cascade-min-out-epochs.php) — Sets the minimum out epochs
  - [fann\_set\_cascade\_num\_candidate\_groups](https://www.php.net/manual/en/function.fann-set-cascade-num-candidate-groups.php) — Sets the number of candidate groups
  - [fann\_set\_cascade\_output\_change\_fraction](https://www.php.net/manual/en/function.fann-set-cascade-output-change-fraction.php) — Sets the cascade output change fraction
  - [fann\_set\_cascade\_output\_stagnation\_epochs](https://www.php.net/manual/en/function.fann-set-cascade-output-stagnation-epochs.php) — Sets the number of cascade output stagnation epochs
  - [fann\_set\_cascade\_weight\_multiplier](https://www.php.net/manual/en/function.fann-set-cascade-weight-multiplier.php) — Sets the weight multiplier
  - [fann\_set\_error\_log](https://www.php.net/manual/en/function.fann-set-error-log.php) — Sets where the errors are logged to
  - [fann\_set\_input\_scaling\_params](https://www.php.net/manual/en/function.fann-set-input-scaling-params.php) — Calculate input scaling parameters for future use based on training data
  - [fann\_set\_learning\_momentum](https://www.php.net/manual/en/function.fann-set-learning-momentum.php) — Sets the learning momentum
  - [fann\_set\_learning\_rate](https://www.php.net/manual/en/function.fann-set-learning-rate.php) — Sets the learning rate
  - [fann\_set\_output\_scaling\_params](https://www.php.net/manual/en/function.fann-set-output-scaling-params.php) — Calculate output scaling parameters for future use based on training data
  - [fann\_set\_quickprop\_decay](https://www.php.net/manual/en/function.fann-set-quickprop-decay.php) — Sets the quickprop decay factor
  - [fann\_set\_quickprop\_mu](https://www.php.net/manual/en/function.fann-set-quickprop-mu.php) — Sets the quickprop mu factor
  - [fann\_set\_rprop\_decrease\_factor](https://www.php.net/manual/en/function.fann-set-rprop-decrease-factor.php) — Sets the decrease factor used during RPROP training
  - [fann\_set\_rprop\_delta\_max](https://www.php.net/manual/en/function.fann-set-rprop-delta-max.php) — Sets the maximum step-size
  - [fann\_set\_rprop\_delta\_min](https://www.php.net/manual/en/function.fann-set-rprop-delta-min.php) — Sets the minimum step-size
  - [fann\_set\_rprop\_delta\_zero](https://www.php.net/manual/en/function.fann-set-rprop-delta-zero.php) — Sets the initial step-size
  - [fann\_set\_rprop\_increase\_factor](https://www.php.net/manual/en/function.fann-set-rprop-increase-factor.php) — Sets the increase factor used during RPROP training
  - [fann\_set\_sarprop\_step\_error\_shift](https://www.php.net/manual/en/function.fann-set-sarprop-step-error-shift.php) — Sets the sarprop step error shift
  - [fann\_set\_sarprop\_step\_error\_threshold\_factor](https://www.php.net/manual/en/function.fann-set-sarprop-step-error-threshold-factor.php) — Sets the sarprop step error threshold factor
  - [fann\_set\_sarprop\_temperature](https://www.php.net/manual/en/function.fann-set-sarprop-temperature.php) — Sets the sarprop temperature
  - [fann\_set\_sarprop\_weight\_decay\_shift](https://www.php.net/manual/en/function.fann-set-sarprop-weight-decay-shift.php) — Sets the sarprop weight decay shift
  - [fann\_set\_scaling\_params](https://www.php.net/manual/en/function.fann-set-scaling-params.php) — Calculate input and output scaling parameters for future use based on training data
  - [fann\_set\_train\_error\_function](https://www.php.net/manual/en/function.fann-set-train-error-function.php) — Sets the error function used during training
  - [fann\_set\_train\_stop\_function](https://www.php.net/manual/en/function.fann-set-train-stop-function.php) — Sets the stop function used during training
  - [fann\_set\_training\_algorithm](https://www.php.net/manual/en/function.fann-set-training-algorithm.php) — Sets the training algorithm
  - [fann\_set\_weight](https://www.php.net/manual/en/function.fann-set-weight.php) — Set a connection in the network
  - [fann\_set\_weight\_array](https://www.php.net/manual/en/function.fann-set-weight-array.php) — Set connections in the network
  - [fann\_shuffle\_train\_data](https://www.php.net/manual/en/function.fann-shuffle-train-data.php) — Shuffles training data, randomizing the order
  - [fann\_subset\_train\_data](https://www.php.net/manual/en/function.fann-subset-train-data.php) — Returns an copy of a subset of the train data
  - [fann\_test](https://www.php.net/manual/en/function.fann-test.php) — Test with a set of inputs, and a set of desired outputs
  - [fann\_test\_data](https://www.php.net/manual/en/function.fann-test-data.php) — Test a set of training data and calculates the MSE for the training data
  - [fann\_train](https://www.php.net/manual/en/function.fann-train.php) — Train one iteration with a set of inputs, and a set of desired outputs
  - [fann\_train\_epoch](https://www.php.net/manual/en/function.fann-train-epoch.php) — Train one epoch with a set of training data
  - [fann\_train\_on\_data](https://www.php.net/manual/en/function.fann-train-on-data.php) — Trains on an entire dataset for a period of time
  - [fann\_train\_on\_file](https://www.php.net/manual/en/function.fann-train-on-file.php) — Trains on an entire dataset, which is read from file, for a period of time
- [FANNConnection](https://www.php.net/manual/en/class.fannconnection.php) — The FANNConnection class
  - [FANNConnection::\_\_construct](https://www.php.net/manual/en/fannconnection.construct.php) — The connection constructor
  - [FANNConnection::getFromNeuron](https://www.php.net/manual/en/fannconnection.getfromneuron.php) — Returns the postions of starting neuron
  - [FANNConnection::getToNeuron](https://www.php.net/manual/en/fannconnection.gettoneuron.php) — Returns the postions of terminating neuron
  - [FANNConnection::getWeight](https://www.php.net/manual/en/fannconnection.getweight.php) — Returns the connection weight
  - [FANNConnection::setWeight](https://www.php.net/manual/en/fannconnection.setweight.php) — Sets the connections weight

### Found A Problem?

[Learn How To Improve This Page](https://github.com/php/doc-base/blob/master/README.md "This will take you to our contribution guidelines on GitHub")
•
[Submit a Pull Request](https://github.com/php/doc-en/blob/master/reference/fann/book.xml)
•
[Report a Bug](https://github.com/php/doc-en/issues/new?body=From%20manual%20page:%20https:%2F%2Fphp.net%2Fbook.fann%0A%0A---)

[＋add a note](https://www.php.net/manual/add-note.php?sect=book.fann&repo=en&redirect=https://www.php.net/manual/en/book.fann.php)

### User Contributed Notes

There are no user contributed notes for this page.

![To Top](https://www.php.net/images/to-top@2x.png)

`↑` and `↓` to navigate •
`Enter` to select •
`Esc` to close


Press `Enter` without
selection to search using Google