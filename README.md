# scikit-learn-split-data
a simple exercise to understand a way of splitting the data into the training set and the test set in scikit-learn.

```
X =  list(range(20))
print (X)
#[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19]


y = [x*x for x in X]
print(y)
#[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196, 225, 256, 289, 324, 361]


Next, import model_selection from scikit-learn, and use the function train_test_split( ) to split our data into two sets:

import sklearn.model_selection as model_selection
X_train, X_test, y_train, y_test = model_selection.train_test_split(X, y, train_size=0.75,test_size=0.25, random_state=104) # random_state: to produce the same random result

print ("X_train: ", X_train)
print ("y_train: ", y_train)
print("X_test: ", X_test)
print ("y_test: ", y_test)

"""
X_train:  [13, 9, 11, 10, 7, 3, 0, 4, 17, 8, 15, 6, 14, 1, 5]
y_train:  [169, 81, 121, 100, 49, 9, 0, 16, 289, 64, 225, 36, 196, 1, 25]
X_test:  [19, 18, 16, 12, 2]
y_test:  [361, 324, 256, 144, 4]
"""
```

By specifying the train_size as 0.75, to put 75% of the data into our training set, and the rest of the data into the test set. Because there is only 20 data points, the program automatically rounded the ratio to 7:3.
Another observation is that the numbers in the lists after splitting do not follow the same ascending order as before. In another word, by default, the program ignores the original order of data.
