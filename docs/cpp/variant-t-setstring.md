---
description: '詳細情報: _variant_t:: SetString'
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: a36bab9189b6046325bb275469dc9dbdb495fc7a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161417"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**Microsoft 固有の仕様**

この `_variant_t` オブジェクトに文字列を代入します。

## <a name="syntax"></a>構文

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>パラメーター

*.Psrc*<br/>
文字列へのポインター。

## <a name="remarks"></a>解説

ANSI 文字列を Unicode `BSTR` 文字列に変換し、この `_variant_t` オブジェクトに割り当てます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
