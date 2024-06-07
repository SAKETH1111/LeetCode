# LeetCode Learning

# RAM

1 GB = 10^9 bytes
1 byte = 8 bits.
bits are 0 and 1.


Integers are commonly ocuppy  4 bytes i.e 32 bits in memory. They are stored in form of bytes that get converetd to bits.

Each character takes 8 bits of space, 1 byte, hence the addresses are 1 byte apart.

# Static Array

1. Arrays are a way of storing data contiguously(Sharing a common border or one next to other in a sequence)
2.  In strictly typed languages like Java, C++, C# etc, arrays have an allocated size when initialized. This means that the size of the array cannot change after its initialization. These are known as static arrays.
3.  Loosely typed languages such as Python and JavaScript do not have static arrays
4.  The most common operations are:
- Reading
- Deletion
- Insertion
5. The last index of the array is n-1 if n is the size of array
Reading from an array
1. Index starts from 0
// initialize myArray
int[] myArray = {1,3,5};

// access an arbitrary element, where i is the index of the desired value
myArray[i];

O(1) really means is that the number of operations is constant relative to the input size.

Traversing through an array

```
for (int i = 0; i < myArray.length; i++) {
    System.out.println(myArray[i]);
}

// OR

int i = 0;
while (i < myArray.length) {
    System.out.println(myArray[i]);
    i++;
}

```
Deleting from an array

