---
description: '詳細情報: _variant_t::D etach'
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
ms.openlocfilehash: 502903f73f9b149a5f85a6eb1be44687aab20664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97204694"
---
# <a name="_variant_tdetach"></a>_variant_t::Detach

**Microsoft 固有の仕様**

このオブジェクトからカプセル化されたオブジェクトをデタッチし `VARIANT` `_variant_t` ます。

## <a name="syntax"></a>構文

```
VARIANT Detach( );
```

## <a name="return-value"></a>戻り値

カプセル化さ `VARIANT` れた。

## <a name="remarks"></a>解説

カプセル化されたを抽出して返した `VARIANT` 後、この `_variant_t` オブジェクトを破棄せずにクリアします。 このメンバー関数は、を `VARIANT` カプセル化から削除し、 `VARTYPE` このオブジェクトのを `_variant_t` VT_EMPTY に設定します。 `VARIANT` [VariantClear](/windows/win32/api/oleauto/nf-oleauto-variantclear)関数を呼び出すことによって返されたを解放します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
