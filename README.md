perceptron.py
=============

A simple perceptron neural network implementatoin. Read more [here.](http://en.wikipedia.org/wiki/Perceptron)

Example
-------

	import perceptron

	nand_set = {
	  (0,0): 1,
	  (0,1): 1,
	  (1,0): 1,
	  (1,1): 0
	  }
	 
	nn = perceptron.Perceptron()
	iterations = nn.train(nand_set, alpha=.2) # alpha is the learning rate
	print "Trained in {0} iterations.".format(iterations)
	print "Correct?", nn.test(nand_set)
	print "Weights: {0}, Threshold: {1}".format(nn.weights, nn.threshold)

Output:

	Trained in 9 iterations.
	Correct? True
	Weights: [-0.40000000000000002, -0.20000000000000001], Threshold: -0.5

Now that we have the weights (-0.4, -0.2) and threshold (-0.5), we can feed those in later without having to train it:

	nand_perceptron = perceptron.Perceptron((-0.4, -0.2), -0.5)
	print "Correct?", nand_perceptron.test(nand_set)

Author
------

Evan Fosmark -- This was originally published on my blog, but I've since refacored that website and moved all of the code to this git repo.