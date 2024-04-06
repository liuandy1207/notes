# C Linked Lists

## Linked Lists
LLs are sequences of nodes, where each node contains some DATA and a LINK to the next node in the list. <br>
The last node does NOT link to another node. 

LLs can grow and shrink at run-time.

A significant advantage over arrays is that it is possible to easily add items to and remove items from the FRONT and the MIDDLE.

### Nodes
Nodes are implemented as structures (`llnode`) and the link between nodes is implemented as a pointer.<br>
The pointer value of the last node is `NULL`, indicating the end of the LL.

The beginning of an LL is usually implemented as seperate WRAPPER STRUCTURE (`llist`), which contains a POINTER to the FRONT / HEAD / FIRST NODE of the LL. <br>
Clients only interact with the LL through the wrapper structure `llist`. <br>
This prevents the client from directly accessing and manipulating the linked data (information hiding).

### Definition
```C
struct llist {
  struct llnode *front;
};

struct llnode {
  int data;
  struct llnode *next;
};

// INTERFACE FUNCTIONS
struct llist *ll_create(void) {
  struct llist *llst = malloc(sizeof(struct llist));
  assert(llst);
  llst->front = NULL;
  return llst;
}

struct llnode *lln_create(int data) {
  struct llnode *lln = malloc(sizeof(struct llnode));
  assert(lln);
  lln->data = data;
  lln->next = NULL;
  return lln;
}

void ll_insert_front(struct llist *lst, int itm) {
  struct llnode *new_node = lln_create(itm);
  new_node->next = lst->front; // point to original first
  lst->front = new_node; // become new first
}

// Traversal - Iterative Approach
int ll_length(const struct llist *llst) {
  int len = 0;
  const struct llnode *current = llst->front;
  while (current) {
    ++len;
    current = current->next;
  }
  return len;
}

// Traversal - Recursive Approach
int ll_length_wrkr(const struct llnode *lln) {
  if (!lln) {
    return 0;
  } else {
    return 1 + ll_length_wrkr(lln->next);
  }
}
int ll_length(const struct llist *llst) {
  return ll_length_wrkr(llst->front):
}

// Destruction - Iterative Approach
void ll_destroy(struct llist *lst) {
  struct llnode *current = lst->front;
  while (current) {
    current = current->next;
    lln_destory(to_destroy);
  }
  free(lst);
}

// Destruction - Recursive Approach
void ll_destroy_wrkr(struct llnode *lln) {
  if (lln) {
    ll_destroy_wrkr(lln->next);
    lln_destroy(lln);
  }
}
void ll_destroy (struct llist *llst) {
  ll_destroy_wrkr(llst->front);
  free(lst);
}

void lln_destroy(struct llnode *lln) {
  assert(lln);
  free(lln);
}

// Back Insertion - Iterative Approach
// time: O(n)
void ll_insert_back(struct llst *lst, int itm) {
  struct llnode *new_node = lln_create(itm);
  if (!lst->front) {
    lst->front = new_node;
  } else {
    struct llnode *insert_after = lst->front;
    while (insert_after->next != NULL) {
      insert_after = insert_after->next;
    }
    insert_after->next = new_node;
  }
}

// Back Insertion - Recursive Approach
void ll_insert_back_wrkr(struct llnode *lln, int itm) {
  if (lln->next == NULL) {
    lln->next = lln_create(itm);
  } else {
  ll_insert_back_wrkr(lln->next, itm);
  }
}
void ll_insert_back(struct llist *lst, int itm) {
  if (lst->front == NULL) {
    lst->front = lln_create(itm);
  } else {
    ll_insert_back_wrkr(lst->first, itm)
  }
}

```















