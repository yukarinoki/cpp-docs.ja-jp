---
title: アルゴリズム (現代的なC++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
ms.openlocfilehash: b972e575c982ae2523ec560a6237eac76ceaf834
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345176"
---
# <a name="algorithms-modern-c"></a>アルゴリズム (現代的なC++)

現代的なC++プログラミングでは[C++標準ライブラリ](../standard-library/cpp-standard-library-reference.md)のアルゴリズムを使用することをお勧めします。いくつかの重要な例を示します。

- **for_each** 既定の走査アルゴリズムです。(また **transform** が入力を出力で上書きしない場合に使えます)。

- **find_if** 既定の検索アルゴリズムです。

- **sort**、 **lower_bound**、およびその他の既定の並べ替えと検索アルゴリズム。

比較子を記述するには、狭義の **<** と *名前付きラムダ* を使用することができます。

```cpp
auto comp = [](const widget& w1, const widget& w2)
     { return w1.weight() < w2.weight(); }

sort( v.begin(), v.end(), comp );

auto i = lower_bound( v.begin(), v.end(), comp );
```

## <a name="loops"></a>ループ

可能であれば、手書きのループの代わりに範囲ベースの **for** ループやアルゴリズムの呼び出しを使いましょう。 **copy**、**transform**、 **count_if**、 **remove_if**、などは、処理の意図が明確なために手書きのループよりはるかに優れていて、またバグのないコードを記述しやすくしてくれます。付け加えて、多くのC++標準ライブラリにはより効率的な実装が最適化されたアルゴリズムがあります。

次のような従来型のC++の代わりに、

```cpp
for ( auto i = strings.begin(); i != strings.end(); ++i ) {
    /* ... */
}

auto i = v.begin();

for ( ; i != v.end(); ++i ) {
    if (*i > x && *i < y) break;
}
```

次のような現代的なC++を使用してください。

```cpp
for_each( begin(strings), end(strings), [](string& s) {
  // ...
} );

auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; } );
```

### <a name="range-based-for-loops"></a>範囲ベースの for ループ

範囲ベースの **for** ループは、C++11の言語機能で、C++標準ライブラリのアルゴリズムではありません。しかし、ループに関するこの説明の中で言及するに値します。 範囲ベースの **for** ループは **for** キーワードの拡張で、値の範囲を反復処理するループを記述する便利で効率的な方法を提供します。C++標準ライブラリのコンテナ、文字列、および配列は範囲ベースの **for** ループに予め対応するように作られています。この新しい反復処理の構文をユーザー定義型に対して適用可能にするには、次の対応を追加します。

- 反復子を構造体の先頭に返す `begin` メソッドと、反復子を構造体の末尾に返す `end` メソッド。

- これらのメソッドの反復子のサポート: <strong>\*</strong>**演算子**、**!=演算子**、および **前置++演算子**。

これらのメソッドは、メンバー関数かスタンドアロン関数のいずれかになれます。

## <a name="random-numbers"></a>乱数

従来のCRTの `rand()` 関数に多くの欠陥があることは広く知られた事実であり、C++コミュニティで長年にわたって議論されてきました。 現代的なC++では、これらの欠陥に対処する必要はありませんし、独自に一様分布する乱数発生器を作成する必要もありません、なぜなら [\<random>](../standard-library/random.md) で示されているように、迅速かつ簡単にそれらを作成するためのツールがC++標準ライブラリから使用可能なためです。

## <a name="see-also"></a>関連項目

[C++ へようこそ (現代的なC++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++言語リファレンス](../cpp/cpp-language-reference.md)<br/>
[C++標準ライブラリ](../standard-library/cpp-standard-library-reference.md)<br/>
