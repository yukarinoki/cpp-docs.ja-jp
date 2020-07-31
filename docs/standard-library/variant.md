---
title: '&lt;variant&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 6074c80b20ae0c69d34768bc16d7aaae16c99579
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232821"
---
# <a name="ltvariantgt"></a>&lt;variant&gt;

バリアントオブジェクトは、値を保持して管理します。 バリアントが値を保持している場合、その値の型は variant に指定されたテンプレート引数の型のいずれかである必要があります。 これらのテンプレート引数は、代替と呼ばれます。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<variant>

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="operators"></a>オペレーター

|||
|-|-|
|[operator = =](../standard-library/forward-list-operators.md#op_eq_eq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトと等しいかどうかをテストします。|
|[operator! =](../standard-library/forward-list-operators.md#op_neq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトと等しくないかどうかをテストします。|
|[<演算子](../standard-library/forward-list-operators.md#op_lt)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトより小さいかどうかをテストします。|
|[operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクト以下かどうかをテストしますです。|
|[>演算子](../standard-library/forward-list-operators.md#op_gt)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクト以上かどうかをテストしますです。|

### <a name="functions"></a>関数

|||
|-|-|
|[get](../standard-library/variant-functions.md#get)|オブジェクトのバリアントを取得します。|
|[get_if](../standard-library/variant-functions.md#get_if)|オブジェクトが存在する場合は、そのバリアントを取得します。|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|**`true`** バリアントが存在する場合は、を返します。|
|[スワップ](../standard-library/variant-functions.md#swap)|**バリアント**を交換します。|
|[ごと](../standard-library/variant-functions.md#visit)|次の**バリアント**に移動します。|

### <a name="classes"></a>クラス

|||
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Variant オブジェクトの値への無効なアクセスを報告するためにスローされるオブジェクト。|
|[variant](../standard-library/variant.md)|別の型のいずれかの値を保持するか、値を持たないオブジェクト。|

### <a name="structs"></a>構造体

|||
|-|-|
|[hash](../standard-library/hash-structure.md)||
|[モノの状態](../standard-library/monostate-structure.md)|バリアント型を既定として構築できるようにするバリアントの代替型。|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Variant オブジェクトを支援します。|
|[variant_size](../standard-library/variant-size-structure.md)|Variant オブジェクトを支援します。|

### <a name="objects"></a>Objects

|||
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
