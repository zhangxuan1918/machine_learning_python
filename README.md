# MACHINE LEARNING PYTHON CODES

We list some commonly used machine learning codes in python for further reference

## ENCODING LABELS

#### ONE HOT SHOT ENCODING

Suppose you have a numpy list of labels, e.g., np.array([0,1,2,3,4,5,6,7,8,9]). Now you want to do one-hot-shot encoding, you can do this
```
one_hot_shot_labels = (np.arange(num_labels)) == labels[:, None]).astype(np.float32)

```