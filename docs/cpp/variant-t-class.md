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
ms.openlocfilehash: e11d31904fd8e54049f69ee4f6530d511c8c7f4e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187753"
---
# <a name="_variant_t-class"></a>_variant_t クラス

**Microsoft 固有の仕様**

**_Variant_t**オブジェクトは、`VARIANT` データ型をカプセル化します。 クラスは、リソースの割り当てと割り当て解除を管理し、必要に応じて `VariantInit` および `VariantClear` の関数呼び出しを行います。

### <a name="construction"></a>構築

|||
|-|-|
|[_variant_t](../cpp/variant-t-variant-t.md)|**_Variant_t**オブジェクトを構築します。|

### <a name="operations"></a>操作

|||
|-|-|
|[[アタッチ]](../cpp/variant-t-attach.md)|`VARIANT` オブジェクトを **_variant_t**オブジェクトにアタッチします。|
|[Clear](../cpp/variant-t-clear.md)|カプセル化された `VARIANT` オブジェクトをクリアします。|
|[ChangeType](../cpp/variant-t-changetype.md)|**_Variant_t**オブジェクトの型を、指定した `VARTYPE`に変更します。|
|[[デタッチ]](../cpp/variant-t-detach.md)|この **_variant_t**オブジェクトから、カプセル化された `VARIANT` オブジェクトをデタッチします。|
|[SetString](../cpp/variant-t-setstring.md)|この **_variant_t**オブジェクトに文字列を割り当てます。|

### <a name="operators"></a>オペレーター

|||
|-|-|
|[Operator =](../cpp/variant-t-operator-equal.md)|既存の **_variant_t**オブジェクトに新しい値を割り当てます。|
|[operator = =、! =](../cpp/variant-t-relational-operators.md)|2つの **_variant_t**オブジェクトが等しいかどうかを比較します。|
|[器](../cpp/variant-t-extractors.md)|カプセル化された `VARIANT` オブジェクトからデータを抽出します。|

**Microsoft 固有の仕様はここまで**

## <a name="requirements"></a>必要条件

**ヘッダー:** \<comutil. h >

**Lib:** comsuppw または comsuppw (詳細について[は、「/zc: Wchar_t (wchar_t ネイティブ型)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 」を参照してください)

## <a name="see-also"></a>参照

[コンパイラ COM サポート クラス](../cpp/compiler-com-support-classes.md)
