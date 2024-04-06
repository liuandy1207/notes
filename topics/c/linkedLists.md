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
  int length; // optional, used to cache info (update interface functions)
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
    struct llnode *to_destroy = current;
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

```C
// General Insertion
// time: O(n)
void slst_insert(struct llist *llst, int itm) {
  struct llnode *new_node = lln_create(itm);
  if (llst->front == NULL || itm <= llst->front->data) {
    new_node->next = llst->front;
    slst->front = new_node;
  } else {
    struct llnode *insert_after = llst->front;
    while (insert_after->next != NULL &&
    itm > insert_after->next->data) {
      insert_after = insert_after->next;
    }
    new_node->next = insert_after->next;
    insert_after->next = new_node;
  }
} 

// General Removal
// time: O(n)
bool ll_remove_item(struct llist *lst, int itm) {
  if (lst->front == NULL) return false;
  if (lst->front->data == itm) {
    ll_remove_front(lst);
    return true;
  }
  struct llnode *remove_after = lst->front;
  while (remove_after->next && itm != remove_after->next->data) {
    remove_after = remove_after->next;
  }
  if (remove_after->next == NULL) return false;
  struct llnode *to_remove = remove_after->next;
  remove_after->next = remove_after->next->next;
  lln_destroy(to_remove);
  return true;
}


```

### Linked List with a Back Pointer
Back pointers improve the efficiency of `insert_back` from O(n) to O(1).
```C
struct llist {
  struct llnode *front;
  struct llnode *back;
};

struct llist *ll_create(void) {
  struct llist *bpll = malloc(sizeof(struct llist));
  bpll->front = NULL;
  bpll->back = NULL;
  return bpll;
}

void ll_insert_front(struct llist *lst, int itm) {
  struct llnode *new_node = lln_create(itm);
  if (lst->front== NULL) { // inserting into empty list
    lst->front = lst->back = new_node;
  } else { // inserting into non-empty list
    new_node->next = lst->front;
    lst->front = new_node;
  }
}

void ll_insert_back(struct llist *lst, int itm) {
  struct llnode *new_node = lln_create(itm);
  if (lst->front == NULL) { // inserting into empty list
    lst->front = lst->back = new_node;
  } else { // inserting into non-empty list
    lst->back->next = new_node;
    lst->back = new_node
  }
}

void ll_remove_front(struct llist *lst) {
  assert(lst->front);
  struct llnode *to_remove = lst->front;
  lst->front = lst->front->next;
  lln_destroy(to_remove);
  if (lst->front == NULL) {
    lst->back = NULL;
  }
}

void ll_remove_back(struct llist *lst) {
  assert(lst->back);
  struct llnode *destroy_after = lst->front;
  struct llnode *to_destroy = lst->front;
  while (to_destroy->next != NULL) {
    destroy_after = to_destroy;
    to_destroy = to_destroy->next;
  }
  if (to_destroy == lst->first) { // removed final element
    lst->front = lst->back = NULL;
  } else { // removed non-final element
    destroy_after->next = NULL;
    lst->back = destroy_after;
  }
  lln_destroy(to_destroy);
}
```

<img width="948" alt="Screenshot 2024-04-06 at 12 51 51 PM" src="https://github.com/liuandy1207/notes/assets/72530429/9af17e7e-ba91-4f73-be5c-0cfce2850695">












