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
ms.openlocfilehash: 9737db6b77483fa55e1dad90b9464752cd8537a5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187740"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft 固有の仕様**

この `_variant_t` オブジェクトから、カプセル化された `VARIANT` オブジェクトをデタッチします。

## <a name="syntax"></a>構文

```
VARIANT Detach( );
```

## <a name="return-value"></a>戻り値

カプセル化された `VARIANT`。

## <a name="remarks"></a>解説

カプセル化された `VARIANT`を抽出して返し、この `_variant_t` オブジェクトを破棄せずにクリアします。 このメンバー関数は、カプセル化から `VARIANT` を削除し、この `_variant_t` オブジェクトの `VARTYPE` を VT_EMPTY に設定します。 返された `VARIANT` は、 [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)関数を呼び出すことによって解放できます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
