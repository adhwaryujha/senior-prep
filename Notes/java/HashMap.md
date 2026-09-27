HashMap:
Syntax- HashMap<String, Integer> res = new HashMap<String, Integer>();

- At the core of hashmaps they actually contain array of buckets.
- these buckets are nothing but nodes which store key value pair.
- So when we add any key value pair it actually internally evaluates= (n-1) & hashcode(key), then at that index it places the key-value pair.
- Earlier this index was calculated by modulus operator of hashcode % n, which later resulted in many collided pairs to get inded in same bucket which later made a in-efficient log(n) linear search to get() elements.
- To protect against this, Java 8 introduced a major structural optimization:
  - TREEIFY_THRESHOLD (8): If a single bucket accumulates 8 or more nodes, the linked list is transformed into a Red-Black Tree. This restores worst-case search performance from O(n) to O(log n).
  - MIN_TREEIFY_CAPACITY (64): This tree conversion only occurs if the total array capacity is at least 64. If the array is smaller, the HashMap will simply resize and rehash the entire array instead of building a tree.
  - UNTREEIFY_THRESHOLD (6): If the tree shrinks to 6 nodes (due to removals or a resize event), it reverts back to a Linked List. Tree nodes take up roughly twice as much memory as standard nodes, so this prevents unnecessary memory bloat.
- So to prevent inconsistency at the collisions the hashmap uses hashcode() first and then later at the node it actually checks if already existing keys are equal() to the new insertion.
- These 2 step verificaition ensures that a hashmap is always having unique keys all the time. So a second map.put(A, B) actually returns old value B before overwriting it with C.
  
