GA-Segments
============

GA-Segments is the package  for efficient prototyping of large time series datasets using DTW distance. 

Example of use of GA-Segments:

.. code-block:: python

	>>> from ga_segments.ga import GA_segments
	>>> import pandas as pd
	
	>>> series = pd.read_csv('./data/50words_TRAIN', header=None).values[:, 1:]
	
	>>> ga = GA_segments()
	>>> centroid, best_fitness, log = ga.calculate_centroids(series)
	
	
Example of use of Nearest Centroid algorithm with GA-Segments:

.. code-block:: python

	>>> from ga_segments.nc import NC
	>>> import pandas as pd
	>>> from sklearn.model_selection import train_test_split
	
	>>> series = pd.read_csv('./data/50words_TRAIN', header=None)
	>>> x, y = series[:, 1:], series[:, 0]
	>>> x_train, x_val, y_train, y_val = train_test_split(x, y, test_size=0.2)
	
	>>> nc = NC()
	>>> nc.fit(x_train, y_train)
	>>> nc.predict(x_val)
	>>> nc.labels
	

Installation
------------

At the moment don't exist pip installation. You can clone the respository and use one of the notebooks. The package has only been tested in the 64-bit Ubuntu operating system.

You have to install the following packages wiht pip:

* numpy
* pandas
* deap
* scikit-learn
* matplotlib

