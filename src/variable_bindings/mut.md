<!--
# Mutability
-->
# ミュータビリティ

<!--
Variable bindings are immutable by default, but this can be overridden using
the `mut` modifier.
-->
変数はデフォルトでイミュータブル（変更不可能）ですが`mut`構文を使用することでミュータブルになります。

```rust,editable,ignore,mdbook-runnable
fn main() {
    let _immutable_binding = 1;
    let mut mutable_binding = 1;

    println!("Before mutation: {}", mutable_binding);

    // Ok
    mutable_binding += 1;

    println!("After mutation: {}", mutable_binding);

    // Error! Cannot assign a new value to an immutable variable
    // エラー! イミュータブルな変数には新しい値を代入できません
    _immutable_binding += 1;
    // FIXME ^ Comment out this line
    // FIXME ^ この行をコメントアウトしましょう
}
```

<!--
The compiler will throw a detailed diagnostic about mutability errors.
-->
コンパイラはミュータビリティに関するエラーの詳細を出してくれます。
