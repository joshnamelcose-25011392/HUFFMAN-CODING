# HUFFMAN-CODING
# Huffman Coding

## Aim

To implement Huffman Coding using Python to generate variable-length binary codes for characters based on their frequency of occurrence.

## Software Required

1. Python 3.x
2. Anaconda
3. Jupyter Notebook

## Algorithm

### Step 1:
Get the input string from the user.

### Step 2:
Calculate the frequency of each character in the input string.

### Step 3:
Create a node for each character and insert all nodes into a priority queue.

### Step 4:
Remove the two nodes with the lowest frequencies from the priority queue.

### Step 5:
Combine the two nodes to create a new node whose frequency is the sum of their frequencies.

### Step 6:
Repeat the process until only one node remains. This forms the Huffman Tree.

### Step 7:
Traverse the Huffman Tree and assign `0` to the left branch and `1` to the right branch.

### Step 8:
Display each character, its frequency, and its corresponding Huffman Code.

## Program

The Huffman Coding program is implemented using Python.

The program uses:

- `heapq` for the priority queue
- `Counter` from `collections` to calculate character frequencies

