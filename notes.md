## operator overloading :
- defining custom behaviour for operators.
```rust
pub trait PartialEq {
    fn eq(&self, other: &Self) -> bool;

    fn ne(&self, other: &Self) -> bool {
        !self.eq(other)
    }
}
```

## string :
-&String points to the memory location where the String's metadata is stored.
thru the pointer we get to the first byte of this String .

- Important point :
1. A `String` type is a container for a `str` that is stored on the heap.

2. str is the actual text iteself , with no pointers involved.
-> generally we should use `&str` when we know there is an owner of the string already and we can borrow it as long as we need it .

## deref coercion :
For `Deref<Target = U>` for a type T :
In particular, you get the following behavior:
-References to T are implicitly converted into references to U (i.e. &T becomes &U)
You can call on &T all the methods defined on U that take &self as input.


NOTE : str is a DST (Dynamically sized type) 
- means whose size is not known at compile time 
eg . The `size_of` function requires the type to implement the Sized trait, which str does not