---
description: '詳細情報: &lt; numeric&gt;'
title: '&lt;numeric&gt;'
ms.date: 11/04/2016
f1_keywords:
- <numeric>
helpviewer_keywords:
- <numeric> header
ms.assetid: 6d6ccb94-48cc-479b-b4a9-bd9c78d4896a
ms.openlocfilehash: 5ff2a0ff2b765afbb60d117745976ad3919dd18f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338045"
---
# <a name="ltnumericgt"></a>&lt;numeric&gt;

数値処理のアルゴリズムを実行するコンテナーのテンプレート関数を定義します。

## <a name="requirements"></a>要件

**ヘッダー**: \<numeric>

**名前空間:** std

## <a name="remarks"></a>解説

数値アルゴリズムは、の C++ 標準ライブラリアルゴリズムに似 [\<algorithm>](algorithm.md) ており、さまざまなデータ構造を操作できます。 これには、標準ライブラリ コンテナー クラス ([vector](../standard-library/vector-class.md) や [list](../standard-library/list-class.md) など) と、特定のアルゴリズムの要件を満たすプログラム定義のデータ構造体と要素の配列が含まれます。 アルゴリズムは、反復子によって間接的にコンテナー要素にアクセスし、走査することによって、このレベルの一般性を実現します。 アルゴリズムは、通常、開始位置または終了位置によって指定される反復子範囲を処理します。 参照される範囲は、範囲内のすべてのポインターが逆参照可能であるという意味において有効であり、かつ各範囲のシーケンス内で先頭位置からのインクリメントにより最後の位置に到達可能である必要があります。

アルゴリズムでは、各 C++ 標準ライブラリ コンテナーの操作およびメンバー関数でサポートされている操作を拡張し、異なる型のコンテナー オブジェクトを同時に操作できるようにします。

## <a name="members"></a>メンバー

### <a name="functions"></a>機能

|名前|説明|
|-|-|
|[accumulate](../standard-library/numeric-functions.md#accumulate)|連続する部分和を計算することで、初期値を含め、指定された範囲のすべての要素の合計を計算します。または、合計演算の代わりに、指定された二項演算を使用して取得された連続する部分的な結果を計算します。|
|[adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)|入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|
|[exclusive_scan](../standard-library/numeric-functions.md#exclusive_scan)||
|[gcd](../standard-library/numeric-functions.md#gcd)||
|[inclusive_scan](../standard-library/numeric-functions.md#inclusive_scan)||
|[inner_product](../standard-library/numeric-functions.md#inner_product)|2 つの範囲の要素ごとの積の合計を計算し、それを指定された初期値に加算するか、または和や積の演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|
|[イオータ](../standard-library/numeric-functions.md#iota)|開始値を格納し、最初の要素から始めて、一連の値のインクリメント (`value++`) を `[first, last)` の間隔で各要素に入力します。|
|[lcm](../standard-library/numeric-functions.md#lcm)||
|[partial_sum](../standard-library/numeric-functions.md#partial_sum)|入力範囲の最初の要素から *i* 番目の要素までの一連の合計を計算し、各合計の結果をターゲット範囲の *i* 番目の要素に格納するか、または合計演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。|
|[落とし](../standard-library/numeric-functions.md#reduce)||
|[transform_exclusive_scan](../standard-library/numeric-functions.md#transform_exclusive_scan)||
|[transform_inclusive_scan](../standard-library/numeric-functions.md#transform_inclusive_scan)||
|[transform_reduce](../standard-library/numeric-functions.md#transform_reduce)||

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
