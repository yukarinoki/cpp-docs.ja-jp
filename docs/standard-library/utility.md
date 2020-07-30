---
title: '&lt;utility&gt;'
ms.date: 11/04/2016
f1_keywords:
- <utility>
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
ms.openlocfilehash: 1beade28ceec0f1552def4bc70c2e95e6b2aa24d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215440"
---
# <a name="ltutilitygt"></a>&lt;utility&gt;

C++ 標準ライブラリの型、関数、および演算子を定義し、オブジェクトのペアを作成し管理するのに役立てます。これらは 2 つのオブジェクトをあたかも 1 つのように扱う必要がある場合に役立ちます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<utility>

**名前空間:** std

## <a name="remarks"></a>解説

ペアは、C++ 標準ライブラリで広く使用されます。 これはさまざまな関数の引数と戻り値として、また [map クラス](../standard-library/map-class.md)と [multimap クラス](../standard-library/multimap-class.md)などのコンテナーの要素型として必要です。 \<utility>ヘッダーは、 \<map> キー/値ペアの型の要素の管理を支援するために、によって自動的に追加されます。

> [!NOTE]
> ヘッダーでは、 \<utility> ステートメントを使用し `#include <initializer_list>` ます。 また、「 `class tuple` 」で定義されているを参照し \<tuple> ます。

## <a name="members"></a>メンバー

### <a name="classes"></a>クラス

|Type|[説明]|
|-|-|
|[chars_format](../standard-library/chars-format-class.md)|プリミティブ数値変換の浮動小数点形式。|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|`pair` 要素の型をラップするクラスです。|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|`pair` 要素の数をラップするクラスです。|

### <a name="objects"></a>Objects

|Template|説明|
|-|-|
|[index_sequence](../standard-library/utility-functions.md#index_sequence)|共通のケースに対して定義されているエイリアステンプレート ( `T` is)`std::size_t`  |
|[index_sequence_for](../standard-library/utility-functions.md#index_sequence_for)|任意の型パラメーターパックを同じ長さのインデックスシーケンスに変換するヘルパーエイリアステンプレート|
|[make_index_sequence](../standard-library/utility-functions.md#make_index_sequence)| 型の作成を簡略化するヘルパーエイリアステンプレート `std::index_sequence` 。 |
|[make_integer_sequence](../standard-library/utility-functions.md#make_integer_sequence)|型の作成を簡略化するヘルパーエイリアステンプレート `std::integer_sequence` 。|

### <a name="functions"></a>関数

|機能|説明|
|-|-|
|[as_const](../standard-library/utility-functions.md#asconst)|型を返します。|
|[declval](../standard-library/utility-functions.md#declval)|省略形の式の評価。|
|[エクスチェンジ](../standard-library/utility-functions.md#exchange)|オブジェクトに新しい値を割り当て、その古い値を返します。|
|[推進](../standard-library/utility-functions.md#forward)|引数の参照型 (`lvalue` または `rvalue` のどちらか) が完全転送によって隠されないよう保ちます。|
|[from_chars](../standard-library/utility-functions.md#from_chars)||
|[get](../standard-library/utility-functions.md#get)|`pair` オブジェクトから要素を取得する関数です。|
|[make_pair](../standard-library/utility-functions.md#make_pair)|`pair` 型のオブジェクトを作成するために使用されるテンプレート ヘルパー関数。コンポーネントの型は、パラメーターとして渡されるデータ型に基づいています。|
|[move](../standard-library/utility-functions.md#move)|`rvalue` 参照として引数で渡されたものを返します。|
|[move_if_noexcept](../standard-library/utility-functions.md#moveif)||
|[スワップ](../standard-library/utility-functions.md#swap)|2 つの `pair` オブジェクトの要素を交換します。|
|[to_chars](../standard-library/utility-functions.md#to_chars)|値を文字列に変換します。|

### <a name="operators"></a>オペレーター

|演算子|Description|
|-|-|
|[operator! =](../standard-library/utility-operators.md#op_neq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しくないかどうかを調べます。|
|[operator = =](../standard-library/utility-operators.md#op_eq_eq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しいかどうかを調べます。|
|[operator\<](../standard-library/utility-operators.md#op_lt)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより小さいかどうかを調べます。|
|[operator\<=](../standard-library/utility-operators.md#op_gt_eq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以下かどうかを調べます。|
|[>演算子](../standard-library/utility-operators.md#op_gt)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以上かどうかを調べます。|

### <a name="structs"></a>構造体

|構造体|説明|
|-|-|
|[from_chars_result](../standard-library/from-chars-result-structure.md)|に使用される構造体 `from_chars` 。|
|[identity](../standard-library/identity-structure.md)|テンプレート パラメーターの型定義を指定する構造体。|
|[in_place_t](../standard-library/in-place-t-struct.md)|には、構造体とも含まれ `in_place_type_t` `in_place_index_t` ます。|
|[integer_sequence](../standard-library/integer-sequence-class.md)|整数のシーケンスを表します。|
|[二重](../standard-library/pair-structure.md)|2 つのオブジェクトを 1 つのオブジェクトとして処理する機能を提供する型。|
|[piecewise_construct_t](../standard-library/piecewise-construct-t-structure.md)|個別のコンストラクターと関数のオーバーロードを維持するために使用される型。|
|[to_chars_result](../standard-library/to-chars-result-structure.md)|に使用される構造体 `to_chars` 。|

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
