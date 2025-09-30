# Experiment 18: Queue in C++
---
## Aim
To study and implement the Queue data structure in C++ by performing:
1. Basic queue creation using arrays.
2. Enqueue (insertion) operation.
3. Dequeue (deletion) operation.
4. Displaying elements of the queue.

---

## Tools Used
VS Code

---

## Theory

## Linear Data Structures
- Linear data structures store elements sequentially and allow traversal in a single logical order.
- Examples: Arrays, Stacks, Queues, Linked Lists.
- Operations like insertion, deletion, and traversal are performed sequentially.
- Queues are widely used in real-world systems where data must be processed in the order it arrives.

---

## Queue
- A **queue** is a linear data structure that follows the **FIFO (First In First Out)** principle.
- The element inserted first is removed first.
- It has two ends:
  - **Front** → points to the first element (for deletion).
  - **Rear** → points to the last element (for insertion).
- Used in scheduling, buffering, and communication systems.

---

## Block Representation of Queue
```
          +-------------------------+
          |       Queue (Array)     |
          +-------------------------+
          |   Front Index  (front)  |
          |   Rear Index   (rear)   |
          +-------------------------+
                     |
    -----------------------------------------
    |         |         |         |         |
   arr[0]    arr[1]    arr[2]    arr[3]    arr[4]
    (10)      (20)      (30)      (40)     (..)
     ↑                                  ↑
   Front                               Rear

Enqueue → Insert at Rear  
Dequeue → Remove from Front

```

---

## Types of Queues
### 1. Simple Queue
- Linear structure with insertion at rear and deletion at front.
- Fixed size when implemented with arrays.
- Risk of "overflow" and "underflow."

### 2. Circular Queue
- Rear wraps around to the front when space is available.
- Efficient memory utilization.
- Prevents wastage of space in array implementation.

### 3. Priority Queue
- Each element has a priority.
- Elements with higher priority are dequeued before lower ones.
- Implemented with heaps or arrays.

### 4. Double-Ended Queue (Deque)
- Insertions and deletions are allowed at both ends.
- Flexible structure.
- Used in cache implementation and sliding window problems.

---

## Difference Between Stack and Queue

| Feature            | Stack                          | Queue                         |
|--------------------|--------------------------------|-------------------------------|
| Principle          | LIFO (Last In First Out)       | FIFO (First In First Out)     |
| Insertion Point    | Top                            | Rear                          |
| Deletion Point     | Top                            | Front                         |
| Example            | Undo operations, recursion     | Scheduling, buffering         |
| Access             | One end                        | Two ends                      |

---

## How a Queue Works
1. Initially, the queue is empty (`front = -1, rear = -1`).
2. **Enqueue**: Insert element at `rear` and increment `rear`.
3. **Dequeue**: Remove element at `front` and increment `front`.
4. Queue becomes empty when `front > rear`.

---

## Memory Storage
- In array implementation, queue elements are stored contiguously.
- In linked list implementation, queue elements are stored dynamically with pointers.
- For this experiment, array-based implementation is used.

---

## Advantages of Queues
1. Order preservation (FIFO).
2. Useful in handling requests sequentially.
3. Easy to implement with arrays and linked lists.
4. Essential in time-sharing and scheduling.

---

## Disadvantages of Queues
1. Fixed size in array-based implementation (overflow).
2. Underflow when queue is empty.
3. In simple queue (array-based), deleted positions cannot be reused until reset (solved by circular queue).
4. Slower search compared to arrays with direct indexing.

---

## Difference Between Array, Stack, Queue, and Linked List

| Aspect      | Array                          | Stack                           | Queue                           | Linked List                        |
|-------------|--------------------------------|---------------------------------|---------------------------------|------------------------------------|
| Structure   | Contiguous memory              | LIFO (Last In First Out)        | FIFO (First In First Out)       | Nodes connected via pointers       |
| Access      | O(1) by index                  | O(n) search                     | O(n) traversal                  | O(n) traversal                     |
| Insertion   | Costly (shifting needed)       | O(1) push/pop at top            | O(1) enqueue at rear            | O(1) with pointer update           |
| Deletion    | Costly (shifting needed)       | O(1) pop at top                 | O(1) dequeue at front           | O(1) with pointer update           |
| Size        | Fixed                          | Dynamic if LL-based             | Dynamic if LL-based             | Dynamic, flexible size             |
| Applications| Tables, matrices               | Undo stack, recursion           | Scheduling, buffering           | Dynamic memory management, graphs  |

---

## Algorithm and Flowchart

### Algorithm
**Main Program Flow**
1. Start.
2. Initialize queue with `front = -1` and `rear = -1`.
3. Enqueue elements into queue.
4. Display queue.
5. Dequeue element.
6. Display queue again.
7. Repeat enqueue/dequeue as needed.
8. Stop.

**Enqueue(x)**
1. Check if `rear == SIZE-1`: if yes, Overflow.
2. If `front == -1`, set `front = 0`.
3. Increment `rear` and insert value.
4. Print insertion success.

**Dequeue()**
1. Check if `front == -1` or `front > rear`: if yes, Underflow.
2. Print and remove element at `front`.
3. Increment `front`.

**Display()**
1. Check if queue empty: if yes, print "empty".
2. Else, print all elements from `front` to `rear`.

---

### Flowchart
```
+----------------+
|     Start      |
+----------------+
       |
       v
+-------------------+
| Initialize Queue  |
| front=-1, rear=-1 |
+-------------------+
       |
       v
+-------------------+
|   Enqueue(x)?     |
+-------------------+
       | Yes
       v
+-------------------+
| rear == SIZE-1 ?  |
+-------------------+
   |Yes         |No
   v            v
Overflow   +-------------------+
           | Insert element at |
           | arr[++rear]       |
           | if front==-1, set |
           | front=0           |
           +-------------------+
                   |
                   v
        +-------------------+
        |   Display Queue   |
        +-------------------+
              |
              v
+-------------------+
|   Dequeue()?      |
+-------------------+
       | Yes
       v
+-------------------+
| front==-1 or      |
| front>rear ?      |
+-------------------+
   |Yes         |No
   v            v
Underflow   +-------------------+
            | Remove arr[front] |
            | front++           |
            +-------------------+
                   |
                   v
           +-------------------+
           | Display Queue     |
           +-------------------+
                   |
                   v
           +----------------+
           |      End       |
           +----------------+


```
---

## Industrial Applications of Queues
1. **CPU Scheduling** – Round-robin process scheduling; Linux, Windows.  
2. **Disk Scheduling** – Managing I/O requests; IBM, Oracle.  
3. **Networking** – Packet buffering and routing; Cisco, Juniper.  
4. **Call Centers** – Customer service queues; Genesys, Avaya.  
5. **Simulation Systems** – Traffic flow, manufacturing; MATLAB, Simulink.  
6. **Printers** – Print job scheduling.  
7. **Messaging Systems** – Kafka, RabbitMQ, AWS SQS.  
8. **Operating Systems** – Ready queue, wait queue management.

---

## Significance
- Provides systematic management of tasks and resources.
- Handles multiple requests fairly in real-time systems.
- Ensures smooth scheduling and load balancing.
- Used as the foundation for advanced scheduling and buffering algorithms.


