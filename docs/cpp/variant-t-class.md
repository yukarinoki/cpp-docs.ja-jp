---
title: _variant_t クラス
ms.date: 11/04/2016
f1_keywords:
- _variant_t
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
ms.openlocfilehash: 3873452afca0159cba815a2cb290ebb6e62aff07
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842560"
---
# <a name="_variant_t-class"></a>_variant_t クラス

**Microsoft 固有の仕様**

**_Variant_t**オブジェクトは、データ型をカプセル化し `VARIANT` ます。 クラスは、リソースの割り当てと割り当て解除を管理し、必要に応じてとの関数呼び出しを行い `VariantInit` `VariantClear` ます。

### <a name="construction"></a>建設

| 名前 | 説明 |
|--|--|
| [_variant_t](../cpp/variant-t-variant-t.md) | **_Variant_t**オブジェクトを構築します。 |

### <a name="operations"></a>操作

| 名前 | 説明 |
|--|--|
| [[アタッチ]](../cpp/variant-t-attach.md) | オブジェクトを `VARIANT` **_variant_t** オブジェクトにアタッチします。 |
| [Clear](../cpp/variant-t-clear.md) | カプセル化されたオブジェクトをクリア `VARIANT` します。 |
| [ChangeType](../cpp/variant-t-changetype.md) | **_Variant_t**オブジェクトの型を、指定されたに変更 `VARTYPE` します。 |
| [[デタッチ]](../cpp/variant-t-detach.md) | `VARIANT`この **_variant_t**オブジェクトから、カプセル化されたオブジェクトをデタッチします。 |
| [SetString](../cpp/variant-t-setstring.md) | この **_variant_t** オブジェクトに文字列を割り当てます。 |

### <a name="operators"></a>演算子

| 名前 | 説明 |
|--|--|
| [Operator =](../cpp/variant-t-operator-equal.md) | 既存の **_variant_t** オブジェクトに新しい値を割り当てます。 |
| [operator = =、! =](../cpp/variant-t-relational-operators.md) | 2つの **_variant_t** オブジェクトが等しいかどうかを比較します。 |
| [抽出](../cpp/variant-t-extractors.md) | カプセル化されたオブジェクトからデータを抽出 `VARIANT` します。 |

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>必要条件

**ヘッダー:**\<comutil.h>

**Lib:** comsuppw または comsuppw (詳細について [は、「/zc: Wchar_t (wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>関連項目

[コンパイラ COM サポートクラス](../cpp/compiler-com-support-classes.md)
