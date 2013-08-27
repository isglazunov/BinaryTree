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

To run the tests, you can try this:
`vows Tests.coffee --spec`

If you use `grunt`, the main file and the test file will be compiled automatically.

## Description

### handler
`(null, null) ->` not found
`(node, null) ->` last node
`(node, next) ->` not last node
the last returned node - the target node

### direction
1 - left
2 - right
0 - disable (not always)

## Methods

### search

#### search node by key, from root
`instance.search key target, (node, next) -> do next`

#### search node from root
`instance.safe.search [address, key, left, right] target, (node, next) -> do next`

#### search node from other node
`instance.unsafe search [address, key, left, right] source, [address, key, left, right] target, (node, next) -> do next`

### attach

#### create a node by a key and attach to the tree from the root
`instance.attach key target, (node, next) -> do next`

#### attach target node to the tree from the root
`instance.safe.attach [address, key, left, right] target, (node, next) -> do next`

#### attach target node to the tree from the source node
`instance.unsafe.attach [address, key, left, right] source, [address, key, left, right] target, (node, next) -> do next`

### detach

#### detach node by address from root node
`instance.detach address target, (node, next) -> do next`

#### detach target node from root node
`instance.safe.detach [address, key, left, right] target, (node, next) -> do next`

#### detach target node from source node
`instance.unsafe.detach [address, key, left, right] source, [address, key, left, right] target, (node, next) -> do next`

### travel

#### travel to node from node
`instance.unsafe.travel [address, key, left, right], (node, next) -> next [address, key, left, right]`

### corner

#### travel in a certain direction at specified node of the tree
`instance.unsafe.corner [address, key, left, right] source, Number direction, (node, next) -> do next`

### merge

#### merging the left and right node
`instance.unsafe.merge [address, key, left, right] left, [address, key, left, right] right, (node, next) -> do next`

## Changes.
### v0.1.0
Written including, possibly, all behaviors.
Written library performs tests.
The library can be used as a node.js module.

### v0.1.1
In the constructor method is added setNode, immediately setting the left and right subtree, for increased productivity.
Custom methods passed to the constructor transferred to the sub-object instance.user.
