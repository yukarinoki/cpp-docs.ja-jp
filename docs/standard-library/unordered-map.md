---
title: '&lt;unordered_map&gt;'
description: C++ 標準ライブラリコンテナークラスの API 概要 `map` 。
ms.date: 11/04/2016
f1_keywords:
- <unordered_map>
helpviewer_keywords:
- unordered_map header
ms.assetid: eb90ecb2-250a-4be1-83d2-f66b2917edde
ms.openlocfilehash: 6a25b69155f5428a7269ea35f104f30df0b61877
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042146"
---
# <a name="ltunordered_mapgt"></a>&lt;unordered_map&gt;

コンテナークラステンプレート [unordered_map](../standard-library/unordered-map-class.md) と [unordered_multimap](../standard-library/unordered-multimap-class.md) と、そのサポートテンプレートを定義します。

## <a name="syntax"></a>構文

```cpp
#include <unordered_map>
```

> [!NOTE]
> ライブラリは、 \<unordered_map> ステートメントも使用し `#include <initializer_list>` ます。

### <a name="classes"></a>クラス

|クラス|説明|
|-|-|
|[unordered_map クラス](../standard-library/unordered-map-class.md)|{key, mapped} のペアのハッシュ テーブルを格納します。|
|[unordered_multimap クラス](../standard-library/unordered-multimap-class.md)|{key, mapped} のペアのハッシュ テーブルを格納します。|

### <a name="functions"></a>関数

|機能|説明|
|-|-|
|[operator! =](../standard-library/unordered-map-operators.md#op_neq)|演算子の左側の unordered_map オブジェクトが右側の unordered_map オブジェクトと等しくないかどうかをテストします。|
|[operator = =](../standard-library/unordered-map-operators.md#op_eq_eq)|演算子の左側の unordered_map オブジェクトが右側の unordered_map オブジェクトと等しいかどうかをテストします。|
|[swap 関数 (unordered_map)](../standard-library/unordered-map-functions.md#swap)|2 つのマップを入れ替えます。|
|[operator! =](../standard-library/unordered-map-operators.md#op_neq)|演算子の左側の unordered_multimap オブジェクトが右側の unordered_multimap オブジェクトと等しくないかどうかをテストします。|
|[operator = =](../standard-library/unordered-map-operators.md#op_eq_eq)|演算子の左側の unordered_multimap オブジェクトが右側の unordered_multimap オブジェクトと等しいかどうかをテストします。|
|[swap 関数 (unordered_map)](../standard-library/unordered-map-functions.md#swap)|2 つの multimap を入れ替えます。|

## <a name="see-also"></a>参照

[unordered_multiset クラス](../standard-library/unordered-multiset-class.md)\
[unordered_set クラス](../standard-library/unordered-set-class.md)
