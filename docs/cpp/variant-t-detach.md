---
title: _variant_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
ms.openlocfilehash: 719852c4556291747b612d54c44d4bf82caa9188
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519007"
---
# <a name="varianttdetach"></a>_variant_t::Detach

**Microsoft 固有の仕様**

カプセル化されたデタッチ`VARIANT`オブジェクトからこの`_variant_t`オブジェクト。

## <a name="syntax"></a>構文

```
VARIANT Detach( );
```

## <a name="return-value"></a>戻り値

カプセル化された`VARIANT`します。

## <a name="remarks"></a>Remarks

抽出し、カプセル化された返します`VARIANT`、これをクリア`_variant_t`オブジェクトを破棄します。 このメンバー関数を削除、`VARIANT`カプセル化し、セットから、`VARTYPE`この`_variant_t`VT_EMPTY するオブジェクト。 返されたを解放するかどうかは`VARIANT`呼び出すことによって、 [VariantClear](/windows/desktop/api/oleauto/nf-oleauto-variantclear)関数。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)