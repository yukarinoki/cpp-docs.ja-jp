---
title: '&lt;省略可能&gt;'
ms.date: 08/06/2019
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.openlocfilehash: 31a3d9aad539e45bb835331a4ef63690d0e16f49
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842677"
---
# <a name="ltoptionalgt"></a>&lt;省略可能&gt;

コンテナークラステンプレート `optional` といくつかのサポートテンプレートを定義します。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<optional>

**名前空間:** std

## <a name="members"></a>メンバー

### <a name="operators"></a>演算子

|名前|説明|
|-|-|
|[operator = =](../standard-library/optional-operators.md#op_eq_eq)|オブジェクトが別のオブジェクトと等しいかどうかをテストします。|
|[operator! =](../standard-library/optional-operators.md#op_neq)|オブジェクトが別のオブジェクトと等しくないかどうかをテストします。|
|[<演算子 ](../standard-library/optional-operators.md#op_lt)|左側のオブジェクトが右側のオブジェクトより小さいかどうかをテストします。|
|[operator<=](../standard-library/optional-operators.md#op_lt_eq)|左側のオブジェクトが右側のオブジェクト以下かどうかをテストします。|
|[>演算子 ](../standard-library/optional-operators.md#op_gt)|左側のオブジェクトが右側のオブジェクトより大きいかどうかをテストします。|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|左側のオブジェクトが右側のオブジェクト以上かどうかをテストします。|

> [!NOTE]
> 関係比較に加えて、 \<optional> 演算子は **nullopt** およびとの比較もサポートして `T` います。

### <a name="functions"></a>Functions

|名前|説明|
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|オブジェクトを省略可能にします。|
|[スワップ](../standard-library/optional-functions.md#swap)|2つのオブジェクトの格納されている値を交換 `optional` します。|

### <a name="classes-and-structs"></a>クラスと構造体

|名前|説明|
|-|-|
|hash|含まれているオブジェクトのハッシュを返します。|
|[optional クラス](../standard-library/optional-class.md)|値を保持できるか、または保持できないオブジェクトを表します。|
|[nullopt_t 構造体](../standard-library/nullopt-t-structure.md)|値を保持しないオブジェクトを記述します。|
|[bad_optional_access クラス](../standard-library/bad-optional-access-class.md)|存在しない値にアクセスしようとしたことを報告する例外としてスローされるオブジェクトを表します。|

### <a name="objects"></a>オブジェクト

|名前|説明|
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)|`nullopt_t`比較のためののインスタンス。|

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
