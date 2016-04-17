# MACHINE LEARNING PYTHON CODES

We list some commonly used machine learning codes in python for further reference

## ENCODING LABELS

#### ONE HOT SHOT ENCODING

Suppose you have a numpy list of labels, e.g., np.array([0,1,2,3,4,5,6,7,8,9]). Now you want to do one-hot-shot encoding, you can do this
```
one_hot_shot_labels = (np.arange(num_labels)) == labels[:, None]).astype(np.float32)
```

## INITIALIZATION

In neural network, we usually randomly initialize weights before training. How to initialize the weights matters. Preferably, we initialize the weights to be Gaussian rvs with small variation. Notice, if the the variation is too big, we might have a very big l2 penalty (if we use l2 to regularize). The first a few iteration (say using stochastic gradient descend) will reduce the weights instead of minimizing the error. However, if the weights are too small, then, the l2 penalty is too small and sometimes the optimization will not work properly. Probably because the weights are too small and doesn't change the output too much.

## SSH DOCKER TO INSTALL PACKAGES
1. find docker images: `docker images`
2. ssh docker container: `docker run -i -t <docker-id> /bin/bash`
3. install packages
4. commit container to a new named image: `docker commit <container> <some_name>`

## DOCKER CREATE IAMGE AND CONTAINERS
1. go to the project fold which contains file `Dockerfile`
2. run docker build to build the image: `docker build --pull -t <docker image tag> .`
3. run docker create to create a container as data storage: `docker create -i -t -v /Users/xuan/Personal/github_repository/docker-container-data --name data-storage xuan/deep-learning-version1 /bin/true`
4. run docker run to create a container as application: `docker run -d -i -t --volumes-from data-storage --name <container-name> xuan/deep-learning-version1` 