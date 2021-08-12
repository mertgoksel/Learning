# Decision Trees

Decision trees are one of the most basic and widely used methods of machine learning. All you do is putting filters in priority order and ultimately use these filters to slice data at each step (node, filter etc.) to finally categorize them. 

# Methods

## Gini method

Impurity = 1 - P(yes)^2 - P(no)^2. 
The impurity of a decision node is the weigthed average gini of both versions of that filter 
(aka. one for "no" inbound, one for "yes" inbound)

### Example

filter => patient has chest pain -> patient has heart desease, the table of this looks like:

chest pain\heart desease  yes  no
yes                       100  40
no                        30   110

then the nodes are A(yes: 100, no:30), B(yes: 40, no:110) so the partial impurities are thus 
A = 1-(100/130)^2-(30/130)^2 = 0.35502958579 
B = 1-(40/150)^2-(110/150)^2 = 0.39111111111
Impurity = 130/(130+150))*A + (150/(130+150))*B = 0.37435897435