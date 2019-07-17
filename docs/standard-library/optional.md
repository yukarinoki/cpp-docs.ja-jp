---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: c73ad2ad94a5de29bc2c457fdf6ca8b9c783615c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268484"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

省略可能なコンテナーのテンプレート クラスといくつかのサポート用テンプレートを定義します。

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
> リレーショナルの比較だけでなく\<省略可能 > 演算子との比較をサポートしても**nullopt**と`T`します。

### <a name="functions"></a>関数

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|オブジェクトは、省略可能。|
|[swap](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>クラスと構造体

|||
|-|-|
|[hash]()||
|[省略可能なクラス](../standard-library/optional-class.md)|値を保持しない場合がありますまたは可能性のあるオブジェクトについて説明します。|
|[nullopt_t 構造体](../standard-library/nullopt-t-structure.md)|いない値を保持するオブジェクトについて説明します。|
|[bad_optional_access クラス](../standard-library/bad-optional-access-class.md)|存在しない値にアクセスしようとすると、レポートに例外としてスロー オブジェクトについて説明します。|

### <a name="objects"></a>オブジェクト

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
