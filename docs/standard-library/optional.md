---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: 83a0ad52735f92d731dafb32ad1be5a8278776b4
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447180"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

コンテナーテンプレートクラスオプションと複数のサポートテンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<オプション >

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトと等しいかどうかを調べます。|
|[operator!=](../standard-library/optional-operators.md#op_neq)|演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトと等しくないかどうかを調べます。|
|[operator<](../standard-library/optional-operators.md#op_lt)|演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトより小さいかどうかを調べます。|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|演算子の左側の `optional` オブジェクトが右側の  `optional` オブジェクト以下かどうかを調べます。|
|[operator>](../standard-library/optional-operators.md#op_gt)|演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクトより大きいかどうかを調べます。|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|演算子の左側の `optional` オブジェクトが右側の `optional` オブジェクト以上であるかどうかを調べます。|

> [!NOTE]
> 関係比較に加えて、 \<オプションの > 演算子は**nullopt**と`T`の比較もサポートします。

### <a name="functions"></a>関数

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|オブジェクトを省略可能にします。|
|[swap](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>クラスと構造体

|||
|-|-|
|[hash]()||
|[省略可能なクラス](../standard-library/optional-class.md)|値を保持できるか、または保持できないオブジェクトを表します。|
|[nullopt_t 構造体](../standard-library/nullopt-t-structure.md)|値を保持しないオブジェクトを記述します。|
|[bad_optional_access クラス](../standard-library/bad-optional-access-class.md)|存在しない値にアクセスしようとしたことを報告する例外としてスローされるオブジェクトを表します。|

### <a name="objects"></a>オブジェクト

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
