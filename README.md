# Binary Search Tree Implementation - Word Tracker

A complete implementation of a Binary Search Tree (BST) data structure in Java with generic type support and word tracking functionality.

This project demonstrates object-oriented programming principles including inheritance, interfaces, generics, and data structure design patterns. Built for CPRG 304 (Object-Oriented Programming III) with comprehensive unit tests.

## Features

- **Generic Binary Search Tree** - Type-safe implementation supporting any Comparable element
- **Complete BST Operations** - Add, search, remove min/max, and tree traversal
- **Multiple Traversal Methods** - In-order, pre-order, and post-order traversals
- **Word Tracking** - Track and manage word occurrences and statistics
- **Iterator Pattern** - Efficient iteration over tree elements
- **Comprehensive Tests** - Unit tests for all major operations
- **Object Serialization** - Serialize and persist tree data

## Tech Stack

- **Java 8+** - Core language
- **JUnit 4** - Unit testing framework
- **Generic Types** - Type-safe implementations
- **Collections API** - ArrayList for traversals and iteration

## Project Structure

```
src/
├── implementations/
│   ├── BSTree.java           # Main BST implementation
│   ├── BSTreeNode.java       # Node structure for BST
│   └── WordNode.java         # Word tracking node (if applicable)
├── utilities/
│   ├── BSTreeADT.java        # Abstract Data Type interface
│   └── Iterator.java         # Custom iterator interface
└── test/
    └── unitTests/
        └── BSTreeTest.java   # Comprehensive unit tests
```

## Getting Started

### Prerequisites

- Java 8 or higher
- JUnit 4 (for running tests)
- Maven or Gradle (optional, for dependency management)

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/webdevyn/OOP3-BinarySearchTreeImplementation_Word-Tracker.git
cd OOP3-BinarySearchTreeImplementation_Word-Tracker
```

2. **Compile the code**

```bash
javac -d bin src/**/*.java
```

3. **Run the application**

```bash
java -cp bin implementations.BSTree
```

## Core Classes

### BSTreeNode<E>
Represents a single node in the binary search tree.

**Key Methods:**
- `getData()` / `setData(E data)` - Get/set node data
- `getLeft()` / `setLeft(BSTreeNode<E> left)` - Left child access
- `getRight()` / `setRight(BSTreeNode<E> right)` - Right child access
- `getElement()` - Retrieve element data

```java
BSTreeNode<Integer> node = new BSTreeNode<>(42);
```

### BSTree<E>
The main Binary Search Tree implementation.

**Key Methods:**
- `add(E newEntry)` - Insert element maintaining BST property
- `contains(E entry)` - Check if element exists
- `search(E entry)` - Find and return node with element
- `removeMin()` - Remove smallest element
- `removeMax()` - Remove largest element
- `getHeight()` - Calculate tree height
- `size()` - Return number of elements
- `isEmpty()` - Check if tree is empty
- `clear()` - Remove all elements

**Traversal Methods:**
- `inorderIterator()` - Left-Root-Right traversal
- `preorderIterator()` - Root-Left-Right traversal
- `postorderIterator()` - Left-Right-Root traversal

```java
BSTree<Integer> tree = new BSTree<>();
tree.add(50);
tree.add(30);
tree.add(70);

Iterator<Integer> iter = tree.inorderIterator();
while (iter.hasNext()) {
    System.out.println(iter.next());
}
```

### BSTreeADT<E> Interface
Defines the contract for BST implementations.

## Testing

Run the comprehensive unit test suite:

```bash
# Using JUnit from command line
java -cp bin:junit-4.13.jar:hamcrest-core-1.3.jar org.junit.runner.JUnitCore unitTests.BSTreeTest

# Or compile and run with JUnit
javac -cp bin:junit-4.13.jar -d bin test/unitTests/BSTreeTest.java
```

### Test Coverage

The `BSTreeTest` class includes tests for:
- Tree construction and initialization
- Adding elements (single, multiple, duplicates)
- Searching and containment checks
- Removing minimum and maximum elements
- Tree traversals (in-order, pre-order, post-order)
- Edge cases (empty tree, single node)
- Height and size calculations

## Usage Examples

### Basic Operations

```java
// Create a tree for integers
BSTree<Integer> tree = new BSTree<>();

// Add elements
tree.add(50);
tree.add(30);
tree.add(70);
tree.add(20);
tree.add(40);
tree.add(60);
tree.add(80);

// Check size and height
System.out.println("Size: " + tree.size());        // Size: 7
System.out.println("Height: " + tree.getHeight()); // Height: 3

// Search for an element
if (tree.contains(30)) {
    BSTreeNode<Integer> node = tree.search(30);
    System.out.println("Found: " + node.getData());
}

// Remove min and max
tree.removeMin();  // Removes 20
tree.removeMax();  // Removes 80
```

### Tree Traversals

```java
// In-order traversal (sorted order)
Iterator<Integer> inorder = tree.inorderIterator();
while (inorder.hasNext()) {
    System.out.print(inorder.next() + " ");
}
// Output: 30 40 50 60 70

// Pre-order traversal (good for tree copying)
Iterator<Integer> preorder = tree.preorderIterator();

// Post-order traversal (good for tree deletion)
Iterator<Integer> postorder = tree.postorderIterator();
```

### Generic Usage

```java
// Works with any Comparable type
BSTree<String> stringTree = new BSTree<>();
stringTree.add("apple");
stringTree.add("banana");
stringTree.add("cherry");

BSTree<Double> doubleTree = new BSTree<>();
doubleTree.add(3.14);
doubleTree.add(2.71);
doubleTree.add(1.41);
```

## Key Concepts Demonstrated

- **Generics** - Type-safe, reusable data structures
- **Interfaces** - Define contracts and abstract methods
- **Recursion** - Recursive search and insertion
- **Tree Traversal** - Multiple traversal strategies
- **Iterator Pattern** - Efficient iteration without exposing structure
- **Serialization** - Persistent data storage
- **Unit Testing** - Comprehensive test coverage

## Algorithm Complexity

| Operation | Average | Worst Case |
|-----------|---------|------------|
| Search | O(log n) | O(n) |
| Insert | O(log n) | O(n) |
| Delete | O(log n) | O(n) |
| Height | O(n) | O(n) |
| Traversal | O(n) | O(n) |

## Learning Resources

- **Data Structures**: Understanding tree traversal and insertion algorithms
- **OOP Principles**: Generic types, interfaces, and inheritance
- **Java Collections**: Iterator pattern and ArrayList usage
- **Testing**: JUnit framework and test-driven development

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Commit changes (`git commit -m 'Add improvement'`)
4. Push to branch (`git push origin feature/improvement`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.

## Author

**Devyn Weir**
- GitHub: [@webdevyn](https://github.com/webdevyn)

## Support

For issues, questions, or suggestions, please open a GitHub Issue.

---

**Course**: CPRG 304 - Object-Oriented Programming III  
**Last Updated**: July 16, 2026  
**Status**: Complete
