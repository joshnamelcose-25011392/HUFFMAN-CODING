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
```
import heapq
from collections import Counter
```
```
import heapq
from collections import Counter
```
```
class Node:
    def __init__(self, char, freq):
        self.char = char
        self.freq = freq
        self.left = None
        self.right = None

    def __lt__(self, other):
        return self.freq < other.freq
```
```
def generate_codes(root, code="", codes=None):
    if codes is None:
        codes = {}

    if root is None:
        return codes

    if root.char is not None:
        codes[root.char] = code
        return codes

    generate_codes(root.left, code + "0", codes)
    generate_codes(root.right, code + "1", codes)

    return codes
```
```
def huffman_coding(text):

    # Calculate frequency
    frequency = Counter(text)

    # Create priority queue
    heap = []

    for char, freq in frequency.items():
        heapq.heappush(heap, Node(char, freq))

    # Build Huffman Tree
    while len(heap) > 1:
        left = heapq.heappop(heap)
        right = heapq.heappop(heap)

        new_node = Node(None, left.freq + right.freq)
        new_node.left = left
        new_node.right = right

        heapq.heappush(heap, new_node)

    root = heap[0]

    # Generate Huffman codes
    codes = generate_codes(root)

    return frequency, codes
```
```
text = "hello world"

frequency, codes = huffman_coding(text)

print("Character\tFrequency\tHuffman Code")
print("---------------------------------------------")

for char, freq in frequency.items():
    print(f"{repr(char)}\t\t{freq}\t\t{codes[char]}")
```

The Huffman Coding program is implemented using Python.

## Output

<img width="489" height="237" alt="Output png" src="https://github.com/user-attachments/assets/5532f3e9-4747-4156-a430-eec4d9714338" />

The program uses:

- `heapq` for the priority queue
- `Counter` from `collections` to calculate character frequencies

