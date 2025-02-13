# Homework 3 CS523
## Author
Sarah Dylan

## Program Description

The goal of this library is to create a 'bbow' or big bag of words.
The big bag of words purpose is to count up occurrences of words in a provided text.
The provided definition of a word is as follows: one or more consecutive Unicode code points that are members of the letter
class that are seperated by whitespace. Any punctuation on the front or end should not be considered a part of the word.

The program must also satisfy this conditions:
* Keys are lower case words only (words are case-insensitive )
* If the word in text is all lowercase, the bbow should store a reference
to the word as the key
* Otherwise, it should create a new string that is the lowercased version of the word
* The keys must be of type Cow

I provided the implementations for the following functions
* extend_from_text - generates the bbow
* count - counts number of unique keys
* match_count - returns number of occurrences of one specific word

## Usage Instructions

### 1. **Add as a Dependency**
To use this library in your Rust project, add it to your `Cargo.toml`:

```toml
[dependencies]
hw_bbow = { git = "https://github.com/colonelcandycorn/hw3_rust" }
```

### 2. **Use in Your Code**
Import and use the library in your Rust project:

```rust
use hw_bbow::Bbow;

fn main() {
    let mut bbow = Bbow::new();
    bbow.extend_from_text("Hello, world!");
    
}
```

### 3. **Build and Test**
If you want to build and test the library locally:

```sh
cargo build
cargo test
```



## Issues Encountered
```rust
self.0.entry(word).and_modify(| count| { *count += 1}).or_insert(1);
```
* This particular line was the hardest to come up with. It is really hard for me
to have the right intuition about when * is required and not required. Also, I spent
a lot of time trying to figure out how to update only if a value existed otherwise set
to some default value. 
* It also took me a while to realize how powerful Cow::from is because I kept trying to manually say something
was borrowed or owned.
* Also hard to figure out how to test whether the values were corrected being set to borrowed vs. owned

