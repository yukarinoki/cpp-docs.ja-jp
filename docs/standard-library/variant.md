---
description: '詳細情報: &lt; バリアント&gt;'
title: '&lt;variant&gt;'
ms.date: 04/04/2019
f1_keywords:
- <variant>
helpviewer_keywords:
- <variant>
ms.openlocfilehash: 994bd18a66dd78c8f6042afea10df69ff08a1487
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312472"
---
# <a name="ltvariantgt"></a>&lt;variant&gt;

バリアントオブジェクトは、値を保持して管理します。 バリアントが値を保持している場合、その値の型は variant に指定されたテンプレート引数の型のいずれかである必要があります。 これらのテンプレート引数は、代替と呼ばれます。

## <a name="requirements"></a>要件

**ヘッダー:**\<variant>

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="operators"></a>オペレーター

|名前|説明|
|-|-|
|[operator = =](../standard-library/forward-list-operators.md#op_eq_eq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトと等しいかどうかをテストします。|
|[operator! =](../standard-library/forward-list-operators.md#op_neq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトと等しくないかどうかをテストします。|
|[<演算子 ](../standard-library/forward-list-operators.md#op_lt)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトより小さいかどうかをテストします。|
|[operator<=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクト以下かどうかをテストしますです。|
|[>演算子 ](../standard-library/forward-list-operators.md#op_gt)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/forward-list-operators.md#op_lt_eq)|演算子の左辺のバリアントオブジェクトが右辺のバリアントオブジェクト以上かどうかをテストしますです。|

### <a name="functions"></a>関数

|名前|説明|
|-|-|
|[get](../standard-library/variant-functions.md#get)|オブジェクトのバリアントを取得します。|
|[get_if](../standard-library/variant-functions.md#get_if)|オブジェクトが存在する場合は、そのバリアントを取得します。|
|[holds_alternative](../standard-library/variant-functions.md#holds_alternative)|**`true`** バリアントが存在する場合は、を返します。|
|[スワップ](../standard-library/variant-functions.md#swap)|**バリアント** を交換します。|
|[ごと](../standard-library/variant-functions.md#visit)|次の **バリアント** に移動します。|

### <a name="classes"></a>クラス

|名前|説明|
|-|-|
|[bad_variant_access](../standard-library/bad-variant-access-class.md)|Variant オブジェクトの値への無効なアクセスを報告するためにスローされるオブジェクト。|
|[variant](../standard-library/variant.md)|別の型のいずれかの値を保持するか、値を持たないオブジェクト。|

### <a name="structs"></a>構造体

|名前|説明|
|-|-|
|[hash](../standard-library/hash-structure.md)||
|[モノの状態](../standard-library/monostate-structure.md)|バリアント型を既定として構築できるようにするバリアントの代替型。|
|[uses_allocator](../standard-library/uses-allocator-structure.md)||
|[variant_alternative](../standard-library/variant-alternative-structure.md)|Variant オブジェクトを支援します。|
|[variant_size](../standard-library/variant-size-structure.md)|Variant オブジェクトを支援します。|

### <a name="objects"></a>Objects

|名前|説明|
|-|-|
|[variant_npos](../standard-library/variant-functions.md#variant_npos)||

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
