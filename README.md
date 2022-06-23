# MetricLearning
Applying weekly supervised metric learning

To make an analogy to human performed tasks, the given task is similar to recognizing
handwriting. In this task one has to recognize and identify characters to known characters of
an alphabet, while also dealing with noise resulting from individual differences. Furthermore,
this skill of analyzing similarity between characters extends to unknown characters as well,
such as hieroglyphs.

In machine learning, performing a similar task where glyphs need to be seperated can be
formulated as an image retrieval task. A neural network will implement this task by creating
an embedding for similarities between images in continuous vector space. By comparing the
embeddings a judgement on similarity can be made. A cutoff value is then used to come to
the binary conclusion on whether the character is identical to the query image or not.
This particular approach to this problem, where a single reference query image is used, is
called weakly supervised learning.

The end goal is to identify whether characters are the same or not, as mentioned before, this
is a binary result, which can be quantified in an accuracy score. This can be done using the
ratio of correct identifications to the amount of total trials. There is no specific reason to use
precision or recall in this model specifically, as there is no reason why both false positives
and false negatives could not be tolerated. Therefore accuracy was chosen to use as the
metric for determining the performance of the neural network.

Before this can be done however, it is needed to first determine a threshold that serves as
the aforementioned cut off for the final evaluation. This threshold is defined by first gathering
for all queries the furthest euclidean distance of the image that is still labeled as identical, as
well as the closest image that is labeled as different. An iteration of 100 equal steps between
these two values is performed and the accuracy is measured each time. Finally, the best
performing threshold, based on its accuracy, is chosen.
