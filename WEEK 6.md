# have learned

operator : & ^ | ~

shift : >> <<

#### **struct pointer in function:**

1 insert After / Node Insertion in a Singly Linked List

2 Delete After / Node Deletion in a Singly Linked List

3 Deleting the Head Node

4 Deleting Middle and Tail Nodes

5 In-Place Linked List Reversal (`reverse_list`)  the step loop

## mistake i got

1

forget to check **`if (curr == null)`** then `return`

### 2

During the initial implementation of `delete_by_val`, the `head` pointer itself was directly mutated inside the traversal loop:

`// INCORRECT IMPLEMENTATION `

`while (head->next != NULL && head->next->val != target) `

`{    `

`head = head->next; // Defect: Shifts the list anchor`

` }`

#### correct:

**Use a traversal cursor**: 

Always instantiate a separate pointer       `struct Node *curr = head;`   

then replace the `head` with `curr` in the loop

```

```
