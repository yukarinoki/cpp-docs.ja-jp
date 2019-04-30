---
title: '&lt;数値&gt;'
ms.date: 11/04/2016
f1_keywords:
- <numeric>
helpviewer_keywords:
- <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
ms.openlocfilehash: ee93d254dcf49b38cb817ba460060fa72b81e01f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371456"
---
# <a name="ltnumericgt"></a>&lt;数値&gt;

数値処理のアルゴリズムを実行するコンテナーのテンプレート関数を定義します。

## <a name="syntax"></a>構文

```cpp
#include <numeric>
```

## <a name="remarks"></a>Remarks

この数値処理のアルゴリズムは　C++ 標準ライブラリの [\<algorithm>](algorithm.md) のアルゴリズムと似ており、さまざまなデータ構造体で操作できます。 これには、標準ライブラリ コンテナー クラス ([vector](../standard-library/vector-class.md) や [list](../standard-library/list-class.md) など) と、特定のアルゴリズムの要件を満たすプログラム定義のデータ構造体と要素の配列が含まれます。 アルゴリズムは、反復子によって間接的にコンテナー要素にアクセスし、走査することによって、このレベルの一般性を実現します。 アルゴリズムは、通常、開始位置または終了位置によって指定される反復子範囲を処理します。 参照される範囲は、範囲内のすべてのポインターが逆参照可能であるという意味において有効であり、かつ各範囲のシーケンス内で先頭位置からのインクリメントにより最後の位置に到達可能である必要があります。

アルゴリズムでは、各 C++ 標準ライブラリ コンテナーの操作およびメンバー関数でサポートされている操作を拡張し、異なる型のコンテナー オブジェクトを同時に操作できるようにします。

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[accumulate](../standard-library/numeric-functions.md#accumulate)|連続する部分和を計算することで、初期値を含め、指定された範囲のすべての要素の合計を計算します。または、合計演算の代わりに、指定された二項演算を使用して取得された連続する部分的な結果を計算します。|
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|
|[inner_product](../standard-library/numeric-functions.md#inner_product)|2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|
|[iota](../standard-library/numeric-functions.md#iota)|開始値を格納し、最初の要素から始めて、一連の値のインクリメント (`value++`) を `[first, last)` の間隔で各要素に入力します。|
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|入力範囲の最初の要素から *i* 番目の要素までの一連の合計を計算し、各合計の結果をターゲット範囲の *i* 番目の要素に格納するか、または合計演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)<br/>
