> [!NOTE]
> このライブラリは[romaji_kana_cvt_rust](https://github.com/yumetodo/romaji_kana_cvt_rust)をベースにライブラリ用途に向けて改変を行ったものです。

使い方:

```rust
use romaji_kana_cvt_rust::cvt::RomajiCvt;

fn main() {
    let conv = RomajiCvt::new();
    let result = conv
        .from_romaji("waruitessakugakusatteiruwa".to_string())
        .unwrap();

    println!("{}", result); // => わるいてっさくがくさっているわ
    println!("{}", conv.to_romaji(result).unwrap()); // => waruitessakugakusatteiruwa
}
```

以下のメソッドがあります。

- `from_romaji`
ローマ字からひらがなへ変換します。

- `to_romaji`
メソッドでひらがなからローマ字へ変換します。

# romaji_kana_cvt_rust


[![Build Status](https://travis-ci.org/yumetodo/romaji_kana_cvt_rust.svg?branch=master)](https://travis-ci.org/yumetodo/romaji_kana_cvt_rust)

ローマ字かな変換をRustで

ローマ字の定義はJIS X 4063:2000(2010年1月20日に廃止)に従います。ただし`^`は`ー`に変換されません。  
ref: [ローマ字入力 - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%AD%E3%83%BC%E3%83%9E%E5%AD%97%E5%85%A5%E5%8A%9B)

詳細は

[ローマ字かな変換をRustで - Qiita](https://qiita.com/yumetodo/items/376c94b618a4aeb49445)

## 使用法

`git clone`して`cargo build --release`すれば普通にコンパイルできるはずだ。

```bash
$ cargo build --release
   Compiling void v1.0.2
   Compiling unreachable v1.0.0
   Compiling smallvec v0.6.8
   Compiling unicode-normalization v0.1.8
   Compiling romaji_kana_cvt_rust v1.1.0 (C:\msys64\home\yumetodo\romaji_kana_cvt_rust)
    Finished release [optimized] target(s) in 38.21s

$ pushd target/release/
~/romaji_kana_cvt_rust/target/release ~/romaji_kana_cvt_rust

$ ./romaji_kana_cvt_rust.exe ありきたりなせかい
arikitarinasekai

$ ./romaji_kana_cvt_rust.exe arikitarinasekai
ありきたりなせかい
```
