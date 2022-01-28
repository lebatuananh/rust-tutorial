# Kiến thức cơ bản

## Biến

- Mặc định biến trong rust là bất biến (immutable)

```rust
fn main() {
    let mut x = 10;
    println!("x={}", x);
    x = 20;
    println!("x={}", x);

    const CONST_VALUE: u128 = 100_000_000_000;
    println!("CONST_VALUE={}", CONST_VALUE);
}
```

## Shadowing

```rust
fn main() {
    let x = 10;
    println!("x = {}", x);
    let x = "name";
    println!("x={}", x);

    let outer = 32;
    {
        let inner = 100;
        println!("inner = {}", inner);
        let outer = 1000;
        println!("outer = {}", outer);
    }
    println!("outer = {}", outer);
}

```

## Data Type

### Scalar Data

> Ex:let x: u32 = 100


- **Integer**

| Length  | Signed | Unsigned | 
|:-------:|:------:|:--------:|
|  8 bit  |   i8   |    u8    |
| 16 bit  |  i16   |   u16    |
| 32 bit  |  i32   |   u32    |
| 64 bit  |  i64   |   u64    |
| 128 bit |  i128  |   u128   |
|  arch   | isize  |  usize   |

```rust
fn main() {
    let a: i64 = 111_111_111_111_111; // Decimals
    let b = 0xff; //Hex
    let c = 0o77; //Octal
    let d = 0b1111_0000; //binary
    let e = b'A'; // byte

    println!("a = {}", a);
    println!("b = {}", b);
    println!("c = {}", c);
    println!("d = {}", d);
    println!("e = {}", e);
}
```

- **Character**

```rust
fn main() {
    let c = 'a';
    let icon = '😋';
}
```

- **Boolean**

```rust

fn main() {
    let t = true;
    let f: bool = false;
}

```

- **Float**

```rust
fn main() {
    let f = 2.2;
    let g: f32 = 3.3;

    let sum = f + g;
    let subtraction = f - g;
    let multiplication = f * g;
    let division = f / g;
    let reminder = g % f;

    println!("sum = {}", sum);
    println!("subtraction = {}", subtraction);
    println!("multiplication = {}", multiplication);
    println!("division = {}", division);
    println!("reminder = {}", reminder);
}
```

### Compound Data

- **Tuple**
  - Dạng dữ liệu kết hợp với nhiều kiểu dữ liệu trong một tuple

```rust
fn main() {
    let tup = ("Hello", 1000_00);
    println!("{:?}", tup);

    let (_string, _integer) = tup;
    let _string = tup.0;
    let integer = tup.1;

    println!("{}", _integer);
    println!("{}", _string);
}

```

- **Array**
  - Là 1 danh sách có kích thước cố định và chứa các phần tử có kiểu dữ liệu đồng nhất

```rust
fn main() {
    let number = [100, 200, 300];
    println!("number = {}", number[0]);


    let _hashing = [0; 32];

    println!("{:?}", _hashing);

    for i in _hashing.iter() {
        print!("{}", i);
    }
}

```
