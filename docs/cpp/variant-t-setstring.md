---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 0cd300a09c29668c496d93109d1bc862947e948c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187558"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft 固有の仕様**

この `_variant_t` オブジェクトに文字列を代入します。

## <a name="syntax"></a>構文

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>パラメーター

*.Psrc*<br/>
文字列へのポインター。

## <a name="remarks"></a>解説

ANSI 文字列を Unicode `BSTR` 文字列に変換し、この `_variant_t` オブジェクトに割り当てます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
