# C Trees
## Terminology
- ROOT node has NO PARENT, all others have exactly one parent.
- Nodes can have MULTIPLE CHILDREN.
  - In a binary tree, each node can have AT MOST 2 children.
- LEAF nodes have NO CHILDREN.
- HEIGHT is the maximum possible number of nodes from the root to a leaf (inclusive).
  - The height of an EMPTY tree is 0.
- NODE COUNT is the number of nodes in a tree.

## Implementation
```C
struct btnode {
    int data;
    struct btnode *left;
    struct btnode *right;
 };

struct bst {
    struct btnode *root;
};

// bst_create() creates a new empty BST.
// effects: allocates heap memory [client must call bst_destroy]
// time: O(1)
struct bst *bst_create(void) {
    struct bst *bst = malloc(sizeof(struct bst));
    bst->root = NULL;
    return bst;
}

// bst_traverse(bst) traverses the tree bst.
// time: O(n)
void bst_traverse(const struct bst *bst) {
    assert(bst);
    if (bst->root != NULL) {
        bst_traverse_wrkr(bst->root);
    }
}
void bst_traverse_wrkr(const struct btnode *node) {
    if (node) {
        bst_traverse_wrkr(node->left);
        bst_traverse_wrkr(node->right);
    }
}

struct btnode *node_create(int data) {
    struct btnode *node = malloc(sizeof(struct btnode));
    node->data = data;
    node->left = NULL;
    node->right = NULL;
    return node;
}

void node_destroy(struct btnode *node) {
    assert(node);
    free(node);
}

void bst_insert(struct bst *bst, int data) {
    assert(bst);
    if (bst->root) { // root node already exists
        bst_insert_wrkr(bst->root, data);
    } else { // empty tree
        bst->root = node_create(data);
    }
}
void bst_insert_wrkr(struct btnode *node, int data) {
    // find node after which to insert
    struct btnode *insert_after = NULL;
    while (node != NULL) {
        insert_after = node;
        if (data < node->data) { // data should go left
            node = node->left;
        } else if (data > node->data) { // data should go right
            node = node->right;
        } else { // data already exists
            return;
        }
    }
    // inserting new data
    if (data < insert_after->data) {
        insert_after->left = node_create(data);
    } else if (data > insert_after->data) {
        insert_after->right = node_create(data);
    }
}
```

### Iteration vs. Recursion
Use iteration when you need to find a single node. <br>
Use recursion when you need to traverse the entire BST.
```C
// ITERATION TEMPLATE
void func(struct btnode *node) {
    struct btnode *parent = NULL;
    while (node && !pred(node)) {
        parent = node;
        if (pred(node) < 0) {
            node = node->left;
        } else { // pred(node) > 0
            node = node->right;
        }
    }
// do something to parent
/ or node
}

// RECURSION TEMPLATE
void func(struct btnode *node) {
    if (node != NULL) {
        func(node->left);
        func(node->right);
        // do something to node
    }
}

```


## Efficiency Talk
- Worst case efficiency for `insert` is O(n) when UNBALANCED (all nodes on one side).
- Best case eff iciency for `insert` is O(h) where h is the height of the tree.
    - BALANCED TREES have a height of O(log n)
- SELF-BALANCING TREES rearrange nodes to ensure the tree is always balanced to preserve the O(log n) running time.

## Node Augmentations
- Some implementations store the count in each node. Count is the number of nodes in its subtree. 










