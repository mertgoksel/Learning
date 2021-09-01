# Forest Classifier

Basically this is the more iterative and more advanced version of decision trees

This method is used if decision trees is appropriate for the data.

## Method

The main dataset is broken down to random versions of it and the empty rows are then filled with random rows of the new dataset, thus repetition. 

Then doing this n times (aka tree number) each new dataset then gets its own decision tree. 

When new data comes it then goes through each tree, the classifications are then counted. The most repeated class from all decision trees is the class that will be given.
