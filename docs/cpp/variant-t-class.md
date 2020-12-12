---
description: '詳細情報: _variant_t クラス'
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
ms.openlocfilehash: e720d78e6f7fd22fc369d4b39804260892e235c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116614"
---
# <a name="_variant_t-class"></a>_variant_t クラス

**Microsoft 固有の仕様**

**_Variant_t** オブジェクトは、データ型をカプセル化し `VARIANT` ます。 クラスは、リソースの割り当てと割り当て解除を管理し、必要に応じてとの関数呼び出しを行い `VariantInit` `VariantClear` ます。

### <a name="construction"></a>建設

| 名前 | 説明 |
|--|--|
| [_variant_t](../cpp/variant-t-variant-t.md) | **_Variant_t** オブジェクトを構築します。 |

### <a name="operations"></a>操作

| 名前 | 説明 |
|--|--|
| [[アタッチ]](../cpp/variant-t-attach.md) | オブジェクトを `VARIANT` **_variant_t** オブジェクトにアタッチします。 |
| [Clear](../cpp/variant-t-clear.md) | カプセル化されたオブジェクトをクリア `VARIANT` します。 |
| [ChangeType](../cpp/variant-t-changetype.md) | **_Variant_t** オブジェクトの型を、指定されたに変更 `VARTYPE` します。 |
| [[デタッチ]](../cpp/variant-t-detach.md) | `VARIANT`この **_variant_t** オブジェクトから、カプセル化されたオブジェクトをデタッチします。 |
| [SetString](../cpp/variant-t-setstring.md) | この **_variant_t** オブジェクトに文字列を割り当てます。 |

### <a name="operators"></a>オペレーター

| 名前 | 説明 |
|--|--|
| [Operator =](../cpp/variant-t-operator-equal.md) | 既存の **_variant_t** オブジェクトに新しい値を割り当てます。 |
| [operator = =、! =](../cpp/variant-t-relational-operators.md) | 2つの **_variant_t** オブジェクトが等しいかどうかを比較します。 |
| [抽出](../cpp/variant-t-extractors.md) | カプセル化されたオブジェクトからデータを抽出 `VARIANT` します。 |

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>要件

**ヘッダー:**\<comutil.h>

**Lib:** comsuppw または comsuppw (詳細について [は、「/zc: Wchar_t (wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>関連項目

[コンパイラ COM サポートクラス](../cpp/compiler-com-support-classes.md)
