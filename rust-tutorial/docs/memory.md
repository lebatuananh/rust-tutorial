|                  |                                                     Ưu điểm                                                      |                                                    Nhược điểm                                                     | 
|:----------------:|:----------------------------------------------------------------------------------------------------------------:|:-----------------------------------------------------------------------------------------------------------------:|
| Bộ gom rác (GC)  |                                 - Không có lỗi <br/> - Giảm thời gian viết code                                  | - Không thể quản lý bộ nhớ <br/> - Thời gian biên dịch chạy chương trình chậm hơn <br/> - Dung lượng file lớn hơn |
| Quản lý thủ công |         - Có quyền kiểm soát bộ nhớ <br/> - Chương trình chạy nhanh hơn <br/> - Dung lượng file nhỏ hơn          |                                                  - Viết code lâu                                                  |
|    Ownership     | - Có thể kiếm soát bộ nhớ <br/> - Không có lỗi <br/> - Chương trình chạy nhanh hơn <br/> Dung lượng file nhỏ hơn |                                                  - Viết code lâu                                                  |

# Stack & Heap

```rust
fn main() {
    fn _x() {
        let _a = "Hello";
        let _b = 100;
        _y();
        println!("a = {}", _a);
    }

    fn _y() {
        let mut _a = String::from("world");
    }
}
```

- Mỗi giá trị trong Rust chỉ có một biến được gọi là chủ sở hữu. *( One variable one owner )*
- Chỉ có một owner ở cùng một thời điểm
- Khi owner đi ra khỏi phạm vi hoạt động giá trị sẽ bị hủy
