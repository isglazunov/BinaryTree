# BinaryTree
0.1.1

Methods for working with binary search tree. Support for duplication.

## Features
### Full modularity
#### As seen node array of 4 values.
`node = [address, key, left, right]`
##### address
a string or a number
##### key
just a number
##### left & right
address, or null if the subtree is empty

#### The constructor takes the wrapper methods.
**This module allows you to use anywhere.**
```
getNode = (address, callback) -> callback node # return the node address - address
setLeft = (address, leftLink, callback) ->
	# set at the left sub-node with address - address
	callback node # return the set via the node as getNode
setRight = (address, rightLink, callback) ->
	# set at the right sub-node with address - address
	callback node # return the set via the node as getNode
setNode = (address, leftLink, rightLink, callback) ->
	# set both the left and right subtree of a node with address - address
	callback node # return the set via the node as getNode
getRoot = (callback) -> callback root
setRoot = (link, callback) ->
	# use the link on the root
	callback link
```
An example can be seen in the test file or Tests.coffee Tests.js.

## Changes.
### v0.1.0
Written including, possibly, all behaviors.
Written library performs tests.
The library can be used as a node.js module.

### v0.1.1
In the constructor method is added setNode, immediately setting the left and right subtree, for increased productivity.
Custom methods passed to the constructor transferred to the sub-object instance.user.
