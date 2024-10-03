Sequence in Rust is like Python List,  and  Map is  like  Python dictionary. But one of the key differences is that they're immutable  by default.

```rust
fn main() {
    let fruits = vec!["Apple", "Banana", "Cherry"];
    for fruit in &fruits {
        println!("{}", fruit);
    }

    let map = std::collections::HashMap::new();
    map.insert("key", "value"); // this will cause compile time error
}
```

# Print Rust data structure
```rust
fn main() {
    println!("Common Rust Collections:");

    // Sequences
    println!("\n\tSequences:");
    println!("\t\tVec: https://doc.rust-lang.org/std/vec/struct.Vec.html");
    println!(
        "\t\tVecDeque: https://doc.rust-lang.org/std/collections/vec_deque/struct.VecDeque.html"
    );
    println!("\t\tLinkedList: https://doc.rust-lang.org/std/collections/linked_list/struct.LinkedList.html");

    // Maps
    println!("\n\tMaps:");
    println!("\t\tHashMap: https://doc.rust-lang.org/std/collections/struct.HashMap.html");
    println!("\t\tBTreeMap: https://doc.rust-lang.org/std/collections/struct.BTreeMap.html");

    // Sets
    println!("\n\tSets:");
    println!("\t\tHashSet: https://doc.rust-lang.org/std/collections/struct.HashSet.html");
    println!("\t\tBTreeSet: https://doc.rust-lang.org/std/collections/struct.BTreeSet.html");

    // Misc
    println!("\n\tMisc:");
    println!("\t\tBinaryHeap: https://doc.rust-lang.org/std/collections/struct.BinaryHeap.html");
}
```

## Vector
```rust
use rand::seq::SliceRandom; // rand is random number generation library
use rand::thread_rng;
/**
 * This program creates a fruit salad by scrambling a list of fruits.
 * A vector is a growable array. It can grow or  shrink in  size and is  one of the  most
 * useful datastructures in Rust. The `vec!` macro is used to create a vector. A vector is
 * represented using the Vec<T> type.
 */
use std::vec;

fn main() {
    let mut fruit = vec!["Orange", "Fig", "Pomegranate", "Cherry", "Apple", "Grape"];
    // Shuffle the fruits
    let mut rng = thread_rng();
    fruit.shuffle(&mut rng);

    // Printout the fruit salad
    println!("Fruit Salad:");
    for (i, item) in fruit.iter().enumerate() {
        if i != fruit.len() - 1 {
            print!("{}, ", item);
        } else {
            println!("{}", item);
        }
    }
}
```

## Vec Dequeue
Double ended queue similar to python's  Dequeue. Cool thing  about it is, it has O(1) time complexity for operations on  both ends.