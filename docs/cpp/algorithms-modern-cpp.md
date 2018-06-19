---
title: アルゴリズム (Modern C) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fdd5742bb86992ce20f5a52f587c8557d46a97eb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412297"
---
# <a name="algorithms-modern-c"></a>アルゴリズム (Modern C++)
最新の C++ プログラミングのことをお勧め内のアルゴリズムを使用すること、 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)です。 次に重要な例を示します。  
  
-   既定の走査アルゴリズムである `for_each`  (また、not-in-place セマンティクスの `transform`)。  
  
-   既定の検索アルゴリズムである `find_if`。  
  
-   `sort`、`lower_bound`、およびその他の既定の並べ替えアルゴリズムや検索アルゴリズム。  
  
 厳密なを使用して記述するには、比較器`<`を使用して*名前付きラムダ*することができます。  
  
```cpp  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
```  
  
## <a name="loops"></a>ループ  
 可能であれば、使用範囲ベースの`for`ループまたはアルゴリズム呼び出し、あるいはその両方ではなく手動で記述したループ`copy`、 `transform`、 `count_if`、 `remove_if`、し、それらのような他のユーザーが手動で記述したループよりはるかに優れているためそれらの意図明らかでは容易になるバグのないコードを記述するとします。 また、多くの C++ 標準ライブラリ アルゴリズムより効率的にする実装の最適化があります。  
  
 次のような従来の C++ を使用する代わりに、  
  
```cpp  
for ( auto i = strings.begin(); i != strings.end(); ++i ) {  
   /* ... */  
}  
  
auto i = v.begin();  
  
for ( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
```  
  
 次のような最新の C++ を使用してください。  
  
```cpp  
for_each( begin(strings), end(strings), [](string& s) {  
   // ...  
} );  
  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; } );  
```  
  
### <a name="range-based-for-loops"></a>範囲ベースの for ループ  
 範囲に基づく`for`ループは c++ 11 言語の機能、C++ 標準ライブラリ アルゴリズムではありません。 しかし、ループに関するこの説明と併せて理解すると便利です。 範囲ベースの `for` ループは、`for` キーワードの拡張機能であり、値の範囲にわたって処理を反復するループを効率的に作成できます。 C++ 標準ライブラリのコンテナー、文字列、および配列は既製の範囲に基づく`for`ループします。 この新しいイテレーション構文をユーザー定義型に対して有効にするには、次のサポートを追加します。  
  
-   反復子を構造体の先頭に返す `begin` メソッドと、反復子を構造体の末尾に返す `end` メソッド。  
  
-   反復子での `operator*`、`operator!=`、および `operator++` (前置バージョン) の各メソッドのサポート。  
  
 これらのメソッドは、メンバー関数かスタンドアロン関数のいずれかです。  
  
## <a name="random-numbers"></a>乱数  
 従来の CRT の `rand()` 関数に多くの欠陥があることは広く知られた事実であり、C++ コミュニティで長年にわたって議論されてきました。 最新の C++ でのそれらの欠点に対処する必要はありません- したり、独自一様に分布した乱数ジェネレーターを作成する —に示すとおり、迅速かつ簡単に作成するためのツールは、C++標準ライブラリで利用可能なため[\<ランダム >](../standard-library/random.md)です。  
  
## <a name="see-also"></a>関連項目  
 [C++ へようこそ](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 言語リファレンス](../cpp/cpp-language-reference.md)   
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)