---
title: '&lt;tuple&gt;'
ms.date: 11/04/2016
f1_keywords:
- <tuple>
helpviewer_keywords:
- tuple header
ms.assetid: e4ef5c2d-318b-44f6-8bce-fce4ecd796a3
ms.openlocfilehash: 2e46b3997096c6e61f7dd6140131e3f10223b8e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399422"
---
# <a name="lttuplegt"></a>&lt;tuple&gt;

さまざまな型のオブジェクトを保持するインスタンスを持つテンプレート `tuple` を定義します。

## <a name="syntax"></a>構文

```cpp
#include <tuple>
```

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[tuple](../standard-library/tuple-class.md)|要素の固定長シーケンスをラップします。|
|[tuple_element クラス](../standard-library/tuple-element-class-tuple.md)|`tuple` 要素の型をラップします。|
|[tuple_size クラス](../standard-library/tuple-size-class-tuple.md)|`tuple` の要素数をラップします。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator==](../standard-library/tuple-operators.md#op_eq_eq)|`tuple` オブジェクトどうしが等しいかどうかの比較|
|[operator!=](../standard-library/tuple-operators.md#op_neq)|`tuple` オブジェクトどうしが等しくないかどうかの比較|
|[operator<](../standard-library/tuple-operators.md#op_lt)|`tuple` オブジェクトどうしの大小関係の比較 (未満)|
|[operator<=](../standard-library/tuple-operators.md#op_lt_eq)|`tuple` オブジェクトどうしの大小関係の比較 (以下)|
|[operator>](../standard-library/tuple-operators.md#op_gt)|`tuple` オブジェクトどうしの大小関係の比較 (より大きい)|
|[operator>=](../standard-library/tuple-operators.md#op_gt_eq)|`tuple` オブジェクトどうしの大小関係の比較 (以上)|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[get](../standard-library/tuple-functions.md#get)|`tuple` オブジェクトから要素を取得します。|
|[make_tuple](../standard-library/tuple-functions.md#make_tuple)|要素値から `tuple` を作成します。|
|[tie](../standard-library/tuple-functions.md#tie)|要素参照から `tuple` を作成します。|

## <a name="see-also"></a>関連項目

[\<array>](../standard-library/array.md)<br/>
