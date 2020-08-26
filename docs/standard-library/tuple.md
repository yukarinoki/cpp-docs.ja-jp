---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: b1eeba2fced21f5a38799db7fc4af259e03bc266
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841845"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

さまざまな型のオブジェクトを保持するインスタンスを持つテンプレート `tuple` を定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<tuple>

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="classes-and-structs"></a>クラスと構造体

|名前|説明|
|-|-|
|[tuple クラス](../standard-library/tuple-class.md)|要素の固定長シーケンスをラップします。|
|[tuple_element クラス](../standard-library/tuple-element-class-tuple.md)|`tuple` 要素の型をラップします。|
|[tuple_size クラス](../standard-library/tuple-size-class-tuple.md)|`tuple` の要素数をラップします。|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||

### <a name="objects"></a>オブジェクト

|名前|説明|
|-|-|
|[tuple_element_t](../standard-library/tuple-functions.md#tuple_element_t)||
|[tuple_size_v](../standard-library/tuple-functions.md#tuple_size_v)||

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator = =](../standard-library/tuple-operators.md#op_eq_eq)|オブジェクトの比較 `tuple` (等しい)。|
|[operator! =](../standard-library/tuple-operators.md#op_neq)|オブジェクトの比較 `tuple` (等しくない)。|
|[<演算子 ](../standard-library/tuple-operators.md#op_lt)|オブジェクトの比較 `tuple` (より小さい)。|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|オブジェクトの比較 `tuple` (以下)。|
|[>演算子 ](../standard-library/tuple-operators.md#op_gt)|オブジェクトの比較 `tuple` (より大きい)。|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|オブジェクトの比較 `tuple` (以上)。|

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[付ける](../standard-library/tuple-functions.md#apply)|タプルを使用して関数を呼び出します。|
|[forward_as_tuple](../standard-library/tuple-functions.md#forward)|参照のタプルを構築します。|
|[get](../standard-library/tuple-functions.md#get)|`tuple` オブジェクトから要素を取得します。|
|[make_from_tuple](../standard-library/tuple-functions.md#make_from_tuple)|を作成するための短縮形 `tuple` 。|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|要素値から `tuple` を作成します。|
|[スワップ](../standard-library/tuple-functions.md#swap)||
|[tie](../standard-library/tuple-functions.md#tie)|要素参照から `tuple` を作成します。|
|[tuple_cat](../standard-library/tuple-functions.md#tuple_cat)|型要素の範囲を持つ組オブジェクトを構築します。|

## <a name="see-also"></a>関連項目

[\<array>](../standard-library/array.md)
